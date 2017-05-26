<template>
  <input type="hidden">
</template>

<script>
  export default {
    props: {
      url: {
        required: true
      }
    },
    data() {
      return {
        uploadcareUrl: ""
      }
    },
    mounted() {
      this.initWidget();
    },
    watch: {
      uploadcareUrl() {
        this.updatePropUrl();
      }
    },
    methods: {

      initWidget() {
        const widget = uploadcare.Widget(this.$el);
        this.url && widget.value(this.url);

        widget.onUploadComplete((info) => {
          this.uploadcareUrl = info.cdnUrl;
        });
      },
      
      updatePropUrl() {
        this.$emit('update:url', this.uploadcareUrl);
      }
    }
  };
</script>