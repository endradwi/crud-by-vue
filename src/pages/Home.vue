<script setup lang="ts">
import { ref, onMounted } from "vue";

interface User {
  id: string;
  name: string;
  address: string;
  gender: string;
  date_of_birth: string;
  input_date: string;
}

// State untuk menyimpan data users
const users = ref<User[]>([]);

// Fungsi Fetch Data
const DataTransfer = async () => {
  try {
    const res = await fetch("https://67b6f7232bddacfb270d092e.mockapi.io/users");
    users.value = await res.json();
  } catch (error) {
    console.error("Error fetching data:", error);
  }
};

// Ambil data saat komponen dimuat
onMounted(() => {
  DataTransfer();
});
</script>

<template>
  <main class="w-full h-screen flex flex-col gap-3 justify-center items-center">
    <button class="border bg-slate-400 hover:bg-slate-900 hover:text-white cursor-pointer py-1 px-3 rounded-lg">
      Tambah User
    </button>

    <table class="table-auto border space-y-52">
      <thead class="border-2">
        <tr>
          <td class="border p-2">No</td>
          <td class="border p-2">Nama</td>
          <td class="border p-2">Alamat</td>
          <td class="border p-2">P/W</td>
          <td class="border p-2">Tanggal Lahir</td>
          <td class="border p-2">Tanggal Input</td>
          <td class="border p-2">Aksi</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user, index) in users" :key="user.id" class="border">
          <td class="border p-2 text-center">{{ index + 1 }}</td>
          <td class="border p-2">{{ user.name }}</td>
          <td class="border p-2">{{ user.address }}</td>
          <td class="border p-2">{{ user.gender == 'male' ? 'Pria' : user.gender == 'female' && 'Wanita' }}</td>
          <td class="border p-2">{{new Date(user.date_of_birth).toLocaleDateString("id-ID", { day: '2-digit', month: 'short', year: 'numeric' })}}</td>
          <td class="border p-2">{{new Date(user.input_date).toLocaleDateString("id-ID")}}</td>
          <td class="gap-2 p-2 flex text-center">
            <button>[View]</button>
            <button>[Edit]</button>
            <button>[Delete]</button>
          </td>
        </tr>
      </tbody>
    </table>
  </main>
</template>
