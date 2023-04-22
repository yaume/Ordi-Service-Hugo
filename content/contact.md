---
title: "Contactez-moi"
date: 2023-04-05T08:02:31+02:00
layout: contact
class: contact
outputs: PHP
slug: contact
url: /contact.php
---

{{< form ID="contact" >}}
{{< php >}}

<?php
$page = "/contact.php";
if ($page !== $_SERVER['PHP_SELF']) {
die(header('location: /index.html'));
}
//Récupération de l'IP
//TODO Geolocalisation
$ip = $_SERVER['REMOTE_ADDR'];
// Création du jeton et du pointeur
session_start();
$_SESSION['jeton'] = bin2hex(random_bytes(32));
$_SESSION['pointeur'] = time();
$jeton = $_SESSION['jeton'];
$pointeur = $_SESSION['pointeur']
 ?>

--coupure--
<input type="hidden" name="jeton" value="<?php echo $jeton ?? '' ?>">
<input type="hidden" name="pointeur" value="<?php echo $pointeur ?? '' ?>">
<input type="hidden" name="ip" value="<?php echo $ip ?? '' ?>">
--coupure--
{{< /php >}}
{{< /form >}}
