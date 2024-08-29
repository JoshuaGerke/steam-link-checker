<script setup lang="ts">
import { ref } from "vue";

const officialLinks = [
  "store.steampowered.com",
  "steamcommunity.com",
  "help.steampowered.com",
  "steamcommunity.com/workshop"
];

const scamLinks = [
  "store.steampowered.co",
  "store.steamp0wered.com",
  "st0re.steampowered.com",
  "store.steamcommunity.com",
  "store.steampowered.net",
  "store.steampowered.info",
  "store.steampowered.store",
  "store.steamcommunity.net",
  "st0re.steamp0wered.com",
  "store.steamcommnity.com",
  "store.steampowered.c0m",
  "st0re.steampowered.com",
  "sto-re.steampowered.com",
  "store.steamc0mmunity.com",
  "store.steamp0wered.org",
  "store-steampowered.com",
  "store.steampowered.cm",
  "sto-re.steampowered.com",
  "store.steampowered.c0m",
  "steampowered-store.com",
  "st0re.steampowered.co",
  "store.steampowered.site",
  "store.steampow3red.com",
  "store.steampowered.co.uk",
  "store.steamcommnity.com",
  "steampowered.com",
  "steampowered.co",
  "steamcommunity-help.com",
  "store.steampowered1.com",
  "store-steampowered.com",
  "store.steamc0mmunity.com",
  "store.steampowered.store",
  "steamcommuni†y.com",
  "steamcommunl†y.com",
  "steampowered.support",
  "steamp0wered.com",
  "store.steamc0mmunity.com",
  "store.steam-community.com",
  "st0re.steampowered.com",
  "st0re.steampowered.co",
  "ste4mpowered.com",
  "store.steamcommnity.com",
  "store.steampowered.com/uk",
  "store.steampowered.c0m",
  "sto-re.steampowered.com",
  "store.steamcommunitv.com",
  "st0re.steamcommunitv.com",
  "sto-re.steampowered.net",
  "store.steampowered.com.free",
  "store.steampowered.com123",
  "store.steampowered.co",
  "store.steamcommnity.com",
  "store.steamcommunity.co",
  "store.steampowered.co.uk",
  "store.steampowered.store",
  "sto-re.steampowered.com",
  "steampowered-support.com",
  "steampowered.st0re.com",
  "store.steampowered.support",
  "sto-re.steampowered.com",
  "steampowered.st0re.com",
  "store.steamcommuni†y.com",
  "store.steampowered1.com",
  "steampowered-1.com",
  "store.steampowered.store",
  "steampowered.com",
  "store.steampowered.mobi",
  "sto-re.steampowered.org",
  "store.steampowered1.com",
  "steampowered.co",
  "st0re.steampowered.org",
  "store.steampowered.site",
  "st0re.steampowered.store",
  "store.steampowered.com/fake",
  "sto-re.steampowered.co",
  "store.steampowered.com/uk",
  "steamp0wered.com",
  "store.steampowered.mobi",
  "store.steampowered1.com",
  "store.steampowered.online",
  "sto-re.steampowered.store",
  "ste4ampowered.com",
  "store.steampowered.gq",
  "st0re.steampowered.com",
  "store.steampowered.xyz",
  "sto-re.steampowered.com",
  "store.steampowered.us",
  "store.steampowered.vip",
  "steamc0mmunity.com",
  "steampowered1.com",
  "steampowered-1.com",
  "steampowered-support.com",
  "steampowered-help.com",
  "steampowered-store.com",
  "steamcommunity-help.com",
  "steamc0mmunity.net",
  "steamc0mmunity.org",
  "steamcommuni†y.co",
  "steamcommunity.net.co",
  "steamp0wered.net",
  "steamp0wered.org",
  "steamp0wered.info",
  "steampowered1.net",
  "steampowered.site",
  "steampowered.store",
  "steamcommunity1.com"
];

const testLink = ref('');

function normalizeUrl(url) {
  return url.replace(/^(https?:\/\/)?/, '').toLowerCase();
}

const checkLink = (url) => {
  const normalizedUrl = normalizeUrl(url);
  if (officialLinks.includes(normalizedUrl)) {
    return 'This link is official and safe! 😍';
  } else if (scamLinks.includes(normalizedUrl)) {
    return 'This link is a scam! ❌';
  } else {
    return 'This link is unknown and potentially a scam! ⚠️';
  }
};

</script>

<template>
  <div class="bg-[#171d25] absolute left-0 right-0 h-[8rem]">
    <div class="text w-full text-center !text-3xl !text-white">Steam URL Checker</div>
  </div>
  <div class="card absolute top-1/2 left-1/2 -translate-y-1/2 -translate-x-1/2 p-4 flex flex-wrap pb-14 px-10">
    <div class="text w-full text-center !text-2xl !text-white mb-1">Enter the link</div>
    <div class="w-full text-center mb-4 text-white opacity-25">Enter a link, and we will check if it is official or a scam.</div>
    <input v-model="testLink" class="text-white p-2" placeholder="Enter URL"/>
    <div class="w-full text-center text-3xl mt-8 text-white" v-if="testLink">
      <div>{{ checkLink(testLink) }}</div>
    </div>
  </div>
  <div class="">Steam Link Checker is not affiliated with or endorsed by Steam, Valve or any other rights holder. All the used trademarks belong to their respective owners.</div>
  <div class="absolute bottom-0 left-1/2 -translate-x-1/2 text-white opacity-10 text-center">made with ♥ by <a href="https://joshua-gerke.de" target="_blank">Joshua Gerke</a> | <a target="_blank" href="https://joshua-gerke.de/imprint">Imprint</a></div>
</template>
