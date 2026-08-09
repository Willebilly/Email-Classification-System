# Email-Classification-System

## **AI-Powered Social vs Promotion Email Classifier**

Syfte/Mål

Detta projekt syftar till att skapa ett AI-system som automatiskt klassificerar e-postmeddelanden som antingen sociala (personliga meddelanden, inbjudningar) eller kampanjer (reklam, nyhetsbrev, erbjudanden). Systemet är byggt för användare som är osäkra på om ett mail är socialt eller en kampanj, och vill ha ett snabbt och pålitligt svar utan att behöva gissa.

Målet är att användaren ska behöva göra så lite som möjligt, bara mata in ett mail och få en omedelbar klassificering med hög tillförlitlighet. För dig som är osäker på om ett mail är en social notifikation eller reklam.

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


#### **INFO:** 
För extra hjälp, se README-filen eller kör notebooken cell för cell för att förstå processen.

En CSV-fil med förutsägelsehistorik skapas i mappen exports/ som kan användas för vidare analys.

En JSON-fil med sammanfattande statistik skapas i samma mapp, där du kan se modellprestanda och nyckeltal.

Ett exempel dataset med 100 kampanj mail & 100 social mail medföljer om du endast vill testa applikationen.

---
## Systemkrav
***Minimala krav***
    
    Operativsystem:  Windows 10, macOS 10.15+, eller Linux (Ubuntu 20.04+)
    Python:	         3.8 eller högre
    RAM:	         8 GB minimum (16 GB rekommenderas)
    Lagring:	     2 GB ledigt utrymme
    Internet:	     Krävs för NLTK-nedladdningar och Google Colab

***Programvara***

    Google Colab:	 Primär miljö 
    Python 3.8+:	 Alternativ lokal körning
    PowerBI Desktop: Dashboard-visualisering (valfritt)
    
***Dataset-krav***

    .mbox	Gmail/Outlook e-postexport
    .zip	Komprimerad fil med .mbox-filer

Filnamnskonvention:

*socialt*.mbox → Sociala mail

*kampanjer*.mbox → Kampanjmail

---

## **Instruktioner för körning**

1. Ladda ner filerna från detta repository
2. Öppna Google Colab
3. Skapa en mapp där applikation och extra filler läggs
4. Klicka "File" --> "Upload notebook". [ Välj *SocialOrPromotion_AI_project-WillJohnFri.ipynb* ]
5. Ladda upp ***requirements.txt***
6. Ladda ner eget dataset: Gå till *google takeout*. Av markera allt förutom gmail. Välj två flikarna för socialt och kampanj. Ladda ner dessa som `.mbox` filer.
7. Kör Cell 1 - 3. Dessa sätter upp miljön för att följande celler ska fungera.

> OBS: För att detta ska fungera måste du acceptera att filen får åtkomst till din google drive och att den tillåts göra ändringar i den. Exempelvis: skapa mappar, filer, redigera filer. 

9. Kör Cell 4, här laddar du upp ditt dataset, `ZIP` fil med `.mbox` filer. (Kan ta lång tid beroende på datasetets storlek).
10. Kör Cell 5, den rensar HTML, tar bort misstänkta ord, tokeniserar och lemmatiserar. (Kan ta lång tid beroende på datasetets storlek).
11. Kör Cell 6, den extraherar features och skapar numeriska egenskaper från text.
12. Kör Cell 7 - 10, dessa tränar ML modellerna: Random Forest & XGBoost.
13. Kör Cell 11 - 11.5 jämför modellerna och optimizerar XGBoost.
14. Kör Cell 12, nu kan du testa med dina egna mail och få en klassificering.
15. Kör Cell 13 för att exportera resultatet av applikationens körning. Detta kan sedan användas i Power BI, (filer sparas i `exports/` mappen).

---

## Skärmbilder

När allt fungerar bör du få följande resultat:

**Cell 9** Random Forest resultat:

