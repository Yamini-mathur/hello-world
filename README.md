# hello-world
$redsys = new \Buuum\Redsys($redsys_key);

try {
    $redsys->setMerchantcode($redsys_merchant_code);
    $redsys->setAmount($amount);
    $redsys->setOrder($order);
    $redsys->setTerminal($redsys_merchant_terminal);
    $redsys->setCurrency(978);

    $redsys->setTransactiontype('0');
    $redsys->setMethod('C');

    $redsys->setNotification('http://localhost/notification.php'); //Url de notificacion
    $redsys->setUrlOk('http://localhost/payment_ok.php');
    $redsys->setUrlKo('http://localhost/payment_ko.php');

    $redsys->setTradeName('Store S.L');
    $redsys->setTitular('John Doe');
    $redsys->setProductDescription('Product description');

    $form = $redsys->createForm();

} catch (Exception $e) {
    echo $e->getMessage();
    die;
}

echo $form;
