<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes added</h3>
            <div class="progress">
            <div class="progress">
                <div class="progress-bar" role="progress-bar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
                :style="{width: (quoteQount / maxQuotes) * 100 + '%'}">
                    {{ quoteQount }} / {{ maxQuotes }} 
                </div>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:[
            'quoteQount', 'maxQuotes'
        ]
    }
</script>

<style scoped>

</style>