<img width="464" height="553" alt="image" src="https://github.com/user-attachments/assets/33edaa1e-7f4c-41a4-ac8c-68311f4f3acd" />



**Cell 10** XGBoost Resultat:

<img width="488" height="697" alt="image" src="https://github.com/user-attachments/assets/ec6f115e-1a3f-4f0b-8c1c-68e7bb99e0f7" />

**Cell 12** Interaktiv Förutsägelse:

<img width="777" height="698" alt="image" src="https://github.com/user-attachments/assets/fc5354ca-a357-4830-b78e-3821f57bed70" />
<img width="756" height="651" alt="image" src="https://github.com/user-attachments/assets/6e282e38-4933-49ec-96f1-899cb74a85a7" />


---

### **Power BI Dashboard exempel:**

<img width="751" height="597" alt="image" src="https://github.com/user-attachments/assets/53910553-63fe-4741-ab30-18b89cff42ac" />

<img width="672" height="629" alt="image" src="https://github.com/user-attachments/assets/c6b37d24-8aa5-44c8-a0e4-1f2973f7c956" />

---

## När bör man använda E-postklassificeraren?

#### Scenario: "Vanlig användare med 100+ mail om dagen"
Problemet:

- Svårt att hinna läsa alla mail
- Viktiga sociala mail drunknar i reklam
- Manuell sortering tar för mycket tid

Praktisk nytta:

- Arbete: Prioritera mail från kollegor före nyhetsbrev
- Privat: Hitta inbjudningar och personliga meddelanden snabbt
- Tid: spara tid


#### Scenario: "Säkerhetsteam som övervakar phishing"
Problemet:

- Phishing-mail förkläds ofta som "sociala" meddelanden
- Svårt att manuellt identifiera alla hot
- Kritiska säkerhetsmail kan missas

Praktisk nytta:

- Hotdetektering: Upptäck avvikande mailmönster
- Snabba insatser: Prioritera säkerhetshot
- Översikt: Se trender i mailtyper över tid

### *Det verkliga värdet!*

A. Spara tid --> Sorterar automatiskt

B. Öka produktivitet --> Fokus på rätt saker

C. Minska stress --> Ingen gissning kring mail

D. Fatta bättre beslut --> Insikter från data

---

## **Varför Random Forest & XGBoost?**

**De är exceptionella för textklassificering med TF-IDF** då de hanterar högdimensionell, gles data. TF-IDF skapar upp till 10 000+ features där de flesta värden är noll, (sparsam data). 
- *Random Forest* fungerar på så sätt att vid varje delning av ett beslutsträd väljs endast en slumpmässig delmängd av features. Det gör att trädet inte påverkas av alla tusentals nollor. Modellen använder dessutom bagging för att minska överanpassning.
- *XGBoost* har en inbyggd "sparsity-aware" algoritm som optimerar för glesa matriser och ignorerar nollvärden effektivt. XGBoost har inbyggd regularisering (L1/L2) som också förhindrar överanpassning.

**De är snabba att träna och enkla att distribuera**. I Google Colab är träningstiden viktig! Båda modellerna är optimerade och kan sparas med pickle. De kräver ingen GPU och kan göra prediktioner på millisekunder, vilket möjliggör realtidsklassificering av användarnas egna mejl i Cell 12.

#### Random Forest och XGBoost valdes eftersom de är branschstandard för textklassificering, hanterar gles TF-IDF-data utan krångel, ger insyn i modellens beslut, är snabba att träna och gör det möjligt att upptäcka dataläckage vilket var *avgörande* i detta projekt.


--- 

## Checklista
Innan du använder applikationen, kontrollera:

□ Python 3.8+ installerad

□ Google Drive monterad (Colab)

□ Dataset i .mbox-format i .zip

□ NLTK-data nedladdad

□ Modeller tränade framgångsrikt

□ Exporter genererade för PowerBI

Lycka till med körningen :D 
