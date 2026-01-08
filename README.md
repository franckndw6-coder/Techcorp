<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Login Google</title>

    <!-- Google Identity -->
    <script src="https://accounts.google.com/gsi/client" async defer></script>

    <style>
        body {
            background: #0a1d3f;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial;
        }
        .box {
            background: #111827;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
        }
    </style>
</head>
<body>

<div class="box">
    <h2>Connexion</h2>

    <div id="g_id_onload"
        data-client_id="TON_CLIENT_ID_ICI"
        data-callback="handleCredentialResponse">
    </div>

    <div class="g_id_signin"
        data-type="standard">
    </div>

    <p id="info"></p>
</div>

<script>
function handleCredentialResponse(response) {
    const data = JSON.parse(atob(response.credential.split('.')[1]));
    
    document.getElementById("info").innerHTML =
        "Connecté en tant que : <br>" +
        data.name + "<br>" + data.email;
}
</script>

</body>
</html>
