<script lang="ts">
import { h, provide, computed, readonly, watch } from 'vue';
import { createComponent } from '@/packages/utils/create';
import { RADIO_KEY } from '../radio/types';
const { componentName, create } = createComponent('radio-group');

export default create({
  props: {
    modelValue: {
      type: [Number, String, Boolean],
      default: ''
    },
    direction: {
      type: String,
      default: 'vertical' //horizontal
    },
    textPosition: {
      type: String,
      default: 'right'
    }
  },
  emits: ['change', 'update:modelValue'],
  setup(props, { emit, slots }) {
    const updateValue = (value: string | boolean | number) => emit('update:modelValue', value);

    provide(RADIO_KEY, {
      label: readonly(computed(() => props.modelValue)),
      position: readonly(computed(() => props.textPosition)),
      updateValue
    });

    watch(
      () => props.modelValue,
      (value) => emit('change', value)
    );

    return () => {
      return h(
        'view',
        {
          class: `${componentName} ${componentName}--${props.direction}`
        },
        slots.default?.()
      );
    };
  }
});
</script>
