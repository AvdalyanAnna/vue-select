<template>
  <div class="app">
    <div class="wrapper">
      <div class="row mt-4">
        <div class="col-4">
          <div class="form-item" :class="{open:isOpen || selectVal.length > 0}">
            <div class="form-label">
              Адрес
            </div>
            <div v-if="selectVal.length > 0" class="vs__clear" @click="selectVal = ''"></div>
            <v-select v-model="selectVal" :options="options" @open="isOpen = true" @close="isOpen = false"
                      :clearable="false">
              <template #open-indicator="{ attributes }">
              <span v-bind="attributes">
                <svg width="10" height="5" viewBox="0 0 10 5" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M0 0L5 5L10 0H0Z" fill="#5F6368"/>
                </svg>
              </span>
              </template>
            </v-select>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>

export default {
  name: "Home",
  data() {
    return {
      selectVal: '',
      isOpen: false,
      attributes: {
        'ref': 'openIndicator',
        'role': 'presentation',
        'class': 'vs__open-indicator',
      },
      options: [
        'Невский проспект, 44 лит.А',
        'Невский проспект, 45 лит.А',
        'Невский проспект, 46 лит.А',
        'Невский проспект, 47 лит.А'
      ]
    }
  }
};
</script>