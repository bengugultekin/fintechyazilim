<template>
    <div id="app" class="container mt-3 mb-5">
        <h2>Country Table</h2>
        <b-row class="mb-3">
            <b-col md="3">
                <b-form-input v-model="filter" type="search" id="filterInput" placeholder="Type to Search"></b-form-input>
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
                :filter="filter"
                :current-page="currentPage"
                :per-page="perPage"
                :filter-included-fields="['name', 'capital', 'region']"
                >

                <template #cell(index)="data">
                    {{data.index + 1 }}
                </template>

                <template #cell(imgflag)="data">
                    <img :src="data.item.flag" width="40" height="30"/>
                </template>
                </b-table>

                <b-pagination
                v-model="currentPage"
                :total-rows="rows"
                :per-page="perPage"
                aria-controls="my-table"
                ></b-pagination>
            </b-col>
        </b-row>
    </div>
</template>

<script>

import axios from 'axios';
    export default {
        data() {
            return {
                filter: "",
                items:[],
                perPage: 10,
                currentPage: 1,
                fields: ['index', 'name', 'capital', 'region', {key:'imgflag', label:'Flag'} ],
                rows:0
            }
        },
        // Fetches posts when the components is created.
        created() {
            axios.get(`https://restcountries.eu/rest/v2/all`)
            .then(
                response => {
                // JSON responses are automatically parsed.
                this.items = response.data;
                this.fields = ['index', 'name', 'capital', 'region', {key:'imgflag', label:'Flag'} ];
                this.rows = response.data.length
            })
            .catch(e => {
                this.errors.push(e)
            })
        }
    }
</script>

