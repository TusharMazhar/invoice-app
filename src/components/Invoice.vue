<script setup>

</script>

<template>
    <div class="main-container">
        <div class="header">
            <div class="company-info">
                <h2>DJ Electronics</h2>
                <p>
                    219/13,South Pirerbug Vangga Bridge <br>
                    Mirpur-1,Dhaka <br>
                    60 Feet Road <br>
                    Mobile: +8801787373498 <br>
                    E-mail: tusharmazhartalukdar@gmail.com  <br>
                </p>
            </div>
            <div class="logo">
                <img src="https://i.pinimg.com/originals/08/02/3d/08023da2fb373a82e518bad747519ced.png" alt="">
            </div>
        </div>
     
        <div class="customer-container">
            <div>
                <h2>Billing To</h2>
                <h4>Ataur Rahman Belal Talukdar</h4>
                <p>
                    218/19,South Pirerbug Vangga Bridge <br>
                    Mirpur-11,Dhaka <br>
                    Fatabill Road <br>
                    Mobile: +8801787456565 <br>
                    E-mail: belaltalukdar@gmail.com  <br>
                </p>
            </div>
            <div class="invoice">
                <table>
                    <tr>
                        <td>Invoice No</td>
                        <td>:</td>
                        <td>#0005485</td>
                    </tr>
                    <tr>
                        <td>Due Date</td>
                        <td>:</td>
                        <td>10 January 2023</td>
                    </tr>
                    <tr>
                        <td>Bill No</td>
                        <td>:</td>
                        <td>56756</td>
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
                <tr>
                    <td>1.</td>
                    <td>Blutooth Headphone</td>
                    <td>3000 Taka</td>
                    <td>5</td>
                    <td>1000 Taka</td>
                    <td>14000 Taka</td>
                </tr>
                <tr>
                    <td>2.</td>
                    <td>Blutooth Headphone</td>
                    <td>3000 Taka</td>
                    <td>5</td>
                    <td>1000 Taka</td>
                    <td>14000 Taka</td>
                </tr>
                <tr>
                    <td>3.</td>
                    <td>Blutooth Headphone</td>
                    <td>3000 Taka</td>
                    <td>5</td>
                    <td>1000 Taka</td>
                    <td>14000 Taka</td>
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
                        <td> Bank</td>
                    </tr>
                    <tr>
                        <td>A/C Number</td>
                        <td>:</td>
                        <td> 244-4546-56765</td>
                    </tr>
                    <tr>
                        <td>A/C Name</td>
                        <td>:</td>
                        <td> Belal Talukdar</td>
                    </tr>
                </table>

                <h4>Terms & Conditions</h4>
                <p>
                    Purchasing products can be changed within 7 days after buying. But, if products damage somehow then these will not changeable.
                </p>
            </div>
            <div class="total-invoice">
                <table>
                    <tr>
                        <td>Sub Total</td>
                        <td>:</td>
                        <td>456756 Taka</td>
                    </tr>
                    <tr>
                        <td>Discount</td>
                        <td>:</td>
                        <td>4544 Taka</td>
                    </tr>
                    <tr>
                        <td>Tax</td>
                        <td>:</td>
                        <td>4565 Taka</td>
                    </tr>
                    <tr>
                        <td>Total</td>
                        <td>:</td>
                        <td>4565565 Taka</td>
                    </tr>
                    <tr>
                        <td>Paid</td>
                        <td>:</td>
                        <td>4565565 Taka</td>
                    </tr>
                    <tr>
                        <td>Due</td>
                        <td>:</td>
                        <td>0.0 Taka</td>
                    </tr>
                </table>
            </div>
        </div>
    </div>

</template>

<style scoped>

.main-container{
   border: 2px solid #00005C;
   margin:20px;
   padding: 10px;
   width: 1200px;
   margin: auto;
   margin-top: 20px;
}

.header{
    display: flex;
    justify-content: space-between;
    width: 100%;
    background-color: #00005C;
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
    border: 4px solid #00005C
}

.total-invoice table tr {
    font-size:14px;
    line-height: 20px;
}
.total-invoice table tr td{
    padding: 5px;
    font-weight: bold;
}
</style>
