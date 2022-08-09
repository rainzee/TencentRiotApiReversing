# GAME INIT FLOW

### Init Command line arguments

```yaml
riotclient-auth-token=gX3GJOnfZKC1Uqoaxp0ltw
riotclient-app-port=6994
riotclient-tencent
no-rads
disable-self-update
region=TENCENT
locale=zh_CN
t.lcdshost=hn4-idc-feapp.lol.qq.com
t.chathost=hn4-idc-ejabberd.lol.qq.com
t.lq=https://hn4-idc-login.lol.qq.com:8443
t.storeurl=https://hn4-sr.lol.qq.com:8443
t.rmsurl=wss://cqidc-rms-bcs.lol.qq.com:443
rso-auth.url=https://prod-rso.lol.qq.com:3000
rso_platform_id=HN4_NEW
rso-auth.client=lol
t.location=loltencent.cqidc.HN4_NEW
tglog-endpoint=https://tglogsz.datamore.qq.com/lolcli/report/
t.league_edge_url=https://ledge-hn4new.lol.qq.com:22019
ccs=https://cc-hn4.lol.qq.com:8093
dradis-endpoint=http://some.url
login.userId=<redacted>
```

### Enabling Data API TGLog collection with endpoint

上报一系列到 tglog-endpoint=https://tglogsz.datamore.qq.com/lolcli/report/

### 启动LCU TRACING LOG

### LCU开始装载WAD

### Begin Launch Ux Process

### Initializing plugins

### RSO鉴权初始化

鉴权流程
初始化地址
{"install-identifier":"943fe4c9dc7da940b1e4f4a664352a8f"}
{"locale":"zh_CN","region":"TENCENT","webLanguage":"zh","webRegion":"staging.na"}
/client-config/v1/config?type=public&namespace=lol
初始化JWT鉴权参数
https://prod-rso.lol.qq.com:3000/.well-known/openid-configuration

### 版本初始化

### LOGIN

拿到已经初始化的Token

/lol-rso-auth/v1/authorization/access-token

装填参数，返回API地址

总参数装填

```json
{
  "lol.client_settings.chat.use_proxy_to_riot_client": false,
  "lol.client_settings.crash_reporter": "none",
  "lol.client_settings.honor": {
    "Enabled": true,
    "HonorVisibilityEnabled": true,
    "RecallRewardEnabled": true,
    "SecondsToVote": 40
  },
  "lol.client_settings.league_edge.url": "https://hn4new-sgp.lol.qq.com:21019",
  "lol.client_settings.loot.loot_milestones_enabled": true,
  "lol.client_settings.player_platform_edge.url": "https://hn4new-sgp.lol.qq.com:21019",
  "lol.client_settings.rms.use_proxy_to_riot_client": false,
  "lol.client_settings.rso_auth.use_proxy_to_riot_client": true,
  "lol.client_settings.summoner.profile_privacy_feature_flag": "ENABLED",
  "lol.client_settings.team_builder.pass_summoner_account_id_with_afk_readiness": true,
  "lol.client_settings.tft.tft_direct_to_hub": false,
  "lol.client_settings.tft.tft_home_hub": {
    "battlePassOfferIds": [
      "bc67768a-cf16-4917-ae92-05b630f47277"
    ],
    "enabled": true,
    "fallbackStorePromoOfferIds": [
      "d2e3cd44-43b9-4a91-9098-242e35737121"
    ],
    "storePromoOfferIds": [
      "930c65a2-a4a9-42ad-9fb6-05c202764e3a"
    ],
    "tacticianPromoOfferIds": [
      "c01af17f-690a-4289-854b-e215716a3539"
    ]
  },
  "lol.client_settings.tft.tft_hub_footer_colors": {
    "bottomColor": "#436cdf",
    "lineColor": "#66d9ff",
    "topColor": "#152846"
  },
  "lol.client_settings.tft.tft_news_hub": {
    "enabled": true,
    "url": " https://lol.qq.com/act/clientTFT/news.html"
  },
  "lol.client_settings.tft.tft_store_promos": {
    "battlePassOfferIds": [
      "f34ed470-015d-428f-b290-c1a285636ec4"
    ],
    "storePromoOfferIds": [
      "484c2f9c-21db-4e03-8f22-acf6cbca1648"
    ],
    "tacticianPromoOfferIds": [
      "2bc19a3c-4c70-4d82-9881-4f958113f39a"
    ]
  },
  "lol.client_settings.voice.use_proxy_to_riot_client": false
}
```

