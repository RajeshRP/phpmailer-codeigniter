# phpmailer-codeigniter

Send mails via phpmailer on codeigniter. Can be useful for someone that doesnot want clone complete source of PHP Mailer repository.

## Usage

Create PHP Mailer object with sample code below and the object same way as PHPMailer

```
$this->load->library("PhpMailerLib");
$mail = $this->phpmailerlib->load();
```        
### Sample Function

```
Replace USERNAME, PASSWORD, and other variables accordingly 
function phpmailer()
{
	$this->load->library("PhpMailerLib");
        $mail = $this->phpmailerlib->load();
	try {
		    //Server settings
		    $mail->SMTPDebug = 2;                                 // Enable verbose debug output
		    $mail->isSMTP();                                      // Set mailer to use SMTP
		    $mail->Host = 'smtp.yandex.com';  // Specify main and backup SMTP servers
		    $mail->SMTPAuth = true;                               // Enable SMTP authentication
		    $mail->Username = 'USERNAME';                 // SMTP username
		    $mail->Password = 'PASSWORD';                           // SMTP password
		    $mail->SMTPSecure = 'ssl';                            // Enable TLS encryption, `ssl` also accepted
		    $mail->Port = 465;                                    // TCP port to connect to
		    //Recipients
		    $mail->setFrom('USEREMAIL', 'Ganesha from Retainly');
		    $mail->addAddress('RECEIPIENTEMAIL01', 'RICIPIENTNAME');     // Add a recipient
		    $mail->addAddress('RECEIPIENTEMAIL02');               // Name is optional
		    $mail->addReplyTo('tejakhan@yahoo.com', 'Ganesha');
		    //$mail->addCC('cc@example.com');
		    //$mail->addBCC('bcc@example.com');

		    //Attachments
		    //$mail->addAttachment('/var/tmp/file.tar.gz');         // Add attachments
		    //$mail->addAttachment('/tmp/image.jpg', 'new.jpg');    // Optional name

		    //Content
		    $mail->isHTML(true);                                  // Set email format to HTML
		    $mail->Subject = 'Here is the subject';
		    $mail->Body    = 'This is the HTML message body <b>in bold!</b>';
		    $mail->AltBody = 'This is the body in plain text for non-HTML mail clients';

		    $mail->send();
		    echo 'Message has been sent';
		} catch (Exception $e) {
		    echo 'Message could not be sent.';
		    echo 'Mailer Error: ' . $mail->ErrorInfo;
		}
	}
  ```
