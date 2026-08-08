# Email-Classification-System

AI-Powered Social vs Promotion Email Classifier
Syfte/Mål
Detta projekt syftar till att skapa ett AI-system som automatiskt klassificerar e-postmeddelanden som antingen sociala (personliga meddelanden, inbjudningar) eller kampanjer (reklam, nyhetsbrev, erbjudanden). Systemet är byggt för användare som är osäkra på om ett mail är socialt eller en kampanj, och vill ha ett snabbt och pålitligt svar utan att behöva gissa.

Målet är att användaren ska behöva göra så lite som möjligt - bara mata in ett mail och få en omedelbar klassificering med hög tillförlitlighet.

---

## Funktion
Systemet erbjuder följande funktioner:

* Automatisk klassificering av e-post som social eller kampanj

* Två ML-modeller (Random Forest och XGBoost) för jämförelse och hög precision

* Konfidensgrad för varje förutsägelse så användaren vet hur mycket den kan lita på resultatet

* Interaktiv gränssnitt där användaren kan klistra in ett mail och få omedelbart svar

* PowerBI-dashboard för visualisering av resultat och modellprestanda

* Export av förutsägelsehistorik för vidare analys

* Stöd för svenska och engelska e-postmeddelanden

## Vad systemet visar:

<img width="610" height="286" alt="image" src="https://github.com/user-attachments/assets/b85bb0d0-0b7f-4e28-82e6-b536b88bf5fa" />


**INFO:** För extra hjälp, se README-filen eller kör notebooken cell för cell för att förstå processen.

En CSV-fil med förutsägelsehistorik skapas i mappen exports/ som kan användas för vidare analys.

En JSON-fil med sammanfattande statistik skapas i samma mapp, där du kan se modellprestanda och nyckeltal.

---
## Systemkrav
***Minimala krav***
    
    Komponent:       Krav
    Operativsystem:  Windows 10, macOS 10.15+, eller Linux (Ubuntu 20.04+)
    Python:	         3.8 eller högre
    RAM:	         8 GB minimum (16 GB rekommenderas)
    Lagring:	     2 GB ledigt utrymme
    Internet:	     Krävs för NLTK-nedladdningar och Google Colab

***Programvara***

    Programvara:	 Syfte
    Google Colab:	 Primär miljö 
    Python 3.8+:	 Alternativ lokal körning
    PowerBI Desktop: Dashboard-visualisering (valfritt)
    
***Dataset-krav***

    Format	Beskrivning
    .mbox	Gmail/Outlook e-postexport
    .zip	Komprimerad fil med .mbox-filer

Filnamnskonvention:

*socialt*.mbox → Sociala mail

*kampanjer*.mbox → Kampanjmail


