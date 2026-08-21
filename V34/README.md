# v34 - Compute: driftsättning av Novatrix kundtjänst

Aron Niklasson

## Syfte

Veckans uppgift var att sätta upp en virtuell maskin i Azure och driftsätta Novatrix kundtjänstsida med ett ärendeformulär, samt versionshantera allt i GitHub.

## Vad jag gjorde
- Skapade en resursgrupp och en virtuell maskin (Ubuntu, storlek B2ats_v2), följde instruktionerna i videon samt Azure - Del 01 - Compute och kom igång dokumentet

  ![res](/V34/vm-info/resursgrupp.JPG)
  ![vm](/V34/vm-info/vm.JPG)
  
- Anslöt till maskinen via SSH
- Installerade nginx som webbserver
- Öppnade port 80 i nätverkssäkerhetsgruppen
  
 ![Port 80](/V34/vm-info/port80.JPG)
  
- Driftsatte kundtjänstsidan med ärendeformuläret
- Verifierade att sidan visas i webbläsaren
- Kommandon


