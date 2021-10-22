<template>
  <div id="section2" class="article container mt-3">
    <div class="row">
      <div class="col-lg-6 order-lg-last">
        <div class="images">
          <div>
            <img src="@/assets/a2.jpg" alt="image" />
          </div>
          <div>
            <video src="@/assets/a1.mp4" autoplay loop></video>
          </div>
        </div>
      </div>
      <div class="col-lg-6 order-lg-first">
        <div class="context">
          <div class="d-none d-md-block">
            <h2>Do You Like Fashion?!</h2>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam
              cumque non porro harum officia sit animi totam error, qui, impedit
              ipsa quaerat soluta ab ipsam laboriosam consectetur ratione
              assumenda commodi!
            </p>
            <button>Read more!</button>
          </div>
          <div class="d-block d-md-none text-center">
            <h3>Do You Like Fashion?!</h3>
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam
              cumque non porro harum officia sit animi totam error, qui, impedit
              ipsa quaerat soluta ab ipsam laboriosam consectetur ratione
              assumenda commodi!
            </p>
            <button class="button">Read more!</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.article {
  .images {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
    div {
      img,
      video {
        width: $full + 1;
        height: $full;
        object-fit: cover;
        border-radius: 20px;
        box-shadow: $darkShadow;
        transition: $transition;

        &:hover {
          transform: scale(1.1);
        }
      }
    }
  }

  .context {
    padding-top: 30px;
    .d-md-block {
      h2 {
        font-size: $headlg;
      }
    }

    .d-md-none {
      p {
        font-size: $sm;
        color: $darkFaded;
      }
    }
  }
}
</style>
