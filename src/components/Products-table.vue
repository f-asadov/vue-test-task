<template>
    <div class="table-wrapper">
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Категория</th>
                    <th>Название</th>
                    <th>Сумма</th>
                    <th></th> <!-- заголовок для столбца с иконкой удаления -->
                </tr>
            </thead>
            <tbody>

                <tr v-for="(product, index) in products" :key="index">
                    <td>{{ product.id }}</td>
                    <td>{{ product.category }}</td>
                    <td>{{ product.title }}</td>
                    <td>{{ product.price }} руб.</td>
                    <td @click="deleteProduct(index)"><i class="fa fa-trash"></i></td> <!-- иконка удаления -->
                </tr>


            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    props: {
        products: {
            type: Array,
            required: true
        }
    },
    methods:{
        deleteProduct(index){
            this.$emit('deleteProduct', index);
        }
    }
    
}

</script>


<style>
.table-wrapper {
    height: 65%;
    overflow-y: auto;
}

table {
    border-collapse: collapse;
    width: 97%;
    height: 200px;
    margin: 30px auto auto auto;
    overflow: auto;
    box-sizing: border-box;
}

thead th {
    background-color: #f2f2f2;
    font-weight: bold;
    text-align: left;
    padding: 10px;
    border-bottom: 1px solid #ccc;
}

tbody td {
    padding: 10px;
}



tbody td:last-child {
    border-bottom: none;
}

.fa-trash {
    background-image: url('https://cdn-icons-png.flaticon.com/512/4662/4662651.png');
    background-repeat: no-repeat;
    background-size: 20px 20px;
    display: inline-block;
    width: 20px;
    height: 20px;
    margin: 0 auto;
    cursor: pointer;
}

tr:not(:last-child) td {
    border-bottom: 1px solid rgba(0, 0, 0, .3)
}

tr:last-child td {

    border-bottom: none
}
</style>