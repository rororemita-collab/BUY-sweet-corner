<?php
include "config.php";

if(isset($_POST['buy'])){
    $product = $_POST['product'];
    $price   = $_POST['price'];
    $qty     = $_POST['qty'];
    $location= $_POST['location'];
    $phone   = $_POST['phone'];

    $total = $price * $qty;
    $order_number = rand(1000,9999);

    mysqli_query($conn,"INSERT INTO buy_orders
    (order_number,product_name,price,quantity,total,location,phone)
    VALUES
    ('$order_number','$product','$price','$qty','$total','$location','$phone')");

    echo "<script>
            alert('Order sent successfully');
            window.location='menu.php';
          </script>";
}
?>
