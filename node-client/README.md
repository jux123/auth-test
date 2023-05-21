# Auth client

This is NodeJS app that is providing secured API resource against OAuth auth-server


Start app
 - `npm start`
 - http://localhost:8080/authorized



 Request token:
 ```
 curl --request POST   --url https://dev-2yd7cgi7d13wlr1x.us.auth0.com/oauth/token   --header 'content-type: application/json'   --data '{"client_id":"Ii8nOKo0rtAf09Zw8OxzmaVRvTKLzKq1","client_secret":"2DglSb87pKHrAO8JfdYivxNSozwsIfs8FMlZ1IfqVEQwF9NFGuEQWlYSKO4AiwCs","audience":"https://test-api.example.com","grant_type":"client_credentials"}'

{"access_token":"eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InRtU2pHVVFZZXdiM0tRX0JzMWRYbyJ9.eyJpc3MiOiJodHRwczovL2Rldi0yeWQ3Y2dpN2QxM3dscjF4LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJJaThuT0tvMHJ0QWYwOVp3OE94em1hVlJ2VEtMektxMUBjbGllbnRzIiwiYXVkIjoiaHR0cHM6Ly90ZXN0LWFwaS5leGFtcGxlLmNvbSIsImlhdCI6MTY4NDY2NzYyNiwiZXhwIjoxNjg0NzU0MDI2LCJhenAiOiJJaThuT0tvMHJ0QWYwOVp3OE94em1hVlJ2VEtMektxMSIsImd0eSI6ImNsaWVudC1jcmVkZW50aWFscyJ9.f2cwXyQZP6LiP55bLontE9Jf4zOwOBEOjI3emEpLjrggxkbuoXJLos1ou0JV_BFNTPFFR1yzoW7rzUb1ICcDBGY-Uypf1vMOWbNB9sQVg0KZGW0OA47WcWUZjfHHmDd42i9mBUfom6M7m7RcYEUR1eJwWSReoaMiCYbX1-PgR_OLKFqDuV0LZpQ669p5mxxm3_JDlHDu6HweF_DlyUfqMQjSW2YpXikSdA5UG992es6kxjiMPEH9-AF380rpk_fr1y5N6uE5WeliMgNU9UIF3IT0kAN7hDCor5jyXyoMiGP_n52SRkTJ-GVRhkuxersVq_a8ulCrIeldTiPrd4YDkA","expires_in":86400,"token_type":"Bearer"}
```


Request API:
```
curl --request Gcurl --request GET \                                                                
    --url http://localhost:8080/authorized \                                                                                            
    --header 'authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6InRtU2pHVVFZZXdiM0tRX0JzMWRYbyJ9.eyJpc3MiOiJodHRwczovL2Rldi0yeWQ3Y2dpN2QxM3dscjF4LnVzLmF1dGgwLmNvbS8iLCJzdWIiOiJJaThuT0tvMHJ0QWYwOVp3OE94em1hVlJ2VEtMektxMUBjbGllbnRzIiwiYXVkIjoiaHR0cHM6Ly90ZXN0LWFwaS5leGFtcGxlLmNvbSIsImlhdCI6MTY4NDY2NzQyMCwiZXhwIjoxNjg0NzUzODIwLCJhenAiOiJJaThuT0tvMHJ0QWYwOVp3OE94em1hVlJ2VEtMektxMSIsImd0eSI6ImNsaWVudC1jcmVkZW50aWFscyJ9.jH8IbFjqpJuS65tf5mfn8fq8waZZOsDUlxU3s706os-RxvgbyehLSl1j7sAfKbd8gPCI1pKSHRRDVvjhpC338ewmnzCAwP2elrX5PV9ctO1cF8FIoBbEEYKgsQtlqzQDYz0HABH0csve-qC-fLho0WKwRZTD7pSLDTaKLu9p1DC964spAMggV7tb2iK0y7WMrCIFcZ6qT-piB51AROIctyNFHqFEOLR73Adtn_evdz6rXjy8zKcdkAj_xqsZwuUpVAgmk2gttqonmLOccS-Ea7Mr4SyUI0iXnvRU8kGU7fwabtIb8i-LXenDAcH7xaeWairqS4ibnJqzYTaj8jEPPA'

Secured Resource
```



Decode the JWT token at https://jwt.io/
```
Header:
{
  "alg": "RS256",
  "typ": "JWT",
  "kid": "tmSjGUQYewb3KQ_Bs1dXo"
}

Payload:
{
  "iss": "https://dev-2yd7cgi7d13wlr1x.us.auth0.com/",
  "sub": "Ii8nOKo0rtAf09Zw8OxzmaVRvTKLzKq1@clients",
  "aud": "https://test-api.example.com",
  "iat": 1684667420,
  "exp": 1684753820,
  "azp": "Ii8nOKo0rtAf09Zw8OxzmaVRvTKLzKq1",
  "gty": "client-credentials"
}

```

Monitor HTTP requests for port 8080:
```
sudo ngrep -d any port 8080
```