<template>
  <div class="home">
    <main>
      <div class="form-container">
        <!-- Import des étapes -->
        <StepFormHead v-bind:activeStep="indexActive"/>

        <!-- Import du formulaire -->

        <form action="" method="POST">

          <div class="etape etape1 active">
            <p>créer une entreprise</p>
            <h2>Quel est le statut de votre entreprise ?</h2>
            <select name="" id="">
              <option value="">EURL</option>
              <option value="">SARL</option>
            </select>
            
            <div class="btn-container">
              <p class="btn-previous">revenir plus tard</p>
              <p class="btn-next" @click="checkStep">continuer</p>
            </div>
          </div>
          
          <!-- Etape 2 -->
          <div class="etape etape2 hidden">
            <p>créer une entreprise</p>
            <h2>Informations de l'entreprise</h2>

            <!-- Nom légal de l'entreprise -->
            <label for="nom_entreprise">
              Nom légal de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="nom_entreprise" required>
            
            <!-- Email -->
            <label for="email_entreprise">
              Email de l'entreprise*
            </label>
            <input type="text" placeholder="email" id="email_entreprise" required>
            
            <!-- Adresse -->
            <label for="adresse_entreprise">
              Adresse de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>
            
            <!-- Etape double -->
            <div class="etape-double">
              <div class="block1">
                <label for="code_postal">
                  Code postal*
                </label>
                <input type="number" placeholder="freelance" id="code_postal" required>
              </div>

              <div class="block2">
                <label for="ville">
                  Ville*
                </label>
                <input type="number" placeholder="freelance" id="ville" required>
              </div>
            </div>

            <!-- region -->
            <label for="adresse_entreprise">
              Adresse de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- pays -->
            <label for="adresse_entreprise">
              Pays*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- Siret -->
            <label for="adresse_entreprise">
              Siret*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- Capital -->
            <label for="adresse_entreprise">
              Capital social de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>
            
            <p class="required-form-info">*Informations obligatoires</p>

            <!-- btn validation  -->
            <div class="btn-container">
              <p class="btn-previous" @click="previousStep">revenir plus tard</p>
              <p class="btn-next" @click="checkStep">continuer</p>
            </div>
          </div>

          <!-- Etape 3 -->
          <div class="etape etape3 hidden">
            <p>créer une entreprise</p>
            <h2>Représentant de l'entreprise</h2>

            <!-- prenom du représentant -->
            <label for="prenom_representant">
              Prénom du représentant*
            </label>
            <input type="text" placeholder="freelance" id="prenom_representant" required>

            <!-- Nom du représentant -->
            <label for="nom_representant">
              Nom du représentant*
            </label>
            <input type="text" placeholder="freelance" id="nom_representant" required>
            
            <!-- Email -->
            <label for="email_entreprise">
              Email de l'entreprise*
            </label>
            <input type="text" placeholder="email" id="email_entreprise" required>
            
            <!-- Adresse -->
            <label for="adresse_entreprise">
              Adresse de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>
            
            <!-- Etape double -->
            <div class="etape-double">
              <div class="block1">
                <label for="code_postal">
                  Code postal*
                </label>
                <input type="number" placeholder="freelance" id="code_postal" required>
              </div>

              <div class="block2">
                <label for="ville">
                  Ville*
                </label>
                <input type="number" placeholder="freelance" id="ville" required>
              </div>
            </div>

            <!-- region -->
            <label for="adresse_entreprise">
              Adresse de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- pays -->
            <label for="adresse_entreprise">
              Pays*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- Siret -->
            <label for="adresse_entreprise">
              Siret*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>

            <!-- Capital -->
            <label for="adresse_entreprise">
              Capital social de l'entreprise*
            </label>
            <input type="text" placeholder="freelance" id="adresse_entreprise" required>
            
            <p class="required-form-info">*Informations obligatoires</p>

            <!-- btn validation  -->
            <div class="btn-container">
              <p class="btn-previous" @click="previousStep">revenir plus tard</p>
              <p class="btn-next">continuer</p>
            </div>
          </div>

        </form>
      </div>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import StepFormHead from '@/components/StepFormHead.vue'

export default {
  name: 'Home',
  components: {
    StepFormHead
  },
  data () {
    return {
      isValidated : false,
      steps: null,
      indexActive: 0
    }
  },
  mounted () {
    this.steps = document.querySelectorAll('.etape')
  },
  methods: {
    checkStep (e) {
      // let allSteps = document.querySelectorAll('.etape')
      let parentBtn = e.target.closest('.etape')
      let parentBtnIsActive = e.target.closest('.etape').classList.contains('active')
      let parentNextEl = e.target.closest('.etape').nextElementSibling

      if (parentBtnIsActive) {
        parentNextEl.classList.add('active')
        parentNextEl.classList.remove('hidden')
        
        parentBtn.classList.remove('active')
        parentBtn.classList.add('hidden')

        this.steps.forEach((step, index) => {
          if(step.classList.contains('active')) {
            this.indexActive = index
          }
        })
      }
    },
    previousStep (e) {
      // let allSteps = document.querySelectorAll('.etape')
      let parentBtn = e.target.closest('.etape')
      let parentBtnIsActive = e.target.closest('.etape').classList.contains('active')
      let parentNextEl = e.target.closest('.etape').previousElementSibling

      if (parentBtnIsActive) {
        parentNextEl.classList.add('active')
        parentNextEl.classList.remove('hidden')
        
        parentBtn.classList.remove('active')
        parentBtn.classList.add('hidden')

        this.steps.forEach((step, index) => {
          if(step.classList.contains('active')) {
            this.indexActive = index
          }
        })
      }
    }
  }
}
</script>

<style lang="scss">
$primary : #2d2f39;
$secondary : #373945;
$blue-link : #0175fb;
$blue-btn : #0076ff;

.home {
  min-height: 100vh;
  background-color: $primary;
}

.etape {
  padding: 30px;
  background-color: $secondary;
  
  &.hidden {
    display: none;
  }
  label {
    display: block;
    margin-top: 20px;
    margin-bottom: 10px;
    text-align: left;
  }

  label, input, select {
    width: 100%;
  }

  input, select {
    height: 35px;
    padding-left: 10px;
    color: #fff;
    border: 1px solid #fff;
    border-radius: 5px;
    background-color: transparent;
    box-sizing: border-box;

    &::placeholder {
      color: #ccc;
    }
  }

  select {
    option {
      color: #000;
    }
  }
}

.etape-double {
  display: flex;

  .block1 {
    width: 33%;
  }

  .block2 {
    width: calc(67% - 11px);
    margin-left: 11px;
  }
}

// Btns prev, next
.btn-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;

  .btn-previous, .btn-next {
    transition: 1s;
    &:hover {
      opacity: .7;
    }
  }

  .btn-previous {
    color: $blue-link;
    text-transform: uppercase;
    cursor: pointer;
  }

  .btn-next {
    padding: 10px;
    background-color: $blue-btn;
    text-transform: uppercase;
    color: #fff;
    text-transform: uppercase;
    border-radius: 10px;
    cursor: pointer;
  }
}

.required-form-info {
  font-size: 12px;
  font-style: italic;
  text-align: left;
}

.form-container {
  max-width: 500px;
  margin: 0 auto;
}
</style>
