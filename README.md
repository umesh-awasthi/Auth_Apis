API Endpoints
# User Registration
Endpoint:  /api/auth/register
Method: POST
Request Body:
{
  "name":" " ,
  "email":" " ,
  "password": " "
}
Response:
{
    "message": "Customer registered successfully",
    "customer": {
        "name": ,
        "email": ,
        "updated_at": ,
        "created_at": ,
        "id": 
    }

# User Login
Endpoint: /api/auth/login
Method: POST
Request Body:
{
  "email": " ",
  "password": " "
}

Response:
{
    "message": "Login successful",
    "customer": {
        "id": ,
        "name": " ",
        "email": " ",
        "created_at": " ",
        "updated_at": " "
    },
    "token": " "      // This token is used at the time of logout.
}

# Password Reset Request

Endpoint: /api/auth/password/reset

Method: POST

Request Body:
{   
    "email": " "
   
}
Response:

{  "message": "Password reset link generated successfully.",
    "reset_link": "http://127.0.0.1:8000/password/reset?token=aSThtue7IOi872aPm8vcts3KdMmwnOgBc5Q0HFMLNYv3XewMgZ89HZwv1a6m",
    "instructions": "Use this link to reset your password. The link will expire in 60 minutes."
}
 

# Reset Password Confirm 

Endpoint: /api/auth/password/reset/confirm

Method: POST

Request Body:
{
  "email": " ",
  "token": "your-reset-token    //This token is received at second part of reset_Link' "   
  "password": " ",
  "password_confirmation": " ",
 
}
Response:
{
    "message": "Password reset successfully"
}

# Logout

Endpoint: /api/auth/logout

Method: POST

Headers:
{
  "Authorization": "Bearer your-access-token"  //This token is received at the time of login.
}
Response:
{
  "message": "Logout successful"
}

# Testing APIs in Postman

Set the Base URL: http://127.0.0.1:8000

Use Authorization: Bearer Token for protected routes.
