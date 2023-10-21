<script setup>
import AdminLayout from "@/Layouts/AdminLayout.vue";
import { Head } from '@inertiajs/vue3';
import Table from "@/Components/Table.vue";
import TableRow from "@/Components/TableRow.vue";
import TableHeaderCell from "@/Components/TableHeaderCell.vue";
import TableDataCell from "@/Components/TableDataCell.vue";
defineProps(['users'])
</script>

<template>
    <Head title="Dashboard" />

    <AdminLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="max-w-7xl mx-auto py-4">
            <h1>Users Index Page</h1>
        </div>
        <div class="mt-6">
            <Table>
                <template #header>
                    <TableRow>
                        <TableHeaderCell>Id</TableHeaderCell>
                        <TableHeaderCell>Name</TableHeaderCell>
                        <TableHeaderCell>email</TableHeaderCell>
                        <TableHeaderCell>Action</TableHeaderCell>
                    </TableRow>
                </template>
                <template #default>
                    <TableRow v-for="user in users" :key="user.id">
                        <TableDataCell>{{user.id}}</TableDataCell>
                        <TableDataCell>{{user.name}}</TableDataCell>
                        <TableDataCell>{{user.email}}</TableDataCell>
                        <TableDataCell>Edit / Delete</TableDataCell>
                    </TableRow>
                </template>
            </Table>
        </div>
    </AdminLayout>
</template>
