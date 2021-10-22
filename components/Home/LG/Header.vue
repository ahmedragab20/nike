<template>
  <header class="container text-center">
    <div class="d-none d-md-block">
      <div class="context">
        <h2>Nike Says Hello!</h2>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laudantium
          ad atque tempora excepturi obcaecati quaerat autem, praesentium rerum
          repellendus, quibusdam.
        </p>
      </div>
      <div class="preview container mt-3">
        <figure oncontextmenu="return false">
          <div>
            <img src="@/assets/h1.jpg" alt="Image" />
          </div>
          <div>
            <video
              src="@/assets/h2.mp4"
              autoplay
              loop
              aria-label="Video"
            ></video>
          </div>
          <div>
            <img src="@/assets/h3.jpg" alt="Image" />
          </div>
        </figure>
      </div>
      <a href="#section2" class="go-down"> scroll down </a>
    </div>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
header {
  margin-top: 12vh;

  .context {
    h2 {
      font-size: $headlg;
    }
    p {
      color: $darkFaded;
    }
  }

  .preview {
    figure {
      display: grid;
      grid-template-areas: 'one two three';
      grid-template-columns: repeat(3, 1fr);
      gap: 2px;

      &:nth-child(1) {
        grid-area: one;
      }
      &:nth-child(2) {
        grid-area: two;
      }
      &:nth-child(3) {
        grid-area: three;
      }

      div {
        img,
        video {
          width: $full - 5;
          height: $full - 5;
          object-fit: cover;
          border-radius: 15px;
          transition: $transition;
        }

        img:hover {
          transform: translateY(10px);
        }
        video:hover {
          transform: scale(1.08);
        }
      }
    }
  }

  .go-down {
    animation: down 1s infinite;
  }
  @keyframes down {
    0% {
      letter-spacing: 1px;
    }
    50% {
      letter-spacing: 0px;
    }
    100% {
      letter-spacing: 1px;
    }
  }
}
</style>
