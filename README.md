# Tweede Kamerverkiezingen 2025

**Verkiezingsdatum**: 29 oktober 2025

**Deelnemende partijen**: 27 (waaronder alle 15 zittende fracties)

Deze repository bevat alle verkiezingsprogramma's in `.txt` formaat. Dat is handig voor gebruik met LLMs zoals ChatGPT, Gemini of Claude. 

## Gebruik

Download het bestand `alle_verkiezingsprogrammas.txt` en voeg ze toe aan je gesprek met een LLM om de standpunten van partijen te vergelijken en analyseren.

## ⚠️ Let op

LLMs kunnen soms: 
* feitelijke dingen verzinnen, 
* fouten maken en 
* onjuiste informatie geven. 

Controleer informatie die jij belangrijk vindt in de originele verkiezingsprogramma's.

## Hoe zijn de verkiezingsprogramma's (in PDF) verwerkt naar een tekstbestand?

De verkiezingsprogramma's zijn gedownload van de [Rijksuniversiteit Groningen](https://www.rug.nl/research/dnpp/verkiezingen/tweede-kamer/tk-verkiezingen-2025) en vervolgens van PDF verwerkt naar `.txt` bestand. Ik heb de volgende script op een Mac (M1) uitgevoerd in een `zsh` omgeving.

```zsh
for f in *.(pdf|PDF)(.N); do
  base="${f:t:r}"
  pdftotext -enc UTF-8 -layout "$f" "$base.txt"
done

cat *.txt > alle_verkiezingsprogrammas.txt
```
