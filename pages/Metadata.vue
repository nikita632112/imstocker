<template>
  <div>
    <upload-file v-model="files" @modelValue="modelValue"></upload-file>
    <v-card-text>{{ files }}</v-card-text>
  </div>
</template>

<script>
import UploadFile from "~/components/UploadFile";
export default {
  name: "Metadata",
  components:{
    UploadFile
  },
  data () {
    return {
      files: []
    }
  },
  methods: {
    modelValue(title) {
      this.files = title
    }
  }
}
</script>

<style scoped>

</style>