### lol-platform-config

/lol-login/v1/login-data-packet

UserInfo Token

会话参数

```json
{
  "accountId": 2934517868,
  "connected": true,
  "error": null,
  "idToken": "eyJraWQiOiJvbmNVIiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJkODk0M2JiNi02OTZkLTVhY2ItYWI2NC1kZjIwZDRlNjdjMmQiLCJhdWQiOiJsb2wiLCJpc3MiOiJodHRwczpcL1wvbG9sLnFxLmNvbSIsImxvbCI6W3sicGlkIjoiSE40X05FVyIsInVpZCI6MjkzNDUxNzg2OCwiY3BpZCI6IkhONF9ORVciLCJzdGF0ZSI6IkVOQUJMRUQiLCJjdWlkIjoyOTM0NTE3ODY4LCJwdHJpZCI6IjEwMDQ1MjkxNjIiLCJ1bmFtZSI6IjEwMDQ1MjkxNjIifV0sImV4cCI6MTY1OTkzODQzMSwiaWF0IjoxNjU5ODUyMDMxLCJhY2N0Ijp7ImdhbWVfbmFtZSI6bnVsbCwidGFnX2xpbmUiOm51bGx9fQ.BLdGjdlqgHADKBkV-QTYZuSOlkVwFAbFMuSgzbwTPE3LiL9HRPJey4NOzk8cbxw5zp-ilhZvo_W9SFrjqH86IYZCsYSsJoEKFbQnE9WU1NCaBkPoNTT0bAwpnm1V1elkdSTqJCeTL6bqTf-F_1Zt2UDlcKtPBVBjTacyfrho36WODjUix1o6Wkw49CQxb3dHhAnenC0Zo2XAyi2vuteepxBi2cPO8UyhgaW1KYtodB_x53n_IbZ6hK18qtAtJuAdalb7_AVT7SMLrtaDJhcikBASJs_2SFISZ9vrwTxfzE_-a1RpQvO0O05F2q6tOkM6tLXoDE7IdSNKRH75mVQB_w",
  "isInLoginQueue": false,
  "isNewPlayer": false,
  "puuid": "d8943bb6-696d-5acb-ab64-df20d4e67c2d",
  "state": "SUCCEEDED",
  "summonerId": 2934517868,
  "userAuthToken": "{\r\n\t\"account_id\": 2934517868,\r\n\t\"account_name\": \"2934517868\",\r\n\t\"fingerprint\": \"7823ae2957be6d04243330e71143cf98\",\r\n\t\"ip\": \"27.11.16.201\",\r\n\t\"other\": \"WfPJOj+I8EnkZuN5nKTR1HeW6g-CjuBmdbeNFINRRl2AVSHpwDh1saRSU5V672MwHgl7cXhmHqb3Vp3Iy5ehoQ==\",\r\n\t\"partner_token\": \"Bearer eyJraWQiOiJvbmNVIiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJkODk0M2JiNi02OTZkLTVhY2ItYWI2NC1kZjIwZDRlNjdjMmQiLCJzY3AiOlsib3BlbmlkIiwib2ZmbGluZV9hY2Nlc3MiLCJsb2wiLCJiYW4iLCJwcm9maWxlIiwiZW1haWwiLCJwaG9uZSJdLCJjbG0iOlsicHciLCJsb2wiLCJiYW4iLCJhY2N0X2dudCIsIm9wZW5pZCIsInJnbl9ITjRfTkVXIiwiYWNjdCIsInVzZXJuYW1lIiwiIV9fOEgiXSwiZGF0Ijp7InIiOiJITjRfTkVXIiwiYyI6InNoIiwidSI6MjkzNDUxNzg2OH0sImlzcyI6Imh0dHBzOlwvXC9sb2wucXEuY29tIiwiZXhwIjoxNjU5ODUyNjMxLCJpYXQiOjE2NTk4NTIwMzEsImp0aSI6IjNmQlhyTV9yRW1VIiwiY2lkIjoibG9sIn0.YtwV18Vc9jMI1BsXDYSlug0EBEOP2WYpq2BTnk7xd4PZXYuIQoEhWtlbDdpOTaBkjSRnwRk9j7DqgCPuEY_kwdACsfV7Z5s8BiPW8GjwP7FXJCvLkVNzu4gEGCCYC3McWk-6zSeWXyRgDQe6ubJXjj2g8GkzUePKNyIeNS1PrpK88leTm2kIYy9fKoI2PPQsQl79hUcwexBO21jvLlDdzKtPpxrIv6ZbUUQnTbFwHnF5YLFRLCRI3U2-bPMT7o5GMxVv7ASeybv58xPTrrMZtf3Tkgnv48hwNq7KsKfLC9o5PqNwqBkC-XrykxLlsGoGQ5E1EvQAs1eKj_TpyEQ71g\",\r\n\t\"resources\": \"lol\",\r\n\t\"signature\": \"TO+3pCU8daMFoDaYSeMjTQH0yJqIwuKkm5uh3wemFEQhk/CjnoM8W+YRZE1Pg2IjJniBcWI9nnc7exJeRLEpIHGFbtUjkXj8nU9Z6FaLZFDnIy9Yf7FXYf6egxBToMcePCHDX2KFaYlVtL10LmEIXw/WyM7MEWdja3LP6jfml3g=\",\r\n\t\"timestamp\": 1659852036756,\r\n\t\"userinfo\": \"eyJraWQiOiJsY3UtcHJvZC1wdWJsaWMtZW5jIiwiY3R5IjoiSldUIiwiZW5jIjoiQTI1NkdDTSIsImFsZyI6IlJTQS1PQUVQIn0.e1kW95Uvd9FYWi8RScrihJ0yHvA4iR1TEyx5YaMch9nKwGjyJaOv-YZ9Ok4EfCibiQhGEkBsFvmNyzSkEnMDc0-gAulV1bzvaebFInyb9jikIspaHSpk-B3ndGX4Ma5COKBABVCBGz3nLvY1Ezhp-IoXRXrfeGdTw-PHs8meox7wc31NZN_W8CRtHtz5jVqeBTr-jYzbNBYe1AGFLxC_IMlpDQOkhX1zoYrRyCbfx11iH9SkA5fqwwKDJFwh-eg-PaeMsnF0Vkb3XoumLFMlS_SKjlLDyRleIEig-EKZu5dBulABILgkeTHIrtgqZNOwfJ4leAJcO1laSvTfFTAp8Q.9j6m_Vk6R26crVhx.ToLjD8kQFqYMt-Zo_4dUuyyVt3tyP-7CxuOVrvL-Idzy9Zs2qk_THmYJD4tT2CsaJhSdZkoFcKZhys6oUF26S25z035snHshdFOH97_N2b45g4n64GuqGVhyTFldglNlGRUdJp1ciFNL6yzoYGeDSQkVdXMH_o0C-UqVuqC2K_qaoBtg_3_CuP5KX6EdUaODb7ck9VAngUnbrJHJ8xhjRcyJEwpk85kgTG1eou9e8NkOtpWkzg-2r-evGjXqIP2I3WM2xL9AcVZAU0iR8Ea3Ht7_KGgkIBVPa5vE09p7lCjGdXJ1TU2MbqJUXie7rokbGOxxScd9ZlO5K69F9vkKBdcG9MTWYoUQJkvRZT2gbD5hd8tqeNzjjsWaiRVTyv3g6g6p68EYMaB3_zIdZNaNaxNz7msZ2CMSCPvyVBbEbvik9bgWTrj7PQ8C0iN0qXI9cC9oqwovCjKul3dy0BqmaNZ2t2DHLj8_PQqPlRT1zZCLbn0Dm1k6lhCnCUGFY8O3IGf2rjYj4eHMJfEahARcSFH9et7o_yX-aiRul0TVJPmfmI9aSbDCNxueeK_ginsrLKjJiGkdgkNTRWfKE07gYtiC-x4QnHojGEIh3--UMpPdnGBcV3-hXoKrVdpEaZXxTkVBZDAu3wKDlYuH2K9XXg7yk3ym9FjAGoX38f_tMyGGZFyoavIxbK-4gVxxFZO3V5F57b6kT9CqCw_qhP3V5XToTGladK-i0F2g2keHZVjUb0M0-25HXSePJnE7_nH0OYzRrwUg9RLosTarMsKyvFPmBcxv1OGpxOGRBAJU_RkMKM80LA1Jng0P6U7Ck3Iv2PajI1nsOSBpWRLPs21eWFqooSrCxRnghQxfzgZOWcrdDp8cNk8Zov5SwComfDba84pEH-krbgYPY1rKFfyb8n8mes9TuZyqx-N3zWc-DpnxqeANQsnp_qIsuSOtUjSVwgIDExlSVv60A_cVJBHD3_sHvyFpnw9auXSk0clKAp4G3k1l9ovkPPJnw5RCEvT4ayO3cb8WSPP1jpQxyXXQFo0jSyB9ezIehP9f0ApT4J6Ko0x2ULNiZ4LR3tym0XAT6WaVEBoQ5zjpdxlGvG3vPdU_PUFp3BDhlmUdXiMQ9kSCuqWRaHrm0C7Q-EiAxNKpvRHuonSzTVtS7sEzZvXW1lDlkg3ViXXSAUJ0fsufu2wvhD8IQiVypC9rsImfXmmAAU9Dz4AIoPIdcIn_Ldx-jBnOXBXunCoy1IQkfqXyq0ONcs1fe_nIstqDLPHLN_2K5Eq1VUpYBrrS0mgd7c4O_WXctGCzWkcNwd9OhxzAXwqHuOlfQaeKozVopU46NPxyf7Vi4THjQ9crN8PZDCbke4qU3dHjeNIRYhdDkiu_UmYzbeDDLGEXxsXhfpXvg9c5CCWgc3QOTVIlTwOLv_25umzA_z1Jko2mbceV4dhV78fUszEuzCGpL-SCUje-tpfLSNdxiGnR10l-rFjvZGIe87FlCXbYhHvi83ZauuOMHHW6HL_MbZslzabEeI4xjJ6ZGBLOPmH8zN_ynDjO7cFiQjkR_42WY-j-HMcS2QMBhXBT13XG3dPExzq-EHwm.8us1M0EFGCxAHI5KjSf3vg\",\r\n\t\"uuid\": \"f4bedb20-670e-498d-9b64-0d918de1b077\"\r\n}",
  "username": "2934517868"
}
```





