<template>
    <div>
        <h3>Quotes Added</h3>

        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="70"
            aria-valuemin="0" aria-valuemax="100"
            :style="{width: (quotesCount / maxQuotes) * 100 + '%'}">
            {{ quotesCount }} / {{ maxQuotes }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quotesCount', 'maxQuotes'],
    }
</script>