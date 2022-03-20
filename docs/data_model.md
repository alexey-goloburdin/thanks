[Data Model SVG](https://mermaid.ink/svg/pako:eNqtVl2PojAU_SuE55k_wBvjuLtkXTWiD5uYkApXbQItacvsmpH_vi3fLRXHjX0wlXvae-45t4VPN6YJuJ4L7B2jE0PZnjhy7ML5xrleX1-v12oerTerb8Fi7jkFBxbhxIR91jB_t_0xX26Dmb8NVksb-rOeq4GJcNqYGgdKU0DEwTxChThTZg_FAn8gAYOFXDBMTg5kCKejpzni_A9lDbzsqbQ1mZQkZxENeSUym8PghOWOSGBKIvVklOiIGRcRQdk4lKJbkfxMCUSkyA7Axgx1Oae0a4izEXGBM3BOQIApzSL1lwuU5SMmSvJIdYNVdbl3r2A9Wfu__TcpX-N_uHsLZ5tgXRufows6pNDRacF3ShCXHDQZxn2m5xk3WClhtGnHITY0wMOYU9Kbi3hx4DHDeWW8WU5zRHRO1hVaujsq1N0fmY9NTQfm6b0l4K9wEuhI9BHZaMBw7OTyB8b9ppX-cLuph9batV78QClWfZimRj_98oNFsPze-tz8Ne1QZ1xWbNd1eqmVW5v1cUsqlWNKBBBhqTNmcOvEdRgul5qAUuP1mCWmOJOuVMI37bwKt614am4ql1MuJhW3LbImHZ5ktcgzlTVOVo0Z3SYtX9qkXgQ_5ybPLpUB0vq22ul5x_Er7o_7puy5POa3Vu89s7sUlQ5TW3dVWNjfPPkal-5QD_1-Xy2bz4Jpz3ucKXEbeeoF-j_3p7zECogEYicQExVvN_4y9GeWV5Xx8tSAJs1B8KmutcWgjBbDK8wm1eCy6IFquC-u3EVePIn8iqzY7V1xBimn68lpAkdUpGLv7kkpoUWuWM4TLChzvSNKOby40i0aXkjseoIV0IKa79EGVf4DK4E9-A)

Models are not populated with a complete sets of attributes to avoid visual overload

**user** - user instances
**user_profile** - user's additional information and probably settings
**user_authentication** - authentications track
**subscription** - the types of subscriptions an author creates for his subscribers
**user_subscriptions** - M2M containing each user's subscriptions and their validity
**mailing** - mailing instances an author creates
**mailing_subscriptions** - M2M containing types of subscriptions the mailing is sent to
**post** - author posts
**post_subscriptions** - M2M containing types of subscriptions the post is visible to
**post_likes** - post likes track
**donation** - a dedicated donation initiated by tan author
**transaction** - payments track
**payable** - intermediate for payable instances
