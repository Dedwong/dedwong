# dedwong 
<!DOCTYPE HTML>
<html>
<head>
<title>CVV Quick Check</title>
<style type="text/css">
</style>
</head>

<body>
<script type="text/javascript">
function validateCVV($cardNumber, $cvv)
{
    // Get the first number of the credit card so we know how many digits to look for
    var $firstnumber = Number($cardNumber.substr(0, 1));
    if ($firstnumber === 3)
    {
        if (!$cvv.match(/^\d{4}$/))
        {
            // The credit card is an American Express card but does not have a four digit CVV code
            return false;
        }
    }
    else if (!$cvv.match(/^\d{3}$/))
    {
        // The credit card is a Visa, MasterCard, or Discover Card card but does not have a three digit CVV code
        return false;
    }
    return true;
}
document.write("validateCVV//Expected <br />");
document.write(validateCVV('4111-1111-1111-1111', '123')+"// True <br />");
document.write(validateCVV('4111-1111-1111-1111', '1233')+"// False <br />");
document.write(validateCVV('4111-1111-1111-1111', 'aaa')+"// False <br />");
document.write(validateCVV('5111-1111-1111-1111', '456')+"// True <br />");
document.write(validateCVV('5111-1111-1111-1111', '567')+"// True <br />");
document.write(validateCVV('6011-1111-1111-1111', '423')+"// True <br />");
document.write(validateCVV('3782-8224631-0005', '4213')+"// True <br />");
document.write(validateCVV('3782-8224631-0005', '423')+"// False <br />");
</script>

</body>
</html>

เลือกทั้งหมด
