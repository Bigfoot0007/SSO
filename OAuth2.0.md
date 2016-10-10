# Hello OAuth.

Demo URL: http://brentertainment.com/oauth2/

通过authorization_code来获得授权


#1. Step 1: *HTTP GET*:  (在客户端页面中的link)
> http://brentertainment.com/oauth2/lockdin/authorize?response_type=code&client_id=demoapp&redirect_uri=http://brentertainment.com/oauth2/client/receive_authcode&state=51eac0abda3682af9639eab16e233677

#2. Step2: *HTTP POST* (On OAuth Server:) 在服务端进行操作后回调客户端URL

> http://brentertainment.com/oauth2/lockdin/authorize?client_id=demoapp&redirect_uri=http://brentertainment.com/oauth2/client/receive_authcode&response_type=code&state=51eac0abda3682af9639eab16e233677
	 
	 The Post Body:  authorize=1
	 
	 And the response code is 302: (HTTP GET)
	 
> http://brentertainment.com/oauth2/client/receive_authcode?code=82ee21c3a90ecef31f90f10aefda52b9f55b4aad	 &state=51eac0abda3682af9639eab16e233677
	 
#3. Step3: get Request_token (HTTP GET)

>	http://brentertainment.com/oauth2/client/request_token/authorization_code?code=82ee21c3a90ecef31f90f10aefda52b9f55b4aad
	
	
#4. Step4: 通过authorization_code获得token

>	In the step, "authorization_code" will get the token from back end.
	
#5. Step5: 
	
>	http://brentertainment.com/oauth2/client/request_resource?token=d05c75aa188b2bdf23ea12649f82014a85978584
> http://brentertainment.com/oauth2/lockdin/resource?access_token=d05c75aa188b2bdf23ea12649f82014a85978584	&access_token=d05c75aa188b2bdf23ea12649f82014a85978584

