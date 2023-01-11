<script setup>
import {ref,onBeforeMount} from 'vue'
import json from '../invoice.json'


const subTotal = ref(0)
const discount = ref(0)

const printInvoice = () => {
   window.print()
}

const calculation = ()=>{
    json.invoice.invoice_details.products.forEach(item=>{
        subTotal.value += parseFloat(item.price)*parseFloat(item.qty)-parseFloat(item.discount)
        discount.value += parseFloat(item.discount)
    })
}

const pdfDownload = ()=>{

}

onBeforeMount(()=>{
    calculation()
})

</script>

<template>
    <div>
        <div class="download">
            <button  @click="printInvoice" class="no-print">Pdf Print</button>
            <button  @click="pdfDownload" class="no-print">Pdf Download</button>
        </div>
        <div class="main-container printable">
            <div class="header">
                <div class="company-info">
                    <h2>{{ json.invoice.companyInfo.compnayName }} </h2>
                    <p>
                        {{ json.invoice.companyInfo.companyAddress.area }} <br>
                        {{ json.invoice.companyInfo.companyAddress.thana }},{{ json.invoice.companyInfo.companyAddress.division }} <br>
                        {{ json.invoice.companyInfo.companyAddress.road }} <br>
                        Mobile: {{ json.invoice.companyInfo.companyAddress.mobile }} <br>
                        E-mail: {{ json.invoice.companyInfo.companyAddress.email }}  <br>
                    </p>
                </div>
                <div class="logo">
                    <img :src="json.invoice.companyInfo.compnayLogo" alt="">
                </div>
            </div>
        
            <div class="customer-container">
                <div>
                    <h2>Billing To</h2>
                    <h4>{{json.invoice.customerInfo.customerName}}</h4>
                    <p>
                        {{json.invoice.customerInfo.area}} <br>
                        {{json.invoice.customerInfo.thana}},{{json.invoice.customerInfo.division}} <br>
                        {{json.invoice.customerInfo.road}} <br>
                        Mobile: {{json.invoice.customerInfo.mobile}} <br>
                        E-mail: {{json.invoice.customerInfo.email}}  <br>
                    </p>
                </div>
                <div class="invoice">
                    <table>
                        <tr>
                            <td>Invoice No</td>
                            <td>:</td>
                            <td>{{json.invoice.invoice_details.invoice_no}}</td>
                        </tr>
                        <tr>
                            <td>Due Date</td>
                            <td>:</td>
                            <td>{{json.invoice.invoice_details.due_date}}</td>
                        </tr>
                        <tr>
                            <td>Bill No</td>
                            <td>:</td>
                            <td>{{json.invoice.invoice_details.bill_no}}</td>
                        </tr>
                    </table>
                </div>
            </div>

            <div class="product-container">
                <table class="table-item" border="1" cellspacing="0">
                    <tr>
                        <th>Sl. No</th>
                        <th>Item</th>
                        <th>Price</th>
                        <th>Qty</th>
                        <th>Discount</th>
                        <th>Total</th>
                    </tr>
                    <tr v-for="item in json.invoice.invoice_details.products" :key="item.sl_no">
                        <td>{{ item.sl_no }}</td>
                        <td>{{ item.item }}</td>
                        <td>{{ parseFloat(item.price) }} Taka</td>
                        <td>{{ parseFloat(item.qty) }}</td>
                        <td>{{ parseFloat(item.discount) }} Taka</td>
                        <td>{{ parseFloat(item.price)*parseFloat(item.qty)-parseFloat(item.discount) }} Taka</td>
                    </tr>
          
                </table>
            </div>

            <div class="footer">
                <!-- <div>
                    <h4> Thank You</h4>
                    <p></p>
                </div> -->
                <div class="payment-info">
                    <h4>Payment Information</h4>
                    <table>
                        <tr>
                            <td>A/C Type</td>
                            <td>:</td>
                            <td> {{json.invoice.paymentInfo.account_type}}</td>
                        </tr>
                        <tr>
                            <td>A/C Number</td>
                            <td>:</td>
                            <td> {{json.invoice.paymentInfo.account_number}}</td>
                        </tr>
                        <tr>
                            <td>A/C Name</td>
                            <td>:</td>
                            <td> {{json.invoice.paymentInfo.account_name}}</td>
                        </tr>
                    </table>

                    <h4>Terms & Conditions</h4>
                    <p>
                        {{ json.invoice.terms_condition }}
                    </p>
                </div>
                <div class="total-invoice">
                    <table>
                        <tr>
                            <td>Sub Total</td>
                            <td>:</td>
                            <td>{{ subTotal }} Taka</td>
                        </tr>
                        <tr>
                            <td>Discount</td>
                            <td>:</td>
                            <td>{{ discount }} Taka</td>
                        </tr>
                        <tr>
                            <td>Tax(2%)</td>
                            <td>:</td>
                            <td>{{ (subTotal-discount)*2/100 }} Taka</td>
                        </tr>
                        <tr>
                            <td style="color:green;fontWeight:bold">Total</td>
                            <td>:</td>
                            <td style="color:green;fontWeight:bold">{{ (subTotal-discount)+ (subTotal-discount)*2/100 }} Taka</td>
                        </tr>
                        <tr>
                            <td>Paid</td>
                            <td>:</td>
                            <td>{{ parseFloat(json.invoice.paymentInfo.amount_paid) }} Taka</td>
                        </tr>
                        <tr>
                            <td>Due</td>
                            <td>:</td>
                            <td>{{ (subTotal-discount)+ (subTotal-discount)*2/100 - parseFloat(json.invoice.paymentInfo.amount_paid) }} Taka</td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>

