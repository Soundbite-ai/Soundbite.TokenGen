# Soundbite.TokenGen
A basic C# project demonstrating Soundbite token generation

This simple example is meant to primarily demonstrate the expected format of our JWT tokens and a basic algorithm for turning the inputs into a hashed output.

# Usage
A basic approach to consuming the code would be as follows:

```cs
string encKey = "SHARED_ENC_KEY_HERE";
string orgRoute = "ORG_ROUTE_HERE";
string userEmail = "USER_EMAIL@DOMAIN.COM";

TokenServiceSettings settings = new TokenServiceSettings()
{
Config = encKey,
TokenTimeoutInMinutes = 60
};
ITokenService service = new TokenServiceSecretKey(settings);
string token = service.GenerateToken("SomeIssuer", orgRoute, userEmail);
Console.WriteLine(token);
Console.ReadLine();
```
