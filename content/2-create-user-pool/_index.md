---
title : "Create User Pool"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
1. Open [Amazon Cognito console](https://ap-southeast-1.console.aws.amazon.com/cognito/v2/idp/user-pools?region=ap-southeast-1)
2. Select **User pools** on the left menu.
- Click **Create user pool**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-1.png?featherlight=false&width=90pc)

3. Select **Email**
- Click **Next**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-2.png?featherlight=false&width=90pc)

4. Select **Custom** for **Password policy** pattern to customize the password as you want
- Uncheck **Contain at least 1 special character**
- Set **30** for expiration date

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-3.png?featherlight=false&width=90pc)

5. Scroll down, select **No MFA** for **Multi-factor authentication** pattern
- Select **Email only** for **Delivery method** pattern
- Click **Next**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-4.png?featherlight=false&width=90pc)

6. Leave the options as default

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-5.png?featherlight=false&width=90pc)

7. Scroll down, click **Next**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-6.png?featherlight=false&width=90pc)

8. Select **Send email with Cognito**
- Click **Next**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-7.png?featherlight=false&width=90pc)

9. Enter user pool name, such as: `cognito-fcj-book-store`

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-8.png?featherlight=false&width=90pc)

10. Select **Public client**
- Enter app client name, such as: `fcj-book-store`

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-9.png?featherlight=false&width=90pc)

11. Expand the **Advanced app client settings** pattern
- Select **ALLOW_USER_PASSWORD_AUTH**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-10.png?featherlight=false&width=90pc)

12. Scroll down to bottom and click **Create user pool**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-11.png?featherlight=false&width=90pc)

13. Click on the user pool you just created
- Click **App intergation** tab

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-12.png?featherlight=false&width=90pc)

14. Scroll down to bottom, record the **Client ID**

![CreateUserPool](/images/2-create-user-pool/2-create-user-pool-13.png?featherlight=false&width=90pc)