.main-container{
   border: 2px solid #00005C;
   margin:20px;
   padding: 10px;
   width: 1000px;
   margin: auto;
   margin-top: 20px;
}

.header{
    display: flex;
    justify-content: space-between;
    width: 100%;
    background-color: #00005C !important;
    color:rgb(255, 255, 255);
}

.company-info h2{
    margin: 10px 0px 10px 10px;
    margin-bottom: 0px;
}

.company-info p{
    margin: 10px 0px 10px 10px;
    margin-top: 10px;
    font-size: 12px;
    line-height: 20px;
}

.logo{
    margin: 10px 10px 10px 0px;
    margin: auto 0;
    margin-right: 10px;
}
.logo img{
    height: 100px;
}

.customer-container{
    display: flex;
    justify-content: space-between;
    border: 2px solid #00005C;
    padding: 5px;
}
.customer-container h2{
    margin-bottom: 10px;
}
.customer-container h4{
    margin-bottom: 6px;
}
.customer-container p{
    margin-bottom: 10px;
    font-size: 14px;
}

.invoice{
    margin:auto 0;
    margin-right: 10px;
}

.product-container{
    margin:10px 0px;
}
.product-container table{
    width: 100%;
    border: 1px solid #00005C;
}
.product-container table tr th{
    padding: 10px;
}
.product-container table tr td{
    padding: 5px;
}

.footer{

    display: flex;
    justify-content: space-between
}

.payment-info h4{
   margin-bottom: 10px;
   margin-top: 10px;
}
.payment-info p{
    color: red
}

.payment-info table tr td {
    font-size:14px;
    line-height: 20px;
}

.total-invoice table{
    border: 4px solid #00005C;
    width: 400px;
}

.total-invoice table tr {
    font-size:14px;
    line-height: 20px;
}
.total-invoice table tr td{
    padding: 5px;
    font-weight: bold;
}

.download{
    text-align: right;
    width: 1000px;

    margin: auto;
    
}
.download button{
    padding: 5px;
    cursor: pointer;
    width:120px;
    margin:5px
}



</style>
