<script>
import { inject, computed, useSlots } from 'vue'

export default {
  props: {
    limit: {
      type: Number,
      default: 2
    }
  },
  setup(props) {
    const slots = useSlots()
    const expandable = inject('expandable')

    const children = computed(() => {
      return slots.default ? slots.default() : []
    })

    return () => {
      const allChildren = children.value
      const isExpanded = expandable.isExpanded.value
      const limit = props.limit
      
      return allChildren.filter((child, index) => {
        return index < limit || isExpanded
      })
    }
  }
}
</script>
