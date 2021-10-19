<template>
  <indentation />{{ name }}: [<br><slot /><indentation />],<br>
</template>

<script>
import Indentation from "components/Indentation";
export default {
  name: "subObj",
  components: { Indentation },
  props: ['name'],
}
</script>
