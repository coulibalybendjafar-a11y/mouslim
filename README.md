# mouslim
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ben Adaptivité</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      color: #202124;
    }

    .container {
      max-width: 650px;
      margin: 30px auto;
      padding: 15px;
    }

    .header {
      background: white;
      border-top: 10px solid #1a73e8;
      border-radius: 8px;
      padding: 25px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.12);
      margin-bottom: 15px;
    }

    h1 {
      margin: 0 0 10px;
      font-size: 28px;
    }

    .question {
      background: white;
      padding: 22px;
      margin-bottom: 12px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.08);
    }

    label.title {
      display: block;
      font-weight: bold;
      margin-bottom: 12px;
    }

    input[type="text"],
    input[type="tel"],
    input[type="number"],
    select {
      width: 100%;
      padding: 13px;
      border: 1px solid #aaa;
      border-radius: 5px;
      font-size: 16px;
    }

    .radio {
      display: block;
      margin: 12px 0;
      font-weight: normal;
    }

    .radio input {
      margin-right: 10px;
    }

    .buttons {
      display: flex;
      gap: 12px;
      margin-top: 15px;
    }

    button {
      border: none;
      padding: 13px 22px;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }

    .send {
      background: #1a73e8;
      color: white;
    }

    .reset {
      background: #e8eaed;
      color: #202124;
    }

    #message {
      display: none;
      background: #d9f7df;
      color: #146c2e;
      padding: 15px;
      border-radius: 6px;
      margin-top: 15px;
      text-align: center;
    }

    .required {
      color: #d93025;
    }
  </style>
</head>

<body>

<div class="container">

  <div class="header">
    <h1>Ben Adaptivité</h1>
    <p>Merci de remplir ce formulaire.</p>
  </div>

  <form
    id="monFormulaire"
    action="https://script.google.com/macros/s/AKfycbwWJbScap4gYyYb-OIMYZDvsHZ9qj-Ec5-S5ijmCkAQZdoYzgC7Gfchm7fPlZ03n6ZDXg/exec"
    method="POST"
    target="envoi">

    <div class="question">
      <label class="title">
        Nom et prénom <span class="required">*</span>
      </label>
      <input type="text" name="nom" required>
    </div>

    <div class="question">
      <label class="title">
        Numéro de téléphone <span class="required">*</span>
      </label>
      <input type="tel" name="telephone" required>
    </div>

    <div class="question">
      <label class="title">
        Ton numéro WhatsApp <span class="required">*</span>
      </label>
      <input type="tel" name="whatsapp" required>
    </div>

    <div class="question">
      <label class="title">Ton genre</label>

      <label class="radio">
        <input type="radio" name="genre" value="Homme">
        Homme
      </label>

      <label class="radio">
        <input type="radio" name="genre" value="Femme">
        Femme
      </label>
    </div>

    <div class="question">
      <label class="title">
        Êtes-vous fier de ZAP à l'ATF ?
      </label>

      <label class="radio">
        <input type="radio" name="atf" value="Oui">
        Oui
      </label>

      <label class="radio">
        <input type="radio" name="atf" value="Non">
        Non
      </label>
    </div>

    <div class="question">
      <label class="title">
        Ta moyenne <span class="required">*</span>
      </label>
      <input
        type="number"
        name="moyenne"
        min="0"
        max="20"
        step="0.01"
        required>
    </div>

    <div class="question">
      <label class="title">Ta série</label>

      <select name="serie">
        <option value="">Choisir une série</option>
        <option value="C">C</option>
        <option value="D">D</option>
        <option value="E">E</option>
        <option value="F">F</option>
        <option value="H">H</option>
        <option value="Autre">Autre</option>
      </select>
    </div>

    <div class="buttons">
      <button type="submit" class="send">
        Envoyer
      </button>

      <button type="reset" class="reset">
        Supprimer
      </button>
    </div>

    <div id="message">
      ✅ Réponse envoyée avec succès !
    </div>

  </form>

  <iframe name="envoi" style="display:none;"></iframe>

</div>

<script>
  const formulaire = document.getElementById("monFormulaire");
  const message = document.getElementById("message");

  formulaire.addEventListener("submit", function() {
    setTimeout(function() {
      message.style.display = "block";
      formulaire.reset();
    }, 1500);
  });
</script>

</body>
</html>