<template>
    <div id="app" class="container mt-3 mb-5">
        <h2>Country Table</h2>
        <b-row class="mb-3">
            <b-col md="3">
                <b-from-input></b-from-input>
            </b-col>
        </b-row>

        <b-row>
            <b-col>
                <b-table
                striped
                hover
                outlined
                :items="items"
                :fields="fields"
                :filter="filetr"
                :current-page="currentPage"
                :per-page="perPage"
                :filter-included-fields="['name', 'capital', 'region']"
                >

                </b-table>
            </b-col>
        </b-row>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>