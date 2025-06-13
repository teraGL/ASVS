# V6 Автентифікація

## Мета контролю

Автентифікація це процес встановлення або підтвердження справжності особи чи пристрою. Вона передбачає перевірку заявлених відомостей про користувача або пристрій, забезпечує стійкість до спроб видавати себе за іншу особу  та запобігає відновленню чи перехопленню паролів.

[NIST SP 800-63](https://pages.nist.gov/800-63-3/) це сучасний стандарт, заснований на доказовому підході, який є корисним для організацій у всьому світі, а особливо для державних установ США та тих, хто з ними взаємодіє.

Хоча багато вимог цього розділу базуються на другому підрозділі стандарту (відомого як NIST SP 800-63B "Digital Identity Guidelines - Authentication and Lifecycle Management"), цей розділ зосереджений на поширених загрозах та часто експлуатованих слабких місцях автентифікації. Він не має на меті повністю охопити всі аспекти стандарту. У випадках, коли потрібна повна відповідність до NIST SP 800-63, слід звертатися безпосередньо до самого стандарту NIST SP 800-63.

Крім того, термінологія NIST SP 800-63 місцями може відрізнятися, і в цьому розділі часто використовується більш загальнозрозуміла термінологія для підвищення ясності.

Поширеною функцією більш просунутих застосунках є здатність адаптувати етапи автентифікації залежно від різних факторів ризику. Ця функція розглядається в розділі "Авторизація", оскільки ці механізми також потрібно враховувати при прийнятті рішень щодо авторизації.

## V6.1 Документація з автентифікації

У цьому підрозділі наведено вимоги, що докладно описують документацію з автентифікації, яку слід підтримувати для застосунку. Це має вирішальне значення для впровадження й оцінки того, як повинні бути налаштовані відповідні засоби контролю автентифікації.

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.1.1** | Перевірити, що в документації до застосунку визначено, як використовуються засоби контролю, такі як обмеження частоти запитів, захист від автоматизації та адаптивна реакція для протидії атакам, таким як підстановка облікових даних (credential stuffing) та перебір паролів (brute force). У документації має бути чітко зазначено, як ці засоби контролю налаштовано та як вони запобігають зловмисному блокуванню облікових записів. | 1 |
| **6.1.2** | Перевірити, що задокументовано перелік контекстно-специфічних слів з метою запобігання їх використанню в паролях. До такого переліку можуть входити варіації назв організацій, продуктів, ідентифікаторів систем, кодових назв проєктів, назв підрозділів або ролей та подібне. | 2 |
| **6.1.3** | Перевірити, що у разі наявності в застосунку кількох шляхів автентифікації, усі вони задокументовані разом із заходами безпеки та міцністю (рівнем) автентифікації, які мають послідовно застосовуватися для всіх них. | 2 |

## V6.2 Безпека паролів

Паролі, які у стандарті NIST SP 800-63 називаються "Memorized Secrets", включають паролі, фрази-паролі, PIN-коди, схеми розблокування, а також вибір правильного зображення, наприклад, кошеняти чи іншого елемента. Їх, як правило, вважають "чимось, що вам відомо", і вони часто використовуються як механізм однофакторної автентифікації.

Відповідно, цей підрозділ містить вимоги щодо забезпечення безпечного створення та обробки паролів. Більшість вимог належать до рівня L1, оскільки вони є найважливішими на цьому рівні. Починаючи з рівня L2, необхідно впроваджувати механізми багатофакторної автентифікації, де паролі можуть бути одним із факторів.

Вимоги цього підрозділу здебільшого стосуються [&sect; 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) з [NIST's Guidance](https://pages.nist.gov/800-63-3/sp800-63b.html).

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.2.1** | Перевірити, що встановлені користувачем паролі мають довжину не менше 8 символів, хоча наполегливо рекомендується мінімальна довжина 15 символів. | 1 |
| **6.2.2** | Перевірити, що користувачі можуть змінювати свій пароль. | 1 |
| **6.2.3** | Перевірити, що функціональність зміни пароля вимагає введення поточного та нового паролів користувача. | 1 |
| **6.2.4** | Перевірити, що паролі, які надані під час реєстрації облікового запису або зміни пароля, перевіряються за допомогою наявного набору щонайменше 3000 найпоширеніших паролів, які відповідають політиці паролів застосунку, наприклад, мінімальній довжині. | 1 |
| **6.2.5** | Перевірити, що паролі можуть містити будь-які символи без обмежень щодо типу дозволених символів. Не повинно бути вимог щодо мінімальної кількості символів верхнього або нижнього регістру, цифр або спеціальних символів. | 1 |
| **6.2.6** | Перевірити, що поля введення пароля використовує type=password для приховування введених символів. Застосунки можуть дозволяти користувачеві тимчасово переглядати увесь прихований пароль або останній введений символ пароля. | 1 |
| **6.2.7** | Перевірити, що функціональність "вставки", інструменти браузера для підтримки роботи з паролями та зовнішні менеджери паролів дозволені. | 1 |
| **6.2.8** | Перевірити, що застосунок перевіряє пароль користувача саме у тому вигляді, в якому він був наданий, без будь-яких змін, таких як обрізання або зміна регістру. | 1 |
| **6.2.9** | Перевірити, що дозволяється використовувати паролі довжиною щонайменше 64 символи. | 2 |
| **6.2.10** | Перевірити, що пароль користувача залишається дійсним до того моменту, поки не буде виявлено його компрометацію або поки користувач не змінить його самостійно. Застосунок не повинен вимагати періодичної зміни облікових даних. | 2 |
| **6.2.11** | Перевірити, що задокументований перелік контекстно-залежних слів використовується для запобігання створенню паролів, які легко вгадати. | 2 |
| **6.2.12** | Перевірити, що паролі, які надані під час реєстрації облікового запису або зміни пароля, перевіряються за допомогою набору скомпрометованих паролів, отриманих унаслідок витоків даних. | 2 |

## V6.3 Загальні вимоги до безпеки автентифікації

Цей підрозділ містить загальні вимоги до безпеки механізмів автентифікації, а також визначає різні очікування відповідно до рівнів. Застосунки рівня L2 повинні примусово впроваджувати використання багатофакторної автентифікації (MFA). Застосунки рівня L3 повинні використовувати автентифікацію на основі апаратного забезпечення, яка виконується в засвідченому та довіреному середовищі виконання (TEE). Це може включати прив’язані до пристрою ключі доступу, автентифікатори, що забезпечують високий рівень довіри відповідно до eIDAS Level of Assurance (LoA) High, автентифікатори з рівнем гарантії автентифікатора 3 (AAL3) відповідно до стандарту NIST або еквівалентний механізм.

Хоча це досить жорсткий підхід до багатофакторної автентифікації (MFA), він є критично важливим для підвищення рівня захисту користувачів, і будь-яка спроба пом’якшити ці вимоги має супроводжуватися чітким планом щодо зниження ризиків, пов’язаних з автентифікацією, з урахуванням NIST рекомендацій та досліджень з цього питання.

Зверніть увагу, що на момент публікації NIST SP 800-63 вважає електронну пошту [неприйнятною](https://pages.nist.gov/800-63-FAQ/#q-b11) як механізм автентифікації ([архівна копія](https://web.archive.org/web/20250330115328/https://pages.nist.gov/800-63-FAQ/#q-b11)).

Вимоги, наведені в цьому розділі, стосуються низки підрозділів [Керівництво NIST](https://pages.nist.gov/800-63-3/sp800-63b.html), зокрема: [&sect; 4.2.1](https://pages.nist.gov/800-63-3/sp800-63b.html#421-permitted-authenticator-types), [&sect; 4.3.1](https://pages.nist.gov/800-63-3/sp800-63b.html#431-permitted-authenticator-types), [&sect; 5.2.2](https://pages.nist.gov/800-63-3/sp800-63b.html#522-rate-limiting-throttling), та [&sect; 6.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#-612-post-enrollment-binding).

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.3.1** | Перевірити, що засоби захисту від атак, таких як підстановка облікових даних (credential stuffing) та перебір паролів (brute force), реалізовані відповідно до документації з безпеки застосунку. | 1 |
| **6.3.2** | Перевірити, що облікові записи за замовчуванням (наприклад, "root", "admin" або "sa") відсутні в застосунку або вимкнені. | 1 |
| **6.3.3** | Перевірите, що для доступу до застосунку має використовуватися або механізм багатофакторної автентифікації, або комбінація однофакторних механізмів автентифікації. Для рівня L3 один із факторів повинен бути апаратним механізмом автентифікації, який забезпечує захист від компрометації та підробки особи у разі фішингових атак, а також підтверджує намір автентифікації через дію, ініційовану користувачем (наприклад, натискання кнопки на апаратному ключі FIDO або мобільному телефоні). Ослаблення будь-яких вимог цього пункту можливе лише за наявності повністю документованого обґрунтування та комплексного набору заходів пом’якшення ризиків. | 2 |
| **6.3.4** | Verify that, if the application includes multiple authentication pathways, there are no undocumented pathways and that security controls and authentication strength are enforced consistently. | 2 |
| **6.3.5** | Verify that users are notified of suspicious authentication attempts (successful or unsuccessful). This may include authentication attempts from an unusual location or client, partially successful authentication (only one of multiple factors), an authentication attempt after a long period of inactivity or a successful authentication after several unsuccessful attempts. | 3 |
| **6.3.6** | Verify that email is not used as either a single-factor or multi-factor authentication mechanism. | 3 |
| **6.3.7** | Verify that users are notified after updates to authentication details, such as credential resets or modification of the username or email address. | 3 |
| **6.3.8** | Verify that valid users cannot be deduced from failed authentication challenges, such as by basing on error messages, HTTP response codes, or different response times. Registration and forgot password functionality must also have this protection. | 3 |

## V6.4 Authentication Factor Lifecycle and Recovery

Authentication factors may include passwords, soft tokens, hardware tokens, and biometric devices. Securely handling the lifecycle of these mechanisms is critical to the security of an application, and this section includes requirements related to this.

The requirements in this section mostly relate to [&sect; 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecretver) or [&sect; 6.1.2.3](https://pages.nist.gov/800-63-3/sp800-63b.html#replacement) of [NIST's Guidance](https://pages.nist.gov/800-63-3/sp800-63b.html).

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.4.1** | Verify that system generated initial passwords or activation codes are securely randomly generated, follow the existing password policy, and expire after a short period of time or after they are initially used. These initial secrets must not be permitted to become the long term password. | 1 |
| **6.4.2** | Verify that password hints or knowledge-based authentication (so-called "secret questions") are not present. | 1 |
| **6.4.3** | Verify that a secure process for resetting a forgotten password is implemented, that does not bypass any enabled multi-factor authentication mechanisms. | 2 |
| **6.4.4** | Verify that if a multi-factor authentication factor is lost, evidence of identity proofing is performed at the same level as during enrollment. | 2 |
| **6.4.5** | Verify that renewal instructions for authentication mechanisms which expire are sent with enough time to be carried out before the old authentication mechanism expires, configuring automated reminders if necessary. | 3 |
| **6.4.6** | Verify that administrative users can initiate the password reset process for the user, but that this does not allow them to change or choose the user's password. This prevents a situation where they know the user's password. | 3 |

## V6.5 General Multi-factor authentication requirements

This section provides general guidance that will be relevant to various different multi-factor authentication methods.

The mechanisms include:

* Lookup Secrets
* Time based One-time Passwords (TOTPs)
* Out-of-Band mechanisms

Lookup secrets are pre-generated lists of secret codes, similar to Transaction Authorization Numbers (TAN), social media recovery codes, or a grid containing a set of random values. This type of authentication mechanism is considered "something you have" because the codes are deliberately not memorable so will need to be stored somewhere.

Time based One-time Passwords (TOTPs) are physical or soft tokens that display a continually changing pseudo-random one-time challenge. This type of authentication mechanism is considered "something you have". Multi-factor TOTPs are similar to single-factor TOTPs, but require a valid PIN code, biometric unlocking, USB insertion or NFC pairing, or some additional value (such as transaction signing calculators) to be entered to create the final One-time Password (OTP).

Details on out-of-band mechanisms will be provided in the next section.

The requirements in these sections mostly relate to [&sect; 5.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#-512-look-up-secrets), [&sect; 5.1.3](https://pages.nist.gov/800-63-3/sp800-63b.html#-513-out-of-band-devices), [&sect; 5.1.4.2](https://pages.nist.gov/800-63-3/sp800-63b.html#5142-single-factor-otp-verifiers), [&sect; 5.1.5.2](https://pages.nist.gov/800-63-3/sp800-63b.html#5152-multi-factor-otp-verifiers), [&sect; 5.2.1](https://pages.nist.gov/800-63-3/sp800-63b.html#521-physical-authenticators), and [&sect; 5.2.3](https://pages.nist.gov/800-63-3/sp800-63b.html#523-use-of-biometrics) of [NIST's Guidance](https://pages.nist.gov/800-63-3/sp800-63b.html).

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.5.1** | Verify that lookup secrets, out-of-band authentication requests or codes, and time-based one-time passwords (TOTPs) are only successfully usable once. | 2 |
| **6.5.2** | Verify that, when being stored in the application's backend, lookup secrets with less than 112 bits of entropy (19 random alphanumeric characters or 34 random digits) are hashed with an approved password storage hashing algorithm that incorporates a 32-bit random salt. A standard hash function can be used if the secret has 112 bits of entropy or more. | 2 |
| **6.5.3** | Verify that lookup secrets, out-of-band authentication code, and time-based one-time password seeds, are generated using a Cryptographically Secure Pseudorandom Number Generator (CSPRNG) to avoid predictable values. | 2 |
| **6.5.4** | Verify that lookup secrets and out-of-band authentication codes have a minimum of 20 bits of entropy (typically 4 random alphanumeric characters or 6 random digits is sufficient). | 2 |
| **6.5.5** | Verify that out-of-band authentication requests, codes, or tokens, as well as time-based one-time passwords (TOTPs) have a defined lifetime. Out of band requests must have a maximum lifetime of 10 minutes and for TOTP a maximum lifetime of 30 seconds. | 2 |
| **6.5.6** | Verify that any authentication factor (including physical devices) can be revoked in case of theft or other loss. | 3 |
| **6.5.7** | Verify that biometric authentication mechanisms are only used as secondary factors together with either something you have or something you know. | 3 |
| **6.5.8** | Verify that time-based one-time passwords (TOTPs) are checked based on a time source from a trusted service and not from an untrusted or client provided time. | 3 |

## V6.6 Out-of-Band authentication mechanisms

This usually involves the authentication server communicating with a physical device over a secure secondary channel. For example, sending push notifications to mobile devices. This type of authentication mechanism is considered "something you have".

Unsafe out-of-band authentication mechanisms such as e-mail and VOIP are not permitted. PSTN and SMS authentication are currently considered to be ["restricted" authentication mechanisms](https://pages.nist.gov/800-63-FAQ/#q-b01) by NIST and should be deprecated in favor of Time based One-time Passwords (TOTPs), a cryptographic mechanism, or similar. NIST SP 800-63B [&sect; 5.1.3.3](https://pages.nist.gov/800-63-3/sp800-63b.html#-5133-authentication-using-the-public-switched-telephone-network) recommends addressing the risks of device swap, SIM change, number porting, or other abnormal behavior, if telephone or SMS out-of-band authentication absolutely has to be supported. While this ASVS section does not mandate this as a requirement, not taking these precautions for a sensitive L2 app or an L3 app should be seen as a significant red flag.

Note that NIST has also recently provided guidance which [discourages the use of push notifications](https://pages.nist.gov/800-63-4/sp800-63b/authenticators/#fig-3). While this ASVS section does not do so, it is important to be aware of the risks of "push bombing".

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.6.1** | Verify that authentication mechanisms using the Public Switched Telephone Network (PSTN) to deliver One-time Passwords (OTPs) via phone or SMS are offered only when the phone number has previously been validated, alternate stronger methods (such as Time based One-time Passwords) are also offered, and the service provides information on their security risks to users. For L3 applications, phone and SMS must not be available as options. | 2 |
| **6.6.2** | Verify that out-of-band authentication requests, codes, or tokens are bound to the original authentication request for which they were generated and are not usable for a previous or subsequent one. | 2 |
| **6.6.3** | Verify that a code based out-of-band authentication mechanism is protected against brute force attacks by using rate limiting. Consider also using a code with at least 64 bits of entropy. | 2 |
| **6.6.4** | Verify that, where push notifications are used for multi-factor authentication, rate limiting is used to prevent push bombing attacks. Number matching may also mitigate this risk. | 3 |

## V6.7 Cryptographic authentication mechanism

Cryptographic authentication mechanisms include smart cards or FIDO keys, where the user has to plug in or pair the cryptographic device to the computer to complete authentication. The authentication server will send a challenge nonce to the cryptographic device or software, and the device or software calculates a response based upon a securely stored cryptographic key. The requirements in this section provide implementation-specific guidance for these mechanisms, with guidance on cryptographic algorithms being covered in the "Cryptography" chapter.

Where shared or secret keys are used for cryptographic authentication, these should be stored using the same mechanisms as other system secrets, as documented in the "Secret Management" section in the "Configuration" chapter.

The requirements in this section mostly relate to [&sect; 5.1.7.2](https://pages.nist.gov/800-63-3/sp800-63b.html#sfcdv) of [NIST's Guidance](https://pages.nist.gov/800-63-3/sp800-63b.html).

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.7.1** | Verify that the certificates used to verify cryptographic authentication assertions are stored in a way protects them from modification. | 3 |
| **6.7.2** | Verify that the challenge nonce is at least 64 bits in length, and statistically unique or unique over the lifetime of the cryptographic device. | 3 |

## V6.8 Authentication with an Identity Provider

Identity Providers (IdPs) provide federated identity for users. Users will often have more than one identity with multiple IdPs, such as an enterprise identity using Azure AD, Okta, Ping Identity, or Google, or consumer identity using Facebook, Twitter, Google, or WeChat, to name just a few common alternatives. This list is not an endorsement of these companies or services, but simply an encouragement for developers to consider the reality that many users have many established identities. Organizations should consider integrating with existing user identities, as per the risk profile of the IdP's strength of identity proofing. For example, it is unlikely a government organization would accept a social media identity as a login for sensitive systems, as it is easy to create fake or throwaway identities, whereas a mobile game company may well need to integrate with major social media platforms to grow their active player base.

Secure use of external identity providers requires careful configuration and verification to prevent identity spoofing or forged assertions. This section provides requirements to address these risks.

| # | Опис | Рівень |
| :---: | :--- | :---: |
| **6.8.1** | Verify that, if the application supports multiple identity providers (IdPs), the user's identity cannot be spoofed via another supported identity provider (eg. by using the same user identifier). The standard mitigation would be for the application to register and identify the user using a combination of the IdP ID (serving as a namespace) and the user's ID in the IdP. | 2 |
| **6.8.2** | Verify that the presence and integrity of digital signatures on authentication assertions (for example on JWTs or SAML assertions) are always validated, rejecting any assertions that are unsigned or have invalid signatures. | 2 |
| **6.8.3** | Verify that SAML assertions are uniquely processed and used only once within the validity period to prevent replay attacks. | 2 |
| **6.8.4** | Verify that, if an application uses a separate Identity Provider (IdP) and expects specific authentication strength, methods, or recentness for specific functions, the application verifies this using the information returned by the IdP. For example, if OIDC is used, this might be achieved by validating ID Token claims such as 'acr', 'amr', and 'auth_time' (if present). If the IdP does not provide this information, the application must have a documented fallback approach that assumes that the minimum strength authentication mechanism was used (for example, single-factor authentication using username and password). | 2 |

## Посилання

Для додаткової інформації дивіться також:

* [NIST SP 800-63 - Digital Identity Guidelines](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-3.pdf)
* [NIST SP 800-63B - Authentication and Lifecycle Management](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63b.pdf)
* [NIST SP 800-63 FAQ](https://pages.nist.gov/800-63-FAQ/)
* [OWASP Web Security Testing Guide: Testing for Authentication](https://owasp.org/www-project-web-security-testing-guide/stable/4-Web_Application_Security_Testing/04-Authentication_Testing)
* [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
* [OWASP Forgot Password Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Forgot_Password_Cheat_Sheet.html)
* [OWASP Choosing and Using Security Questions Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet.html)
* [CISA Guidance on "Number Matching"](https://www.cisa.gov/sites/default/files/publications/fact-sheet-implement-number-matching-in-mfa-applications-508c.pdf)
* [Details on the FIDO Alliance](https://fidoalliance.org/)
