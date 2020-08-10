<template>
  <div class="step_form-head">
    <div class="step one active">
      <div class="step-content">
        <div class="step-icon">
          <svg version="1.1" id="Calque_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
            viewBox="282.4 326.5 15 16.9" enable-background="new 282.4 326.5 15 16.9" xml:space="preserve">
              <g>
                <path d="M296.2,330.8l1.2-1.3v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0l0,0l-1.1,1.3c0.8,0.1,1.5,0.4,2.2,0.9
                  C295.6,329.4,296,330.1,296.2,330.8z M286,339.2c-0.7-0.6-1.5-0.8-2.3-0.8l0,0l-0.7,2.5l-0.7,2.5l2.4-1l2.4-1l0,0
                  C287,340.6,286.7,339.8,286,339.2z M293.2,334.3l2.7-3.1v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0v0l-2.7,3.1
                  l0,0l0,0l-0.6,0.7l-5.2,6c0.8,0.1,1.5,0.4,2.2,0.9c0.7,0.5,1.1,1.3,1.3,2l5.2-6L293.2,334.3L293.2,334.3L293.2,334.3z"/>
              </g>
          </svg>
        </div>
        <p class="step-label">
          Statut
        </p>
      </div>
    </div>

    <div class="step two hidden">
      <div class="step-content">
        <div class="step-icon">
          <svg version="1.1" id="Calque_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
            viewBox="282.4 326.5 15 16.9" enable-background="new 282.4 326.5 15 16.9" xml:space="preserve">
              <g>
                <path d="M296.2,330.8l1.2-1.3v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0l0,0l-1.1,1.3c0.8,0.1,1.5,0.4,2.2,0.9
                  C295.6,329.4,296,330.1,296.2,330.8z M286,339.2c-0.7-0.6-1.5-0.8-2.3-0.8l0,0l-0.7,2.5l-0.7,2.5l2.4-1l2.4-1l0,0
                  C287,340.6,286.7,339.8,286,339.2z M293.2,334.3l2.7-3.1v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0v0l-2.7,3.1
                  l0,0l0,0l-0.6,0.7l-5.2,6c0.8,0.1,1.5,0.4,2.2,0.9c0.7,0.5,1.1,1.3,1.3,2l5.2-6L293.2,334.3L293.2,334.3L293.2,334.3z"/>
              </g>
          </svg>
        </div>
        <p class="step-label">
          Information
        </p>
      </div>
    </div>

    <div class="step three hidden">
      <div class="step-content">
        <div class="step-icon">
          <svg version="1.1" id="Calque_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
            viewBox="282.4 326.5 15 16.9" enable-background="new 282.4 326.5 15 16.9" xml:space="preserve">
              <g>
                <path d="M296.2,330.8l1.2-1.3v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0l0,0l-1.1,1.3c0.8,0.1,1.5,0.4,2.2,0.9
                  C295.6,329.4,296,330.1,296.2,330.8z M286,339.2c-0.7-0.6-1.5-0.8-2.3-0.8l0,0l-0.7,2.5l-0.7,2.5l2.4-1l2.4-1l0,0
                  C287,340.6,286.7,339.8,286,339.2z M293.2,334.3l2.7-3.1v0h0c-0.1-0.8-0.5-1.6-1.2-2.1c-0.7-0.5-1.5-0.8-2.2-0.8l0,0v0l-2.7,3.1
                  l0,0l0,0l-0.6,0.7l-5.2,6c0.8,0.1,1.5,0.4,2.2,0.9c0.7,0.5,1.1,1.3,1.3,2l5.2-6L293.2,334.3L293.2,334.3L293.2,334.3z"/>
              </g>
          </svg>
        </div>
        <p class="step-label">
          Représentant
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StepFormHead',
  data () {
    return {
      steps : null
    }
  },
  props: {
    activeStep: Number
  },
  watch: {
    activeStep : function () {
      this.steps.forEach((step, index) => {
        if(index != this.activeStep) {
          this.steps[index].classList.remove('active')
          this.steps[index].classList.add('hidden')
        } else {
          this.steps[this.activeStep].classList.add('active')
          this.steps[this.activeStep].classList.remove('hidden')
        }
      })

    }
  },
  mounted () {
    this.steps = document.querySelectorAll('.step')
  },
}
</script>

<style scoped lang="scss">
$blue-link : #0175fb;

.step_form-head {
  display: flex;
  justify-content: space-between;
  padding-top: 20px;
  padding-bottom: 20px;
}

.step {
  display: flex;

  &.active {
    .step-icon {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 30px;
      height: 30px;
      margin: 0;
      border-color: $blue-link;
    }
    svg {
      display: inline-block;
      fill: $blue-link;
      width: 15px;
    }
    .step-label {
      color: $blue-link;
    }
  }

  &.hidden {
    svg {
      display: none;
    }
  }

  .step-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .step-icon {
    width: 5px;
    height: 5px;
    margin: 15px;
    border: 1px solid #ccc;
    border-radius: 50%;
  }
}
</style>
