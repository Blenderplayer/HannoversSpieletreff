<template>
    <div class="f_Events h-100 position-relative">
        <Event
            class="pb-4"
            src="werwolf.jpg"
            title="Werwolf"
            description="Die Nacht erwacht, die Wölfe heulen und das Dorf erbost. Diese Plage muss ausgelöscht werden!"
            nextDates="Nächste Spielrunde: 21.11.2023, 19.12.2023"
        />
        <Event
            class="pb-4"
            src="OnePieceTcg.png"
            title="One Piece TCG"
            description="Ruhm, Macht, Reichtum. Der Mann, der sich dies alles erkämpfte war Goldroger. Und auch du kannst Hannovers Gold Roger werden!"
            nextDates="Nächstes Treffen: 07.11.2023, 21.11.2023"
        />
        <Event
            src="PenAndPaper.png"
            title="Pen and Paper"
            description="Erstellt euren Charakter und stürtzt euch in allerlei Abenteuer. Egal, ob Fantasy, Krimi oder Scifi. Hier wird alles gespielt."
            nextDates="Nächste Oneshots: "
        />
    </div>
</template>

<script>
import Event from "@/components/Event";
export default {
  name: "f_Events",
    components: {Event},
    emits: [],
  props: {},
  created(){},
  mounted(){},
  data(){
    return {
        
    }
  },
  computed: {},
  methods: {},
}
</script>

<style scoped>
.f_Events{
}
</style>