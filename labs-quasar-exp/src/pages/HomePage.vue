<template>
  <q-page class="">
    <div class="q-py-lg q-px-lg">
      <div class="input-container">
        <q-input bottom-slots v-model="newTweetContent" placeholder="Anything to share today?" counter maxlength="300" autogrow >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="/avatars/avatar.png">
            </q-avatar>
          </template>

          <template v-slot:after>
            <q-btn unelevated rounded color="blue" no-caps label="Tweeter" :disable="!newTweetContent" />
          </template>
        </q-input>
      </div>
      <div>
        <q-list bordered class="tweet-container" style="margin-top: 1rem">
          <q-item-label header class="text-h6 text-black text-weight-bold q-pb-xs">Community Feed</q-item-label>
          <q-item clickable v-ripple class="q-mt-md">
            <q-item-section avatar top>
              <q-avatar size="xl">
                <img src="/avatars/avatar2.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>
                <strong>Dr. Maxime LOUMBERG</strong>
                <span class="q-ml-xs text-gray-7" style="color: #475569">@doctorloumberg</span>
              </q-item-label>
              <q-item-label lines="1" class="q-pt-xs text-weight-medium q-mb-sm">Usage of Creative</q-item-label>
              <q-item-label caption lines="4" class="text-weight-medium q-mb-sm">
                Creatine monohydrate is a widely researched and popular supplement known for its effectiveness in enhancing athletic performance and muscle growth. It works by increasing the phosphocreatine stores in muscles, which helps produce more ATP, the primary energy currency of the body during high-intensity exercise. Numerous studies have shown that creatine monohydrate can improve strength, increase lean muscle mass, and accelerate recovery after intense workouts. Additionally, it is considered safe for long-term use, with minimal side effects reported when taken in recommended dosages. This makes it a staple in the supplement regimen of many athletes and fitness enthusiasts aiming to optimize their training results.
              </q-item-label>
              <div class="row">
                <q-btn flat round color="grey" size="sm" icon="comment" />
                <q-btn flat round color="grey" size="sm" icon="repeat" />
                <q-btn flat round color="red" size="sm" icon="favorite" />
                <q-btn flat round color="grey" size="sm" icon="delete" />
              </div>
            </q-item-section>
            <q-item-section side top>
              5h ago
            </q-item-section>
          </q-item>
          <q-separator inset="item" />
          <q-item clickable v-ripple class="q-mt-md">
            <q-item-section avatar top>
              <q-avatar size="xl">
                <img src="/avatars/avatar3.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>
                <strong>Dr. Alexender Young</strong>
                <span class="q-ml-xs text-gray-7" style="color: #475569">@dralexenderyoung</span>
              </q-item-label>
              <q-item-label lines="1" class="q-pt-xs text-weight-medium q-mb-sm">The importance of not skipping cardio</q-item-label>
              <q-item-label caption lines="4" class="text-weight-medium q-mb-sm">
                Cardiovascular exercise, often simply referred to as cardio, plays a crucial role in maintaining overall health and fitness. Regular cardio workouts, such as running, cycling, or swimming, are essential for improving heart health, increasing lung capacity, and enhancing endurance. Skipping cardio can lead to a decrease in cardiovascular efficiency, which may result in reduced stamina and higher susceptibility to heart-related diseases. Additionally, incorporating cardio into a fitness routine helps with weight management by burning calories and boosting metabolism. It also promotes mental well-being by releasing endorphins, which can alleviate stress and improve mood. Therefore, to achieve a balanced fitness regimen and enjoy the numerous health benefits, it is important not to overlook the significance of regular cardio sessions.
              </q-item-label>
              <div class="row">
                <q-btn flat round color="grey" size="sm" icon="comment" />
                <q-btn flat round color="grey" size="sm" icon="repeat" />
                <q-btn flat round color="grey" size="sm" icon="favorite" />
                <q-btn flat round color="grey" size="sm" icon="delete" />
              </div>
            </q-item-section>
            <q-item-section side top>
              1h ago
            </q-item-section>
          </q-item>
          <q-separator inset="item" />
          <q-item clickable v-ripple class="q-mt-md">
            <q-item-section avatar top>
              <q-avatar size="xl">
                <img src="/avatars/avatar4.png">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>
                <strong>Alexender DELACROIX</strong>
                <span class="q-ml-xs text-gray-7" style="color: #475569">@alxdr.delacroix</span>
              </q-item-label>
              <q-item-label lines="1" class="q-pt-xs text-weight-medium q-mb-sm">PSG vs OM ?</q-item-label>
              <q-item-label caption lines="4" class="text-weight-medium q-mb-sm">
                Le match tant attendu entre le Paris Saint-Germain (PSG) et l'Olympique de Marseille (OM) a captivé les amateurs de football du monde entier. Cette rencontre épique entre deux des plus grandes équipes du championnat français a été marquée par une intense rivalité et une passion débordante sur le terrain. Les joueurs ont livré un spectacle palpitant, avec des attaques rapides, des dribbles habiles et des arrêts spectaculaires. Chaque action était scrutée avec attention par les supporters enfiévrés des deux camps, créant une atmosphère électrique dans le stade. Finalement, c'est le PSG qui a réussi à s'imposer dans ce duel mémorable, laissant les fans parisiens exulter de joie tandis que les supporters marseillais se projettent déjà vers le prochain affrontement, animant ainsi cette rivalité légendaire qui perdure depuis des décennies.
              </q-item-label>
              <div class="row">
                <q-btn flat round color="grey" size="sm" icon="comment" />
                <q-btn flat round color="green" size="sm" icon="repeat" />
                <q-btn flat round color="grey" size="sm" icon="favorite" />
                <q-btn flat round color="grey" size="sm" icon="delete" />
              </div>
            </q-item-section>
            <q-item-section side top>
              5h ago
            </q-item-section>
          </q-item>
        </q-list>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      newTweetContent: ''
    }
  }
}
</script>
<style>
.input-container {
  border-radius: 0.75rem; /* rounded-xl */
  background-color: #ffffff; /* bg-slate-50 */
  border: 2px solid #cbd5e1; /* border-2 border-slate-300 */
  padding-left: 1.75rem; /* px-3 */
  padding-right: 1.75rem; /* px-3 */
  padding-top: 1rem; /* py-1.5 */
  padding-bottom: 0.5rem; /* py-1.5 */
}

.tweet-container {
  border-radius: 0.75rem; /* rounded-xl */
  background-color: #ffffff; /* bg-slate-50 */
  border: 2px solid #cbd5e1; /* border-2 border-slate-300 */
  padding-left: 1.75rem; /* px-3 */
  padding-right: 1.75rem; /* px-3 */
  padding-top: 1rem; /* py-1.5 */
  padding-bottom: 1rem; /* py-1.5 */
}
</style>
