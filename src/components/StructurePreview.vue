<template>
	<div class="k-structure-field-preview">
        <div class="structure-entries-preview" v-html="entriesString"></div>
    </div>
</template>

<script>
export default {
    props: {
        value: String,
    },
    computed: {
    	entriesCount() {
            return this.value
        },
        entriesString() {
            console.log(this.entriesCount)
						if (this.entriesCount[0].text) {
							return (
								this.entriesCount[0].text + "<br><br>" + "TYPE: " + this.entriesCount[0].width
							)
						}

						if (this.entriesCount[0].image) {
							return (
								'<img style="width: 100%;" src=' + this.entriesCount[0].image[0].icon.url + '/> <br> TYPE: ' + this.entriesCount[0].width
							)
						}
						if (this.entriesCount[0].videourl) return this.entriesCount[0].videourl

        }
    },
    methods: {
        entryString(n) {
            return n == 1 ? ' entry' : ' entries'
        }
    }
};
</script>
