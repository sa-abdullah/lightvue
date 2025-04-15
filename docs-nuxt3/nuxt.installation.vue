<template>
  <div>
    <div class="content-section introduction">
      <div class="feature-intro">
        <h1>Installation (Nuxt 3)</h1>
        <p style="opacity: 0.8">
          To use LightVue in a Nuxt 3 project, start by installing Nuxt, then add LightVue and its dependencies.
        </p>
      </div>
    </div>
    <br />

    <div class="content-section implementation">
      <docs-card title="Create a Nuxt 3 Project" :showCardActions="false" :responsive="false">
        <div class="install__wrapper" style="padding: 1rem">
          <div class="install__container">
            <div class="install__process">
              <CodeHighlight lang="bash">
                <pre>
npx nuxi init my-app
cd my-app
npm install
                </pre>
              </CodeHighlight>
            </div>
          </div>
        </div>
      </docs-card>
    </div>

    <div class="content-section implementation">
      <docs-card title="Install LightVue" :showCardActions="false" :responsive="false">
        <div class="install__wrapper" style="padding: 1rem">
          <div class="install__container">
            <div class="install__process">
              <CodeHighlight lang="bash">
                <pre>
npm install lightvue@next
# OR
yarn add lightvue@next
                </pre>
              </CodeHighlight>
            </div>
          </div>
        </div>
      </docs-card>
    </div>

    <div class="content-section implementation">
      <docs-card title="Register LightVue Plugin" :showCardActions="false" :responsive="false">
        <div class="install__wrapper" style="padding: 1rem">
          <div class="install__container">
            <p style="opacity: 0.8">
              Create a file in the <code>plugins/</code> directory named <code>lightvue.client.ts</code>:
            </p>
            <div class="install__process">
              <CodeHighlight lang="ts">
                <pre>
import { defineNuxtPlugin } from '#app'
import LightVue from 'lightvue'

export default defineNuxtPlugin((nuxtApp) => {
  nuxtApp.vueApp.use(LightVue)
})
                </pre>
              </CodeHighlight>
            </div>
          </div>
        </div>
      </docs-card>
    </div>

    <div class="content-section implementation">
      <docs-card title="Add LightVue Styles" :showCardActions="false" :responsive="false">
        <div class="install__wrapper" style="padding: 1rem">
          <div class="install__container">
            <p style="opacity: 0.8">
              Include LightVue’s global styles in your <code>nuxt.config.ts</code>:
            </p>
            <div class="install__process">
              <CodeHighlight lang="ts">
                <pre>
export default defineNuxtConfig({
  css: ['lightvue/dist/lightvue.css']
})
                </pre>
              </CodeHighlight>
            </div>
          </div>
        </div>
      </docs-card>
    </div>

    <div class="content-section implementation">
      <docs-card title="Step 5: Use LightVue Components" :showCardActions="false" :responsive="false">
        <div class="install__wrapper" style="padding: 1rem">
          <div class="install__container">
            <p style="opacity: 0.8">
              You can now use LightVue components like buttons or inputs directly:
            </p>
            <div class="install__process">
              <CodeHighlight lang="vue">
                <pre>
<template>
  <LvButton label="Click Me" />
</template>
                </pre>
              </CodeHighlight>
            </div>
          </div>
        </div>
      </docs-card>
    </div>
  </div>
</template>

<script setup>
import DocsCard from '@/components/docs-card/DocsCard';
import CodeHighlight from '@/components/docs-card/CodeHighlight.vue';
</script>
