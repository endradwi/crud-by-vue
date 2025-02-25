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
    
              <tr class="border">
                <td class="border p-2 text-center">No</td>
                <td class="border p-2">Nama</td>
                <td class="border p-2">Alamat</td>
                <td class="border p-2">gender</td>
                <td class="border p-2">Date</td>
                <td class="border p-2">Date</td>
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
  