/lol-login/v2/league-session-init-token



```json
{
  "logoutOnFailure": true,
  "token": "eyJraWQiOiJzMSIsImFsZyI6IlJTNTEyIn0.eyJzY3AiOiJMT0wiLCJzdWIiOiJkODk0M2JiNi02OTZkLTVhY2ItYWI2NC1kZjIwZDRlNjdjMmQiLCJwcm9kdWN0IjoiTE9MIiwicGFydGlkIjoiMTAwNDUyOTE2MiIsImFjdGlkIjoyOTM0NTE3ODY4LCJjbmFtZSI6ImxjdSIsImlzcyI6Imh0dHBzOlwvXC9zZXNzaW9uLWp3a3MtMTI1MzI5ODE4NS5jb3MuYXAtc2hhbmdoYWkubXlxY2xvdWQuY29tIiwicmZhIjoxNjU5ODUyMzY4LCJzaWQiOiIzOGNjYjI0ZC0zODQ4LTQ2MjQtYjBkOC1jM2MxNjU2OGFkZGQiLCJieXBhc3MiOmZhbHNlLCJyZWciOiJITjRfTkVXIiwiZGF0Ijp7InIiOiJITjRfTkVXIiwidSI6MjkzNDUxNzg2OH0sInJmbyI6MzMyLCJleHAiOjE2NTk4NTI2MzYsImlhdCI6MTY1OTg1MjAzNiwianRpIjoiOWZiYjFkNGUtMzlkYy00MmE3LTgwZmQtZDY0NDQxODA2YzliIiwiY2lkIjoibHNzIiwic2l0IjoxNjU5ODUyMDM2fQ.K3olKbqEVdWV4sVI7b77Ov5ZUD6BhPZHv90kAiWwvCzSQRaxqIiC1Ao87ct_N2pyqp3PaWty-4Jfex_7aZvYPvm1fzqEJtFT-Mb9UY99YxsXb89Vpjje9xhlKcj3ajxm-TB1Bh8OHI0-SUdQ5gtj9hzquDTDZfyPiBl2Pa1jC2ib3Ce1nGYfpsaGTHV7ow3Er0jdgc0XDnvw_QI3K_BcjTDpI6aoYig2IJ3Jzn9_qsWyZ-Z8SrR9yk-zzOtbWsMUuFPAif3_XSEzlD536PhD0eGKwOXFUEpcse-JYesjaw48iBJW1js_AlS04uDEUzDP41zUPIVNSw2WyH4JyfwJ6Q"
}
```

https://127.0.0.1:2195/lol-platform-config/v1/namespaces/

