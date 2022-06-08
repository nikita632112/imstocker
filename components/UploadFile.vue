<template>
  <div>
    <input id="dropzone" ref="dropzoneFile" type="file" accept="image/*" @change="handleFile"/>
    <v-card @drop.prevent="handleFile" @dragenter.prevent="" @dragover.prevent="">
      <label for="dropzone">
        <div>
          <v-card-text>Переместите файл в эту область или нажмите кнопку ниже:</v-card-text>
          <v-btn>Выберите файл</v-btn>
        </div>
      </label>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "UploadFile",
  data() {
    return {
      files: []
    }
  },
  methods: {
    handleFile(e)
    {
      const inputValue = e.target.files || e.dataTransfer.files || this.$refs.dropzoneFile.files
      console.log(inputValue)
      this.files.push(inputValue[0].name)
      console.log(this.files)
      this.$emit('modelValue', this.files)
    }
  }
}
</script>

<style scoped>
input[type="file"]{
  display: none;
}
</style>
