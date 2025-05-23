<template>
  <docs-page-layout :title="$options.title" :description="$options.description" :status="$options.status">
    <template v-for="(demo, i) in demos">
      <docs-card-vue :title="demo.title" :description="demo.description" :file="demo.file" :id="demo.id" />
    </template>
    <template #api>
      <getting-started :package-name="$options.packageName" :component-name="$options.componentName" />
      <docs-all-api :api-data="$options.apiData" />
    </template>
  </docs-page-layout>
</template>

<script>
import DocsPageLayout from '@/components/docs-card/DocsPageLayout.vue';
import DocsCardVue from '@/components/docs-card/DocsCardVue.vue';
import DocsCard from '@/components/docs-card/DocsCard.vue';
import GettingStarted from '@/components/docs-card/GettingStarted.vue';
import DocsAllApi from '@/components/docs-card/DocsAllApi.vue';
import CheckboxAPI from 'lightvueDocs/example/checkbox/CheckboxAPI';

const pageMeta = {
  title: ' RadioGroup Docs | LightVue ',
  meta: [
    { charset: 'utf-8' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { property: 'og:title', content: 'LightVue' },
    { property: 'og:image', content: 'https://lightvue.com/og-img.png' },
    {
      property: 'og:site_name',
      content: ' RadioGroup Docs | LightVue ',
    },
    {
      property: 'og:description',
      content: 'RadioGroup component can be used when user needs to select or deselect options from a given array of options.',
    },
  ],
  link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }],
};
export default {
  head: pageMeta,
  setup() {
    useHead(pageMeta);
  },
  data() {
    return {
      demos: [
        {
          title: 'Basic',
          file: 'radio-group/RadioGroupDemo_Basic',
          description: 'You can pass the <span>options</span> in <span>lv-checkbox-group</span> as an array of objects. You can still use all the props and variations in the <span>LvCheckbox</span>. LightVue radio-group is Both compatible with Vue 2.x and Vue 3.x',
        },
        {
          title: 'Set option value',
          file: 'radio-group/RadioGroupDemo1',
          description: 'You can set the option value and label through <sapn>optionValue</sapn> and <span>optionLabel</span> respectively',
        },
        {
          title: 'Array of strings',
          description: 'You can also use array of strings for options',
          file: 'radio-group/RadioGroupDemo2',
        },
        {
          title: 'Preselect Value',
          description: 'You can set the value selected by default by setting it as an <span>v-model</span> value',
          file: 'radio-group/RadioGroupDemo3',
        },
      ],
    };
  },
  components: {
    DocsCardVue,
    DocsCard,
    GettingStarted,
    DocsPageLayout,
    DocsAllApi,
  },
  title: 'Radio Group',
  description: `LvRadioGroup component can be used when user needs to select or deselect options from a given array of options.`,
  packageName: 'radio-group',
  componentName: 'LvRadioGroup',
  // status: 'Stable',
  apiData: CheckboxAPI,
};
</script>
