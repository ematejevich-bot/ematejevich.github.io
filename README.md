html_content = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>EJ Matejevich - About</title>
<style>
body { font-family: Arial, sans-serif; margin: 0; padding: 0; line-height: 1.6; background-color: #f4f4f4; }
header { background: #333; color: #fff; padding: 20px 0; text-align: center; }
.container { width: 80%; margin: auto; overflow: hidden; padding: 20px; }
h1, h2 { color: #333; }
.section { margin-bottom: 30px; }
footer { background: #333; color: #fff; text-align: center; padding: 10px 0; position: fixed; width: 100%; bottom: 0; }
</style>
</head>
<body>
<header>
<h1>EJ Matejevich</h1>
<p>CREATOR · INNOVATOR · DEVELOPER</p>
</header>
<div class="container">
<div class="section" id="about">
<h2>About Me</h2>
<p>Born and raised in NYC with Serbian, Irish, and Filipino roots. A five-year student at The Browning School driven by a passion for finance, entrepreneurship, law, and technology — committed to growth in every arena.</p>
</div>
<div class="section" id="background-interests">
<h2>Background & Interests</h2>
<p>Basketball in recreational leagues and piano at Filipino roots. Five years at The Browning School, recitals keep me disciplined and balanced, consistently challenging myself academically outside of academics, and growing as a leader.</p>
</div>
<div class="section" id="looking-forward">
<h2>Looking Forward</h2>
<p>Actively involved in Mock Trial, Model United Nations, and Debate — aiming to earn recognition in competitions and gain valuable experience through internships and future career opportunities.</p>
<p>Active member contributing to school culture, community storytelling, and publication.</p>
</div>
<div class="section" id="activities">
<h2>Activities</h2>
<h3>Model United Nations & Debate</h3>
<p>Actively involved in Model UN, working toward awards in competitive conferences. Participating in debate tournaments, developing argumentation and critical thinking under pressure.</p>
</div>
</div>
<footer>
<p>&copy; 2024 EJ Matejevich</p>
</footer>
</body>
</html>
'''

with open('ej_website.html', 'w') as file:
    file.write(html_content)
