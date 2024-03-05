<template>
  <div class="selfie-capture">
    <header class="header">
      <h1><div id="skewed">MUNCH</div> "Selfie Booth"</h1>
    </header>
    <div class="camera-feed">
      <video ref="video" autoplay class="mirrored-video"></video>
    </div>
    <button @click="captureSelfie">Capture Selfie</button>
  </div>
</template>

<script>

export default {
  name: 'SelfieCapture',
  mounted() {
    this.startCamera();
  },
  methods: {
    async startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        this.$refs.video.srcObject = stream;
      } catch (err) {
        console.error("Error accessing the camera: ", err);
      }
    },
    captureSelfie() {
      const canvas = document.createElement('canvas');
      const video = this.$refs.video;
      canvas.width = video.videoWidth;
      canvas.height = video.videoHeight;
      // Apply the mirror effect for the canvas as well
      const context = canvas.getContext('2d');
      context.translate(canvas.width, 0);
      context.scale(-1, 1);
      context.drawImage(video, 0, 0);
      canvas.toBlob(blob => {
        this.uploadImage(blob);
      }, 'image/jpeg');
    },
    async uploadImage(imageBlob) {
      const formData = new FormData();
      formData.append('selfie', imageBlob);

      try {
        await fetch('YOUR_BACKEND_ENDPOINT', {
          method: 'POST',
          body: formData,
        });
        console.log('Image uploaded successfully');
      } catch (err) {
        console.error('Upload error: ', err);
      }
    },
  },
};
</script>

<style>

.camera-feed {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 40px 0;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  background: #ffffff;
}
#skewed {
  transform: skew(18deg);
  display: inline-block;
  color: #FE390F;
}
#skewed:hover {
  color: #fbfbfb;
  transition-duration: 1s;
  text-decoration: none;
}

.mirrored-video {
  transform: scaleX(-1);
}

</style>
