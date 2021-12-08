<template>
  <div>
    <v-row class="mb-6">
      <v-toolbar flat class="page-toolbar py-3">
        <v-row justify="center" class="mx-0">
          <v-col cols="12" sm="" class="d-flex align-center">
            <h1 class="text-h5">Load chat</h1>
            <v-spacer></v-spacer>
          </v-col>
        </v-row>
      </v-toolbar>
    </v-row>

    <v-card>
      <v-card-text>
        <v-form autocomplete="off">
          <v-row>
            <v-col cols="12" sm="8">
              <v-text-field
                  v-model="chatID"
                  label="Chat ID"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row>
            <v-btn
                id="load-chat-confirm"
                color="accent"
                @click="onLoadChat"
            >
              Load
            </v-btn>
          </v-row>
        </v-form>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>

import $ from 'jquery'

export default {
  name: 'LoadChat',
  data() {
    return {
      chatID: ''
    };
  },
  methods: {
    async onLoadChat(event) {
      event.preventDefault();

      const chatId = this.chatID;

      $.getJSON("chats.json", function(chats) {
        const chatsArr = JSON.parse(chats);

        const chat = chatsArr.find(chat => chat.chatID === chatId);
        console.log(JSON.stringify(chat));
      });
    },
  },
};
</script>
