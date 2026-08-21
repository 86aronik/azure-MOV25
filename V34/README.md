# v34 - Compute: driftsättning av Novatrix kundtjänst

Aron Niklasson Azure v34

## Syfte

Veckans uppgift var att sätta upp en virtuell maskin i Azure och driftsätta Novatrix kundtjänstsida med ett ärendeformulär, samt versionshantera allt i GitHub.

## Vad jag gjorde
- Skapade en resursgrupp och en virtuell maskin (Ubuntu, storlek B2ats_v2), följde instruktionerna i videon samt Azure - Del 01 - Compute och kom igång dokumentet

  ![res](/V34/vm-info/resursgrupp.JPG)
  ![vm](/V34/vm-info/vm.JPG)
  
- Anslöt till maskinen via SSH

ssh -i vm-novatrix-web_key@20.240.204.16

Svarade 'yes' på frågan om att lita på servern första gången

Uppdaterade servern med nyaste paket samt uppgraderingar:
sudo apt update
sudo apt upgrade -y

- Installerade nginx som webbserver

sudo apt install nginx -y

kontroll att den är igång: systemctl status nginx

- Öppnade port 80 i nätverkssäkerhetsgruppen
  
 ![Port 80](/V34/vm-info/port80.JPG)

- Driftsatte kundtjänstsidan med ärendeformuläret

Gick in i /var/www/html i terminalen öppnade redigering suno nano index.html och använde min html kod (se html kod rubrik)

- Verifierade att sidan visas i webbläsaren

  Surfar in på http://20.240.204.16/

  ![web](/V34/vm-info/webserv.JPG)

- HTML kod

```html
<!DOCTYPE html>
<html lang="sv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Novatrix AB</title>
</head>
<body>

    <h1>Novatrix AB</h1>

    <h2>Ärendeformulär</h2>

    <form>
        <label for="namn">Namn:</label><br>
        <input type="text" id="namn" name="namn" required><br><br>

        <label for="email">E-post:</label><br>
        <input type="email" id="email" name="email" required><br><br>

        <label for="meddelande">Meddelande:</label><br>
        <textarea id="meddelande" name="meddelande" rows="6" required></textarea><br><br>

        <button type="submit">Skicka</button>
    </form>

</body>
</html>
```

