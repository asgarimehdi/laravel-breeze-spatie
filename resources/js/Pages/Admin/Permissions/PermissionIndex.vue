<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { Head } from '@inertiajs/vue3';
import TableHeaderCell from "@/Components/TableHeaderCell.vue";
import TableDataCell from "@/Components/TableDataCell.vue";
import Table from "@/Components/Table.vue";
import TableRow from "@/Components/TableRow.vue";

defineProps(['permissions'])
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <div class="max-w-7xl mx-auto py-4">
            <h1>permissions Index Page</h1>
        </div>
        <div class="mt-6">
            <Table>
                <template #header>
                    <TableRow>
                        <TableHeaderCell>Id</TableHeaderCell>
                        <TableHeaderCell>Name</TableHeaderCell>
                        <TableHeaderCell>Action</TableHeaderCell>
                    </TableRow>
                </template>
                <template #default>
                    <TableRow v-for="permission in permissions" :key="permission.id">
                        <TableDataCell>{{permission.id}}</TableDataCell>
                        <TableDataCell>{{permission.name}}</TableDataCell>
                        <TableDataCell>Edit / Delete</TableDataCell>
                    </TableRow>
                </template>
            </Table>
        </div>
    </AdminLayout>
</template>
