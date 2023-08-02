<template>
 <div class="my-select delay-3">
        <h4 
            class="my-select-title"
            @click="areOptionsVisible = !areOptionsVisible"
        >
            {{selectedOption}}
            <span class="arrow-right"></span>
        </h4>
        <div 
            class="options"
            v-if="areOptionsVisible"
        >
            <p 
                class="option"
                :style="option.background"
                v-for="option in options" 
                :key="option.value"
                @click="selectOption(option)"
            >{{option.name}}</p>
        </div>
    </div> 
</template>

<script>
export default {
    name: 'MySelect',
    data() {
        return {
            areOptionsVisible: false,
        }
    },
    props: {
        options: {
            type: Array,
            default() {
                return []
            }
        },
        selectedOption: {
            type: String,
            default: ''
        }
    },
    methods: {
        selectOption(option) {
            this.$emit('selectOption', option);
            this.areOptionsVisible = false;
        },
        hideSelect() {
            this.areOptionsVisible = false;
        },
        sortByCategories(option) {
            this.$emit('sortByCategories', option)
        }
    },
    mounted() {
        document.addEventListener('click', this.hideSelect.bind(this), true);
    },
    beforeDestroy() {
        document.removeEventListener('click', this.hideSelect.bind);
    }
}
</script>

<style>
.my-select {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--navbar-bg-color);
  border-radius: 4px;
  border: var(--box-border);
  cursor: pointer;
  max-width: 12rem;
  position: relative;
  z-index: 12;
  margin-left: auto;
  transition: .2s;
}
.my-select-title {
  width: 100%;
  border-radius: 4px;
  text-align: center;
  padding: 0.5rem;
  box-shadow: var(--box-shadow);
  transition: .2s;
}
.my-select-title:hover {
  background-color: var(--nav-item-bg);
}
.arrow-right {
  display: inline-block;
  width: .8rem;
  height: .5rem;
  background-color: var(--default-text-color);
  clip-path: polygon(0 0, 100% 0, 50% 100%);
  margin-left: 0.5rem;
}
.options {
  display: flex;
  justify-content: flex-start;
  width: 100%;
  position: absolute;
  top: 2.6rem;
  left: 0;
  flex-direction: column;
  align-items: flex-end;
  z-index: 7;
  padding: 0.5rem;
  background-color: var(--navbar-mobile-bg-color);
  backdrop-filter: blur(5px);
  border-radius: 0 0 4px 4px;
  border: var(--box-border);
}
.option {
  padding: .5rem 1.6rem;
  border-radius: 4px;
  border: var(--box-border);
  margin: 0 0 .5rem 0;
  box-shadow: var(--box-shadow);
}
</style>