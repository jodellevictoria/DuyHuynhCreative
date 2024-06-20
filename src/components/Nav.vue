<template>
    <div>
        <v-app-bar>
            <template v-slot="extension">
                <v-tabs>
                    <v-tab>Home</v-tab>
                    <v-tab>Projects</v-tab>
                </v-tabs>
            </template>
        </v-app-bar>
    </div>
</template>

<script>
    export default {
        data: () => ({}),
    };
</script>