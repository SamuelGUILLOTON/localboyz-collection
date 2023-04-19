<template>
  <div>
    <div class="video-container" v-for="video in videos" :key="video.id">
      <div class="video-iframe">
        <iframe
          class="video-card"
          title="YouTube video player"
          frameborder="0"
          allow="encrypted-media;"
          allowfullscreen
          :src="video.path"
        ></iframe>
      </div>
      <div class="desc-container">
        <h2>{{ video.title }}</h2>
        <p>Date : {{ video.date }}</p>
        <p>Location : {{ video.location }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoCard',
  props: {
    create: String
  },
  data() {
    return {
      videos: []
    }
  },
  created() {
    fetch('/video.csv')
      .then((response) => response.text())
      .then((csv) => {
        const lines = csv.split('\n')
        const headers = lines[0].split(',')
        const result = []
        for (let i = 1; i < lines.length; i++) {
          const obj = {}
          const currentline = lines[i].split(',')
          for (let j = 0; j < headers.length; j++) {
            obj[headers[j]] = currentline[j]
          }
          result.push(obj)
        }
        this.videos = result
      })
  }
}
</script>
<style lang="less" scoped>
.video-container {
  margin: 100px 0 75px 0;

  .desc-container {
    line-height: 23px;
    color: #dacfcf;

    h2,
    p {
      margin: 0;
    }
  }
}
@media (max-width: 768px) {
  .video-container {
    margin: 100px 0 75px 0;

    .desc-container {
      h2 {
        font-size: 20px;
      }
      p {
        font-size: 17px;
      }
    }
  }
}
</style>
