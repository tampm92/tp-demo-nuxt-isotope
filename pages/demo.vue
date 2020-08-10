<template>
  <div class="w-full min-h-screen bg-gray-800 text-white pt-8">

    <vs-sidebar
      absolute
      hover-expand
      reduce
      v-model="active"
      open
      >
      <template #logo>
        <img src="/tp-100.png">
      </template>
      <vs-sidebar-item id="isotope">
        <template #icon>
          <i class="material-icons">done_outline</i>
        </template>
        Isotope
      </vs-sidebar-item>
      <vs-sidebar-item id="vuesax">
        <template #icon>
          <i class="material-icons">account_balance</i>
        </template>
        Vuesax
      </vs-sidebar-item>
      <vs-sidebar-item id="more">
        <template #icon>
          <i class="material-icons">more</i>
        </template>
        More...
      </vs-sidebar-item>
      <template #footer>
        <vs-row justify="space-between">
          <vs-avatar class="mb-2" color="#969696" badge-color="danger" badge-position="top-right">
            <i class="material-icons">notification_important</i>
            <template #badge>
              28
            </template>
          </vs-avatar>
          <vs-avatar class="mb-2" color="#FFFFFF">
            <img src="/tp-100.png">
          </vs-avatar>
        </vs-row>
      </template>
    </vs-sidebar>

    <section class="container mx-auto px-4" v-show="active === 'isotope'">
      <h2 class="text-4xl font-bold text-center text-gray-300 mb-16">
        TP-Demo Nuxt Isotope
      </h2>
      <div class="flex flex-wrap">
        <div class="w-full mb-4">
          <h4 class="text-xl text-gray-300">Filtering</h4>
          <div class="flex">
            <vs-button class="inline" :upload="filterStr === '*'" @click="onFilter('*')">
              All
            </vs-button>
            <vs-button class="inline" :upload="filterStr === '.metal'" @click="onFilter('.metal')">
              Metal
            </vs-button>
            <vs-button class="inline" :upload="filterStr === '.transition'" @click="onFilter('.transition')">
              Transition
            </vs-button>
            <vs-button class="inline" :upload="filterStr === '.metal:not(.transition)'" @click="onFilter('.metal:not(.transition)')">
              Metal but not Transition
            </vs-button>
          </div>
        </div>
        <div class="w-full mb-4">
          <h4 class="text-xl text-gray-300">Sorting</h4>
          <div class="flex">
            <vs-button class="inline" :upload="sorterStr === 'original-order'" @click="onSorter('original-order')">
              All
            </vs-button>
            <vs-button class="inline" :upload="sorterStr === 'name'" @click="onSorter('name')">
              Name
            </vs-button>
            <vs-button class="inline" :upload="sorterStr === 'symbol'" @click="onSorter('symbol')">
              Symbol
            </vs-button>
            <vs-button class="inline" :upload="sorterStr === 'number'" @click="onSorter('number')">
              Number
            </vs-button>
            <vs-button class="inline" :upload="sorterStr === 'category'" @click="onSorter('category')">
              Category
            </vs-button>
          </div>
        </div>
        <div class="w-full">
          <div class="grid">
            <div class="element-item transition metal " data-category="transition">
              <h3 class="name">
                Mercury
              </h3>
              <p class="symbol">
                Hg
              </p>
              <p class="number">
                80
              </p>
              <p class="weight">
                200.59
              </p>
            </div>
            <div class="element-item metalloid " data-category="metalloid">
              <h3 class="name">
                Tellurium
              </h3>
              <p class="symbol">
                Te
              </p>
              <p class="number">
                52
              </p>
              <p class="weight">
                127.6
              </p>
            </div>
            <div class="element-item post-transition metal " data-category="post-transition">
              <h3 class="name">
                Bismuth
              </h3>
              <p class="symbol">
                Bi
              </p>
              <p class="number">
                83
              </p>
              <p class="weight">
                208.980
              </p>
            </div>
            <div class="element-item post-transition metal " data-category="post-transition">
              <h3 class="name">
                Lead
              </h3>
              <p class="symbol">
                Pb
              </p>
              <p class="number">
                82
              </p>
              <p class="weight">
                207.2
              </p>
            </div>
            <div class="element-item transition metal " data-category="transition">
              <h3 class="name">
                Gold
              </h3>
              <p class="symbol">
                Au
              </p>
              <p class="number">
                79
              </p>
              <p class="weight">
                196.967
              </p>
            </div>
            <div class="element-item alkali metal " data-category="alkali">
              <h3 class="name">
                Potassium
              </h3>
              <p class="symbol">
                K
              </p>
              <p class="number">
                19
              </p>
              <p class="weight">
                39.0983
              </p>
            </div>
            <div class="element-item alkali metal " data-category="alkali">
              <h3 class="name">
                Sodium
              </h3>
              <p class="symbol">
                Na
              </p>
              <p class="number">
                11
              </p>
              <p class="weight">
                22.99
              </p>
            </div>
            <div class="element-item transition metal " data-category="transition">
              <h3 class="name">
                Cadmium
              </h3>
              <p class="symbol">
                Cd
              </p>
              <p class="number">
                48
              </p>
              <p class="weight">
                112.411
              </p>
            </div>
            <div class="element-item alkaline-earth metal " data-category="alkaline-earth">
              <h3 class="name">
                Calcium
              </h3>
              <p class="symbol">
                Ca
              </p>
              <p class="number">
                20
              </p>
              <p class="weight">
                40.078
              </p>
            </div>
            <div class="element-item transition metal " data-category="transition">
              <h3 class="name">
                Rhenium
              </h3>
              <p class="symbol">
                Re
              </p>
              <p class="number">
                75
              </p>
              <p class="weight">
                186.207
              </p>
            </div>
            <div class="element-item post-transition metal " data-category="post-transition">
              <h3 class="name">
                Thallium
              </h3>
              <p class="symbol">
                Tl
              </p>
              <p class="number">
                81
              </p>
              <p class="weight">
                204.383
              </p>
            </div>
            <div class="element-item metalloid " data-category="metalloid">
              <h3 class="name">
                Antimony
              </h3>
              <p class="symbol">
                Sb
              </p>
              <p class="number">
                51
              </p>
              <p class="weight">
                121.76
              </p>
            </div>
            <div class="element-item transition metal " data-category="transition">
              <h3 class="name">
                Cobalt
              </h3>
              <p class="symbol">
                Co
              </p>
              <p class="number">
                27
              </p>
              <p class="weight">
                58.933
              </p>
            </div>
            <div class="element-item lanthanoid metal inner-transition " data-category="lanthanoid">
              <h3 class="name">
                Ytterbium
              </h3>
              <p class="symbol">
                Yb
              </p>
              <p class="number">
                70
              </p>
              <p class="weight">
                173.054
              </p>
            </div>
            <div class="element-item noble-gas nonmetal " data-category="noble-gas">
              <h3 class="name">
                Argon
              </h3>
              <p class="symbol">
                Ar
              </p>
              <p class="number">
                18
              </p>
              <p class="weight">
                39.948
              </p>
            </div>
            <div class="element-item diatomic nonmetal " data-category="diatomic">
              <h3 class="name">
                Nitrogen
              </h3>
              <p class="symbol">
                N
              </p>
              <p class="number">
                7
              </p>
              <p class="weight">
                14.007
              </p>
            </div>
            <div class="element-item actinoid metal inner-transition " data-category="actinoid">
              <h3 class="name">
                Uranium
              </h3>
              <p class="symbol">
                U
              </p>
              <p class="number">
                92
              </p>
              <p class="weight">
                238.029
              </p>
            </div>
            <div class="element-item actinoid metal inner-transition " data-category="actinoid">
              <h3 class="name">
                Plutonium
              </h3>
              <p class="symbol">
                Pu
              </p>
              <p class="number">
                94
              </p>
              <p class="weight">
                (244)
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="container mx-auto px-4" v-show="active === 'vuesax'">
      <h2 class="text-4xl font-bold text-center text-gray-300 mb-16">
        TP-Demo Nuxt Vuesax
      </h2>

      <div class="w-full my-4">
        <h4 class="text-xl pb-2">Loading</h4>
        <div class="flex" :class="{ hasOpenLoading }">
          <div v-for="(type, i) in loadingTypes" :key="`box${i}`" :ref="`box${i}`" @click="handleClickLoading(type)" class="box-loading inline" />
        </div>
      </div>

      <hr>
      
      <div class="w-full my-4">
        <h4 class="text-xl pb-2">Dialog</h4>
        
        <div class="flex">
          <vs-button @click="dialogActive=!dialogActive">
            Open Dialog
          </vs-button>
          <vs-dialog v-model="dialogActive">
            <template #header>
              <h4 class="not-margin">
                Welcome to <b>Vuesax</b>
              </h4>
            </template>


            <div class="con-form">
              <vs-input v-model="dialogEmail" placeholder="Email">
                <template #icon>
                  @
                </template>
              </vs-input>
              <vs-input type="password" v-model="dialogPassword" placeholder="Password">
                <template #icon>
                  <i class='bx bxs-lock'></i>
                </template>
              </vs-input>
              <div class="flex">
                <vs-checkbox v-model="dialogRemember">Remember me</vs-checkbox>
                <a href="#">Forgot Password?</a>
              </div>
            </div>

            <template #footer>
              <div class="footer-dialog">
                <vs-button block>
                  Sign In
                </vs-button>

                <div class="new">
                  New Here? <a href="#">Create New Account</a>
                </div>
              </div>
            </template>
          </vs-dialog>
        </div>
      </div>

      <hr>

      <div class="w-full my-4">
        <h4 class="text-xl pb-2">Notification</h4>
        
        <div class="flex">
          <vs-button shadow icon @click="openNotification(null, null)">
            <i class='bx bx-border-radius b-r'></i>
          </vs-button>
          <vs-button flat icon @click="openNotification(null, 'primary')">
            <i class='bx bx-border-radius b-r'></i>
          </vs-button>
          <vs-button flat success icon @click="openNotification('top-right', 'success')">
            <i class='bx bx-border-radius t-r'></i>
          </vs-button>
          <vs-button flat danger icon @click="openNotification('top-left', 'danger')">
            <i class='bx bx-border-radius t-l'></i>
          </vs-button>
          <vs-button flat warn icon @click="openNotification('bottom-left', 'warn')">
            <i class='bx bx-border-radius b-l'></i>
          </vs-button>
          <vs-button flat dark icon @click="openNotification('bottom-center', '#000000')">
            <i class='bx bx-border-bottom' ></i>
          </vs-button>
          <vs-button flat color="#7d33ff" icon @click="openNotification('top-center', '#7d33ff')">
            <i class='bx bx-border-top' ></i>
          </vs-button>
          <vs-button flat color="rgb(59,222,200)" icon @click="openNotification(null, 'rgb(59,222,200)')">
            <i class='bx bx-border-radius b-r'></i>
          </vs-button>
        </div>
      </div>

      <hr>
      
      <div class="w-full my-4">
        <h4 class="text-xl pb-2">Alert</h4>
        
        <div class="block">
          <vs-button class="mb-4" @click="alertActive=true">
            Open Alert 10s
          </vs-button>
          <vs-alert :progress="alertProgress" v-model="alertActive">
            <template #title>
              Vuesax Framework
            </template>
            Vuesax (pronounced / vjusacksː /, as view sacks) is a <b>UI components framework</b>
            created with <a href="https://vuejs.org/">Vuejs</a> to make projects easily and with a
            Unique and pleasant style, Vuesax is created from scratch and designed for all types of
            developed from the frontend lover to the backend that wants to easily create
            your visual approach to the end user
          </vs-alert>
        </div>
      </div>

    </section>

    <section class="container mx-auto px-4" v-show="active === 'more'">
      <h2 class="text-4xl font-bold text-center text-gray-300 mb-16">
        More information
      </h2>
      <div class="block">
        <div class="block mb-12">
          <h4 class="text-xl text-yellow-700">Isotope: </h4>
          <a href="https://isotope.metafizzy.co/" target="_blank">https://isotope.metafizzy.co/</a>
        </div>
        
        <div class="block">
          <h4 class="text-xl text-green-700">Vuesax: </h4>
          <a href="https://vuesax.com/" target="_blank">https://vuesax.com/</a>
        </div>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  data() {
    return {
      grid: null,
      active: 'isotope',
      filterStr: '*',
      sorterStr: 'original-order',
      hasOpenLoading: false,
      loadingTypes: [
        'default',
        'waves',
        'corners',
        'border',
        'points',
        'square',
        'gradient',
        'rectangle',
        'circles',
        'square-rotate',
        'scale'
      ],
      dialogActive: false,
      dialogEmail: '',
      dialogPassword: '',
      dialogRemember: false,
      alertActive: false,
      alertTime: 6000,
      alertProgress: 0
    }
  },
  mounted() {
    this.$nextTick(() => {
      // vanilla JS
      const Isotope = require('isotope-layout')
      this.grid = new Isotope('.grid', {
        itemSelector: '.element-item',
        layoutMode: 'fitRows',
        getSortData: {
          name: '.name',
          symbol: '.symbol',
          number: '.number parseInt',
          category: '[data-category]'
        }
      })
    })

    this.loadingTypes.forEach((type, i) => {
      this.openLoading(type, `box${i}`)
    })
  },
  watch: {
    alertActive(val) {
      if(val) {
        var interval = setInterval(() => {
          this.alertProgress++
        }, this.alertTime / 100);

        setTimeout(() => {
          this.alertActive = false
          clearInterval(interval)
          this.alertProgress = 0
        }, this.alertTime);
      }
    }
  },
  methods: {
    onFilter(value) {
      this.filterStr = value
      this.grid.arrange({ filter: value })
    },
    onSorter(value) {
      this.sorterStr = value
      this.grid.arrange({ sortBy: value })
    },

    handleClickLoading(type) {
      const loading = this.$vs.loading({
        type
      })
      this.hasOpenLoading = true
      setTimeout(() => {
        loading.close()
        this.hasOpenLoading = false
      }, 3000)
    },
    openLoading(type, ref) {
      this.$vs.loading({
        target: this.$refs[ref][0],
        text: type,
        type
      })
    },
    openNotification(position = null, color) {
      try {
        const noti = this.$vs.notification({
          color,
          position,
          title: 'Documentation Vuesax 4.0+',
          text: 'These documents refer to the latest version of vuesax (4.0+), to see the documents of the previous versions you can do it here 👉 Vuesax 3.x'
        })
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style>
/* ---- vuesax ---- */

.vs-sidebar__item.hasIcon {
  outline: none;
}

.hasOpenLoading .box-loading {
  opacity: 0;
  transform: scale(0.7);
}
.box-loading {
  width: 120px;
  height: 120px;
  position: relative;
  margin: 5px;
  border-radius: 20px;
  box-shadow: 0px 10px 20px -10px rgba(0,0,0,0.07);
  overflow: hidden;
  cursor: pointer;
  transition: all 0.25s ease;
}
.box-loading:hover {
  transform: translate(0, -5px);
  box-shadow: 0px 15px 20px -10px rgba(0,0,0,0.09);
}
.box-loading >>>.vs-loading {
  padding: 0px;
}

.not-margin {
  margin: 0px;
  font-weight: normal;
  padding: 10px;
}
.con-form {
  width: 100%;
}
.con-form .flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.con-form .flex a {
  font-size: 0.8rem;
  opacity: 0.7;
}
.con-form .flex a:hover {
  opacity: 1;
}
.con-form .vs-checkbox-label {
  font-size: 0.8rem;
}
.con-form .vs-input-content {
  margin: 10px 0px;
  width: calc(100%);
}
.con-form .vs-input-content .vs-input {
  width: 100%;
}
.footer-dialog {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  width: calc(100%);
}
.footer-dialog .new {
  margin: 0px;
  margin-top: 20px;
  padding: 0px;
  font-size: 0.7rem;
}
.footer-dialog .new a {
  color: rgba(var(--vs-primary), 1) !important;
  margin-left: 6px;
}
.footer-dialog .new a:hover {
  text-decoration: underline;
}
.footer-dialog .vs-button {
  margin: 0px;
}


/* ---- isotope ---- */

.grid {
  border: 1px solid #333;
}

/* clear fix */
.grid:after {
  content: '';
  display: block;
  clear: both;
}

/* ---- .element-item ---- */

.element-item {
  position: relative;
  float: left;
  width: 100px;
  height: 100px;
  margin: 5px;
  padding: 10px;
  background: #888;
  color: #262524;
}

.element-item > * {
  margin: 0;
  padding: 0;
}

.element-item .name {
  position: absolute;

  left: 10px;
  top: 60px;
  text-transform: none;
  letter-spacing: 0;
  font-size: 12px;
  font-weight: normal;
}

.element-item .symbol {
  position: absolute;
  left: 10px;
  top: 0px;
  font-size: 42px;
  font-weight: bold;
  color: white;
}

.element-item .number {
  position: absolute;
  right: 8px;
  top: 5px;
}

.element-item .weight {
  position: absolute;
  left: 10px;
  top: 76px;
  font-size: 12px;
}

.element-item.alkali          { background: #F00; background: hsl(   0, 100%, 50%); }
.element-item.alkaline-earth  { background: #F80; background: hsl(  36, 100%, 50%); }
.element-item.lanthanoid      { background: #FF0; background: hsl(  72, 100%, 50%); }
.element-item.actinoid        { background: #0F0; background: hsl( 108, 100%, 50%); }
.element-item.transition      { background: #0F8; background: hsl( 144, 100%, 50%); }
.element-item.post-transition { background: #0FF; background: hsl( 180, 100%, 50%); }
.element-item.metalloid       { background: #08F; background: hsl( 216, 100%, 50%); }
.element-item.diatomic        { background: #00F; background: hsl( 252, 100%, 50%); }
.element-item.halogen         { background: #F0F; background: hsl( 288, 100%, 50%); }
.element-item.noble-gas       { background: #F08; background: hsl( 324, 100%, 50%); }
</style>
