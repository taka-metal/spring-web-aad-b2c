# Azure Active Directory B2Cを使用したサインインをSpring Web アプリケーションで実装したいデス

# 参考
[Azure Learn: Azure Active Directory B2C を使用したサインインを Spring Web アプリに追加する](https://learn.microsoft.com/ja-jp/azure/developer/java/spring-framework/configure-spring-boot-starter-java-app-with-azure-active-directory-b2c-oidc)

# 前提条件
- Azureサブスクリプションを用意
- Java Development Kit
- Apache Mavem バージョン3.0以降
- src/main/resources配下にapplication.ymlを作成
  - client-idとclient-secretに自分の値を記入
  ```yml
  spring:
  cloud:
    azure:
      active-directory:
        b2c:
          enabled: true
          base-uri: https://myb2cdummyorganization.b2clogin.com/myb2cdummyorganization.onmicrosoft.com/
          credential:
            client-id: 
            client-secret: ''
          login-flow: sign-up-or-sign-in
          logout-success-url: http://localhost:8080/login/oauth2/code/
          user-flows:
            sign-up-or-sign-in: B2C_1_susi
            profile-edit: B2C_1_edit_profile
            password-reset: B2C_1_password_reset
  ```
