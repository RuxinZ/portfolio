<script lang="ts">
  let time = 0;
	let duration: number;
  let paused = true;

  let showControls = true;
	let showControlsTimeout: ReturnType<typeof setTimeout>;

  // Used to track time of last mouse down event
	let lastMouseDown: Date;

  function handleMove(e: any){
    clearTimeout(showControlsTimeout);
		showControlsTimeout = setTimeout(() => (showControls = false), 2500);
		showControls = true;

    if (!duration) return; // video not loaded yet
		if (e.type !== 'touchmove' && !(e.buttons & 1)) return; // mouse not down

		const clientX = e.type === 'touchmove' ? e.touches[0].clientX : e.clientX;
		const { left, right } = ( this as HTMLElement).getBoundingClientRect();
		time = (duration * (clientX - left)) / (right - left);
  }

  const handleMousedown =  (e: MouseEvent) => {
		lastMouseDown = new Date();
	}

	const handleMouseup = (e: MouseEvent) => {
		if (new Date().getTime() - lastMouseDown.getTime() < 300) {
			if (paused) (e.target as HTMLVideoElement).play();
			else (e.target as HTMLVideoElement).pause();
		}
	}

  const formatTime = (time: number) => {
    let hour = Math.floor(time / 360);
    let minute = Math.floor((time - hour * 360) / 60);
    let second = Math.floor( time % 60);
    let hourStr = hour > 0 ? hour >= 10 ?  hour.toString() : "0" +  hour + ":": "";
    let minuteStr =  minute >= 10 ?  minute.toString() : "0" +  minute + ":";
    let seondStr = second >= 10 ?  second.toString() : "0" +  second;
    return hourStr + minuteStr + seondStr

  }

</script>

<div class="video-container flex flex-col items-center">
  <div class="">
    <video
      poster="https://sveltejs.github.io/assets/caminandes-llamigos.jpg"
      src="https://sveltejs.github.io/assets/caminandes-llamigos.mp4"
      on:mousemove={handleMove}
      on:touchmove|preventDefault={handleMove}
      on:mousedown={handleMousedown}
      on:mouseup={handleMouseup}
      bind:currentTime={time}
      bind:duration
      bind:paused
      controls
    >
      <track kind="captions" />
    </video>
    <!-- <div class="controls flex flex-col">
      <progress value={time / duration || 0} />
      <div class="flex">
        <button class="play" aria-label={paused ? 'play' : 'pause'}>Play</button>
        <div class="flex px-5"></div>
        <div><span>{time ? formatTime(time) : '00:00'}</span></div>
        <div>/</div>
        <div>{duration ? formatTime(duration) : '00:00'}</div>
      </div>
    </div> -->
  
    

  </div>
</div>

<style>
.video-container {
  border: 2px solid red;
  width: 80%;
}

/* progress {
  display: block;
  width:100%;
} */
</style>