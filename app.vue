<script setup>
import "@nordhealth/components/lib/Layout";
import "@nordhealth/components/lib/CommandMenu";

import { useI18n } from "vue-i18n";

const i18n = useI18n();

useHead({
  htmlAttrs: {
    lang: i18n.locale,
    dir: () => {
      return i18n.locale.value === "he" ? "rtl" : "ltr";
    },
  },
});
</script>

<template>
  <nord-layout>
    <PrimaryNavigation />
    <PageHeader />
    <NuxtPage />
    <nord-command-menu></nord-command-menu>
  </nord-layout>
</template>

<style>
:not(:defined) {
  visibility: hidden;
}

body {
  background-color: var(--n-color-background);
  color: var(--n-color-text);
  margin: 0;

  font-size: var(--n-font-size-m);
  font-family: var(--n-font-family);
  line-height: var(--n-line-height);
}

/* Nav account button */
.account-button {
  --n-button-text-align: start;
  --_n-button-padding-inline: calc(var(--n-space-s) / 2);
  --_n-button-color: var(--n-color-text-weak);
  --_n-button-background-color: transparent;
}
.account-button:hover {
  --n-button-border-color: var(--n-color-border-hover);
}
/* Nav header prototype */
.has-logo nord-icon {
  display: none;
}
.has-logo .n-clinic-img {
  opacity: 1;
  visibility: visible;
}
.has-logo .n-clinic-name,
.has-logo .n-clinic-icon {
  opacity: 0;
  visibility: hidden;
}
.n-clinic-img {
  max-width: calc(100% - var(--n-space-xl) - var(--n-space-s));
  width: calc(100% - var(--n-space-xl) - var(--n-space-s));
  opacity: 0;
  visibility: hidden;
  position: absolute;
  margin-left: calc(var(--n-space-s) / 1.2);
  background: transparent;
  height: 100%;
  background-position: 0 50%;
  background-repeat: no-repeat;
  background-size: 60% auto;
}
.n-logo-contents,
.n-clinic-name {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  vertical-align: middle;
}
.n-clinic-name {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-width: 100%;
  display: inline-block;
}
.n-clinic-icon {
  background-repeat: no-repeat;
  background-size: contain;
  background-position: 50% 50%;
}
/* Responsive settings */
@media (max-width: 550px) {
  .filter {
    display: none;
  }
}
@media (max-width: 450px) {
  .export {
    display: none;
  }
}
@media (max-width: 370px) {
  .new {
    display: none;
  }
}
[data-action="delete"] span,
[data-action="delete"] nord-icon {
  color: var(--n-color-text-error);
}
</style>
