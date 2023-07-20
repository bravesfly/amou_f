<template>
  <div class="video-background">
    <video playsinline autoplay="autoplay" muted loop>
      <source :src="videoURL" type="video/mp4">
    </video>
    <div class="content">
      <div class="header">
        <img src="./assets/images/appIcon.png" alt="Logo" class="logo" />
        <h1 class="slogan">Amoury Dating</h1>
      </div>
      <img src="./assets/images/slogan.png" alt="Center Image" class="center-image" />
      <button v-if="isAndroid">
        <span>Android Download</span>
        <svg height="24" width="24" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 0h24v24H0z" fill="none"></path>
          <path
            d="M1 14.5a6.496 6.496 0 0 1 3.064-5.519 8.001 8.001 0 0 1 15.872 0 6.5 6.5 0 0 1-2.936 12L7 21c-3.356-.274-6-3.078-6-6.5zm15.848 4.487a4.5 4.5 0 0 0 2.03-8.309l-.807-.503-.12-.942a6.001 6.001 0 0 0-11.903 0l-.12.942-.805.503a4.5 4.5 0 0 0 2.029 8.309l.173.013h9.35l.173-.013zM13 12h3l-4 5-4-5h3V8h2v4z"
            fill="currentColor"></path>
        </svg>
      </button>
      <button v-else>
        <span>IOS(Coming Soon)</span>
        <svg height="24" width="24" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path d="M0 0h24v24H0z" fill="none"></path>
          <path
            d="M1 14.5a6.496 6.496 0 0 1 3.064-5.519 8.001 8.001 0 0 1 15.872 0 6.5 6.5 0 0 1-2.936 12L7 21c-3.356-.274-6-3.078-6-6.5zm15.848 4.487a4.5 4.5 0 0 0 2.03-8.309l-.807-.503-.12-.942a6.001 6.001 0 0 0-11.903 0l-.12.942-.805.503a4.5 4.5 0 0 0 2.029 8.309l.173.013h9.35l.173-.013zM13 12h3l-4 5-4-5h3V8h2v4z"
            fill="currentColor"></path>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videoURL: 'https://res.origin-safari.com/assets/fen/bg.mp4.js', // 背景图片的 URL
      // videoURL: 'https://res.origin-safari.com/assets/jue/bg.mp4.js', // 背景图片的 URL
      isAndroid: navigator.userAgent.toLowerCase().indexOf("android") > -1,
      apkURL: 'your-apk-url',
    }
  },
  methods:{
    androidDownload(){
      window.open(this.apkURL, '_blank');
      
    }
  }
}
</script>

<style scoped>
.video-background {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.video-background video {
  position: absolute;
  top: 50%;
  left: 50%;
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: -100;
  transform: translate(-50%, -50%);
}

.content {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  padding: 20px;
}

.header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content:space-around;
  width: 90%;
  
}

.logo {
  width: 50px; /* 更改 logo 图片的大小 */
  margin-right: 20px; /* 添加 logo 和 slogan 之间的间距 */
}

.slogan {
  font-size: 28px; /* 更改 slogan 的字体大小 */
  text-align: left;
  font-family: Helvetica,"sans-serif";
  color: #ff3c71;
}

/* From www.lingdaima.com */
button {
 cursor: pointer;
 font-weight: 700;
 height: 6vh;
 font-family: Helvetica,"sans-serif";
 transition: all .2s;
 padding: 10px 20px;
 margin-bottom: 150px;
 border-radius: 100px;
 background: #ff3c71;
 border: 1px solid transparent;
 display: flex;
 align-items: center;
 font-size: 15px;
 color: #ffffff;
}

.center-image {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 70%; /* 更改中心图片的大小 */
  transform: translate(-50%, -50%);
}


button > svg {
 width: 34px;
 margin-left: 10px;
 transition: transform .3s ease-in-out;
}

button:hover svg {
 transform: translateX(5px);
}

button:active {
 transform: scale(0.95);
}


</style>