<template>
 
  <v-card
    class="mx-auto"
    color="#26c6da"
    dark
    max-width="400"
  >
    <v-card-title>
      <v-icon
        large
        left
      >
        mdi-twitter
      </v-icon>
      <span class="title font-weight-light">Twitter</span>
    </v-card-title>

    <v-card-text class="headline font-weight-bold">
      {{datatest}}
    </v-card-text>

    <v-card-actions>
      <v-list-item class="grow">
        <v-list-item-avatar color="grey darken-3">
          <v-img
            class="elevation-6"
            alt=""
            src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
          ></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>Evan You</v-list-item-title>
        </v-list-item-content>

        <v-row
          align="center"
          justify="end"
        >
          <v-icon class="mr-1">
            mdi-heart
          </v-icon>
          <span class="subheading mr-2">256</span>
          <span class="mr-1">·</span>
          <v-icon class="mr-1">
            mdi-share-variant
          </v-icon>
          <span class="subheading">45</span>
          <v-dialog
            v-model="dialog"
            width="500"
          >
          <template v-slot:activator="{ on, attrs }">
            <v-btn
                color="red lighten-2"
                dark
                v-bind="attrs"
                v-on="on"
                @click="dialogload"
                @closetest="res"
            >click me</v-btn>
          </template>
          <v-card>
                <v-card-title class="headline grey lighten-2">
                Privacy Policy
                </v-card-title>

                <v-card-text>
                 {{datatest}}
                </v-card-text>
                    <v-textarea
                    name="input-7-1"
                    label="Default style"
                    :value=datatestchild
                    hint="Hint text"
                    v-model="datatestchild"
                    ></v-textarea>
                <v-divider></v-divider>

                <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                    color="primary"
                    text
                    @click="agree(datatestchild)"
                >
                    I accept
                </v-btn>
                </v-card-actions>
            </v-card>
            </v-dialog>
        </v-row>
      </v-list-item>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
   },
})
export default class Home extends Vue {

    dialog: boolean =  false
    datatest: string = "test."
    datatestchild: string =""
    agree(test:string){
        window.confirm(test)
        this.dialog = false
        this.datatest = test
        
    }
    dialogload(){
       this.datatestchild = this.datatest 
    }

    
    res(obj:any){
    }

    close(obj:any){
    }
}
</script>