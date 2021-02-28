<template>
  <div>
    <div v-for="(roop , index) in roops" :key="index">
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
          {{roop.note}}
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
              
                <v-btn
                    color="red lighten-2"
                    dark
                    @click="dialogload(index)"
                >click me</v-btn>
            </v-row>
          </v-list-item>
        </v-card-actions>
      </v-card>
    </div>
    <span class="subheading">45</span>
    <v-dialog
        v-model="dialog"
        width="500"
      >
      <v-card>
            <v-card-title class="headline grey lighten-2">
            Privacy Policy
            </v-card-title>
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
                @click="agree(datatestchild,roopnumber)"
            >
                I accept
            </v-btn>
            </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
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

    roopnumber: number =0


    roops:any = [
      {
        note:"フロントエンド",
      },
      {
        note:"バックエンド",
        
      },
      {
        note:"データベース",
      }
    ]
    



    agree(test:string,test2:number){
        window.confirm(test)
        this.dialog = false
        this.roops[test2].note = test
        
    }
    dialogload(index:number){
      window.alert(index)
      this.dialog = true
      this.roopnumber = index
      this.datatestchild = this.roops[index].note
    }

    
    res(obj:any){
      this.datatest = obj.datatestchild
    }

    close(obj:any){
      this.datatest = obj.datatestchild
    }
}
</script>