<template>
  <indentation /><slot />,<br>
</template>

<script>
import Indentation from "components/Indentation";
export default {
  name: "IndentedLine",
  components: { Indentation },
}
</script>
