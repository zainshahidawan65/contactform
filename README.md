# Simple contact form

Note: Replace "your_email@example.com" with your actual email address where you want to receive the contact form submissions. Also, create a "thankyou.html" file and customize the "Location" header in the PHP code to redirect to the correct thank you page URL.

------------------------------------------------------------------------------------------------------------------------------------------------------------------

Certainly! Here's a more detailed explanation of the PHP code for the simple contact form:

1 - Start with an if statement that checks if the form has been submitted:

                                                            if(isset($_POST['submit'])) {

This condition checks whether the "submit" button has been clicked and the form data has been submitted to the server.

2 - Collect the form data using the $_POST superglobal array:

                                                              $name = $_POST['name'];
                                                             $email = $_POST['email'];
                                                            $message = $_POST['message'];
                                                            
Here, we're collecting the form data submitted by the user and storing it in variables for further use.

3 - Set the recipient email address:

                                                            $to = "your_email@example.com";

This line sets the email address where you want to receive the contact form submissions.

4 - Set the email subject:

                                                            $subject = "New contact form submission";

This line sets the subject of the email that you will receive when someone submits the contact form.

5 - Build the email content:

                                                              $email_content = "Name: $name\n";
                                                            $email_content .= "Email: $email\n\n";
                                                           $email_content .= "Message:\n$message\n";
 
Here, we're building the email content by concatenating the form data collected in step 2. The "\n" character is used to create a new line in the email message.

6 - Set the email headers:

                                                                $headers = "From: $name <$email>";

This line sets the "From" header for the email, which will display the user's name and email address in the recipient's email client.

7 - Send the email:

                                                           mail($to, $subject, $email_content, $headers);

This line uses the mail() function in PHP to send the email with the form data to the recipient's email address.

8 - Redirect to the thank you page:

                                                                  header("Location: thankyou.html");
                                                                  exit;

Finally, we're using the header() function to redirect the user to a "thank you" page after the form has been submitted. This is done by setting the "Location" header to the URL of the thank you page, and then calling exit() to terminate the script execution.

A Code by http://www.shinematrix.com/

Thanks
