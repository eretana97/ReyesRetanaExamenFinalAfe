<template>
  <div class="table-responsive">
    <table class="table table-striped table-hover mt-3">
      <thead>
        <tr>
          <th v-for="(header, index) in headers" :key="index">{{ header }}</th>
        </tr>
      </thead>
      <tbody v-if="data">
        <tr v-if="data.length == 0">
          <td :colspan="headers.length" class="text-center">
            No se encontraron registros por mostrar.
          </td>
        </tr>
        <tr v-for="(value, index) in data" :key="value.id">
          <td>{{ index + 1 }}</td>
          <td>{{ value.name_bank }}</td>
          <td>
            <a href="#" class="btn btn-warning" @click="edit(value.id)"
              ><i class="fa fa-edit"></i> Editar</a
            >
            <a href="#" class="btn btn-danger" @click="deleteValue(value.id)"
              ><i class="fa fa-trash"></i> Eliminar</a
            >
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>