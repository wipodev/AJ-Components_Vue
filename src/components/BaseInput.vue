<template>
  <div class="base-container">
    <label class="base-label" :class="{ 'is-Active': active }">
      <slot></slot>
    </label>
    <input
      :id="name"
      v-model="valor"
      :type="type"
      :name="name"
      class="base-input"
      @focus="inputActive('focus')"
      @focusout="inputActive"
    />
    <BaseEye v-if="type == 'password'" class="eye" @click="show()" />
  </div>
</template>

<script>
import BaseEye from "@/components/BaseEye.vue";

export default {
  components: {
    BaseEye,
  },
  props: {
    type: {
      type: String,
      default: "text",
    },
    name: {
      type: String,
      default: "input",
    },
    modelValue: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      active: false,
    };
  },
  computed: {
    valor: {
      get() {
        if (this.modelValue === "") {
          this.inputActive("focus");
        }
        return this.modelValue;
      },
      set(v) {
        this.$emit("update:modelValue", v);
      },
    },
  },
  mounted() {
    this.inputActive();
  },
  methods: {
    inputActive($e) {
      if (this.modelValue !== "" || $e === "focus") {
        this.active = true;
      } else {
        this.active = false;
      }
    },
    show() {
      let input = document.querySelector("#" + this.name);
      if (input.type === "password") {
        input.type = "text";
      } else if (input.type === "text") {
        input.type = "password";
      }
    },
  },
};
</script>

<style scoped>
.base-container {
  position: relative;
}

.base-input {
  position: relative;
  z-index: 2;
  margin-bottom: 20px;
  width: 100%;
  display: block;
  border: none;
  padding: 5px 0;
  border-bottom: solid 1px var(--bg-border);
  transition: all 0.3s cubic-bezier(0.64, 0.09, 0.08, 1);
  background: linear-gradient(to bottom, var(--bg) 96%, var(--bg-list) 96%);
  background-position: -1920px 0;
  background-size: 100%;
  background-repeat: no-repeat;
  font-size: 14px;
  font-weight: 500;
  color: var(--second-color);
}

.base-input:focus {
  background-position: 0 0;
  box-shadow: none;
  outline: 0;
}

.base-label {
  color: var(--bg-stroke);
  font-size: 14px;
  font-weight: 500;
  transition: all 0.3s cubic-bezier(0.64, 0.09, 0.08, 1);
  margin: 10px 0 10px;
  display: inline-block;
  transform: translateY(-5px);
  position: absolute;
  text-align: left;
}

.is-Active {
  transform: translateY(-20px);
  font-size: 10px;
}

.eye {
  position: absolute;
  width: 13.12%;
  top: 0;
  right: 15px;
  z-index: 100;
}
</style>
