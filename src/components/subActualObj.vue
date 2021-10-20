<template>
  <indentation /><indentation />{<br><slot /><indentation /><indentation />},<br>
</template>

<script>
import Indentation from "components/Indentation";

export default {
  name: "subActualObj",
  components: { Indentation }
}
</script>

<style scoped>

</style>
