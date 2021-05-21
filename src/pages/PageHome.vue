<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input
          bottom-slots
          class="new-whisper"
          v-model="newWhisperContent"
          placeholder="What's happening?"
          counter
          maxlength="280"
          autogrow
        >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="https://cdn.quasar.dev/img/avatar5.jpg" />
            </q-avatar>
          </template>
        </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn
          class="q-mb-lg"
          unelevated
          rounded
          color="primary"
          label="Whisper"
          no-caps
          :disable="!newWhisperContent"
        />
      </div>
    </div>
    <q-separator class="divider" size="10px" color="grey-2" />

    <q-list separator>
     <q-item
        v-for="whisper in whispers"
        :key="whisper.date"
        class="q-py-md">
        <q-item-section avatar top>
          <q-avatar size="xl">
            <img src="https://cdn.quasar.dev/img/avatar5.jpg" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong>Miss Kiwi</strong>
            <span class="text-grey-7"> @kiwii </span>
          </q-item-label>
          <q-item-label class="whisper-content text-body1"
            >{{whisper.content}}.
          </q-item-label>

          <div class="whisper-icon row justify-between q-mt-sm">
            <q-btn flat round color="grey" size="sm" icon="far fa-comment" />
            <q-btn flat round color="grey" size="sm" icon="fas fa-retweet" />
            <q-btn flat round color="grey" size="sm" icon="far fa-heart" />
            <q-btn flat round color="grey" size="sm" icon="fas fa-trash" />
          </div>
        </q-item-section>

        <q-item-section side top>{{whisper.date}}</q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: "PageHome",
  data() {
    return {
      newWhisperContent: "",
      whispers: [
        {
          content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic commodi repellendus incidunt accusamus quaerat, voluptate quae consequuntur temporibus quas omnis id aperiam maiores recusandae nobis aliquid exercitationem iure doloribus quia.',
          date: 1621374645813
        },
        {
          content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic commodi repellendus incidunt accusamus quaerat, voluptate quae consequuntur temporibus quas omnis id aperiam maiores recusandae nobis aliquid exercitationem iure doloribus quia.',
          date: 1621374693413
        }
      ]
    };
  },
};
</script>

<style lang="sass">
.new-whisper
  textarea
    font-size: 19px
    line-height: 1.4 !important
.divider
  border-top: 1px solid
  border-bottom: 1px solid
  border-color: $grey-4
.whisper-content
  white-space: pre-line
.whisper-icon
 margin-left: -5px
</style>
