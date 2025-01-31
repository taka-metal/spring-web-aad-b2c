# spring-web-aad-b2c

Azure Active Directory B2C を使用したサインインを Spring Web アプリケーションで実装したいデス

# 参考

[Azure Learn: Azure Active Directory B2C を使用したサインインを Spring Web アプリに追加する](https://learn.microsoft.com/ja-jp/azure/developer/java/spring-framework/configure-spring-boot-starter-java-app-with-azure-active-directory-b2c-oidc)

# 前提条件

- Azure サブスクリプションを用意
- Java Development Kit
- Apache Mavem バージョン 3.0 以降
- src/main/resources 配下に application.yml を作成
  - client-id と client-secret に自分の値を記入
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
            client-secret: ""
          login-flow: sign-up-or-sign-in
          logout-success-url: http://localhost:8080/login/oauth2/code/
          user-flows:
            sign-up-or-sign-in: B2C_1_susi
            profile-edit: B2C_1_edit_profile
            password-reset: B2C_1_password_reset
  ```

# 画面イメージ

![image](https://github.com/taka-metal/spring-web-aad-b2c/assets/173770336/639a8ed4-122d-45b3-a1d5-cdf31557dadf)

![image](https://github.com/taka-metal/spring-web-aad-b2c/assets/173770336/4a2ca9d4-c028-409d-9cae-1886421aa930)

# Future Work

フロント画面を React で書きたいデス
