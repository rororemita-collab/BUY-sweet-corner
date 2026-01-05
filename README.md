# BUY-sweet-corner
<?php
include "config.php";

$order_number = rand(12334, 99999); 

if(isset($_POST['buy'])){
    $product = $_POST['product'];
    $price   = $_POST['price'];
    $qty     = $_POST['qty'];
    $location = $_POST['location'];
    $phone    = $_POST['phone'];

    $total = $price * $qty;

    $sql = "INSERT INTO buy_orders(order_number, product_name, price, quantity, total, location, phone)
            VALUES('$order_number', '$product', '$price', '$qty', '$total', '$location', '$phone')";

    if(mysqli_query($conn, $sql)){
        echo "<script>alert('Order #$order_number has been placed successfully!'); window.location.href='Menu.php';</script>";
    } else {
        echo "Error: ".mysqli_error($conn);
    }
}
?>
