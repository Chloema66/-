# -
德语打怪中
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <title>A1 Lückentext Quiz</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; line-height: 1.6; }
    .question { margin-bottom: 30px; }
    .input-word { width: 150px; margin: 0 5px; }
    .wrong { border: 2px solid red; background-color: #ffe5e5; }
    .correct-answer { color: red; font-size: 0.9em; margin-left: 5px; }
    .submit-btn { padding: 10px 20px; font-size: 16px; margin-top: 20px; }
  </style>
</head>
<body>
  <h1>A1 Lückentext Übung – Fünf Texte</h1>
  <form id="quizForm">
    <div class="question">
      <strong>1. Im Café</strong><br>
      Marina und ihre <input type="text" name="1" class="input-word"> Conny sind im Café. Conny kommt aus <input type="text" name="2" class="input-word">. Sie lernt <input type="text" name="3" class="input-word">. Marina trinkt gern <input type="text" name="4" class="input-word"> mit Milch. Conny trinkt Eistee ohne <input type="text" name="5" class="input-word">. Zusammen zahlen sie 8,60 <input type="text" name="6" class="input-word">. Sie zahlen <input type="text" name="7" class="input-word">.
    </div>

    <div class="question">
      <strong>2. Beruf und Hobby</strong><br>
      Karin ist Deutschlehrerin an einer <input type="text" name="8" class="input-word"> in Berlin und lebt mit ihrem <input type="text" name="9" class="input-word">. Im Moment lernt sie <input type="text" name="10" class="input-word">. Sie möchte in Madrid <input type="text" name="11" class="input-word"> unterrichten. Sie hat ein Motorrad. Das ist ihr Hobby. Mit dem <input type="text" name="12" class="input-word"> fährt sie oft zu ihren Eltern. Manchmal macht sie mit dem Motorrad <input type="text" name="13" class="input-word"> Urlaub in <input type="text" name="14" class="input-word">.
    </div>

    <div class="question">
      <strong>3. Antonios Tag</strong><br>
      Er steht jeden Tag um <input type="text" name="15" class="input-word"> auf, dann geht er <input type="text" name="16" class="input-word">. Um 8 Uhr <input type="text" name="17" class="input-word"> er. <input type="text" name="18" class="input-word"> 9.30 <input type="text" name="19" class="input-word"> 19.00 Uhr arbeitet er. <input type="text" name="20" class="input-word"> 13.00 Uhr und 14.00 Uhr <input type="text" name="21" class="input-word"> er Mittagspause. <input type="text" name="22" class="input-word"> <input type="text" name="23" class="input-word"> spielt er Squash, und um 21 Uhr geht Antonio mit <input type="text" name="24" class="input-word"> Freunden in eine Bar. <input type="text" name="25" class="input-word"> Samstag haben alle frei.
    </div>

    <div class="question">
      <strong>4. Leben ohne Auto</strong><br>
      Lars und Carla <input type="text" name="26" class="input-word"> eine Wohnung im <input type="text" name="27" class="input-word"> von Leipzig. Sie haben kein Auto. Carla fährt mit der Straßenbahn zur <input type="text" name="28" class="input-word">. Lars mit dem <input type="text" name="29" class="input-word">. Das <input type="text" name="30" class="input-word"> von Lars ist auch sein <input type="text" name="31" class="input-word">. Er kocht und isst gern und arbeitet in einem Restaurant.
    </div>

    <div class="question">
      <strong>5. Meine Arbeit</strong><br>
      Ich arbeite als <input type="text" name="32" class="input-word"> bei der Firma Steiff. <input type="text" name="33" class="input-word"> Sie die Teddybären? Nicht nur <input type="text" name="34" class="input-word"> lieben <input type="text" name="35" class="input-word"> Produkte! Ich arbeite im <input type="text" name="36" class="input-word">. Ich schreibe Texte am <input type="text" name="37" class="input-word">, <input type="text" name="38" class="input-word">, plane Termine für meinen <input type="text" name="39" class="input-word">.
    </div>

    <button type="button" class="submit-btn" onclick="checkAnswers()">提交答案</button>
  </form>

  <script>
    const answers = {
      1:"Freundin", 2:"Frankreich", 3:"Deutsch", 4:"Kaffee", 5:"Milch", 6:"Euro", 7:"getrennt",
      8:"Schule", 9:"Hund", 10:"Spanisch", 11:"Deutsch", 12:"Motorrad", 13:"auch", 14:"Europa",
      15:"7 Uhr", 16:"joggen", 17:"frühstückt", 18:"Von", 19:"bis", 20:"Zwischen", 21:"macht", 22:"Am", 23:"Freitag", 24:"seinen", 25:"Am",
      26:"haben", 27:"Zentrum", 28:"Arbeit", 29:"Fahrrad", 30:"Hobby", 31:"Beruf",
      32:"Sekretärin", 33:"Kennen", 34:"Kinder", 35:"unsere", 36:"Büro", 37:"Computer", 38:"telefonieren", 39:"Chef"
    };

    function checkAnswers() {
      const form = document.getElementById('quizForm');
      const inputs = form.querySelectorAll('input');
      inputs.forEach(input => {
        const userAnswer = input.value.trim();
        const correct = answers[input.name];
        const existing = input.nextElementSibling;
        if (existing && existing.classList.contains('correct-answer')) existing.remove();
        if (userAnswer.toLowerCase() !== correct.toLowerCase()) {
          input.classList.add('wrong');
          const correction = document.createElement('span');
          correction.className = 'correct-answer';
          correction.textContent = `(${correct})`;
          input.after(correction);
        } else {
          input.classList.remove('wrong');
        }
      });
    }
  </script>
</body>
</html>
