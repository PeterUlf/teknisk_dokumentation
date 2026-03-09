Teknisk dokumentation – [Projektets navn]

Om projektet

Dette projekt er lavet som en del af Tema 8.
Vi har lavet et dynamisk website med HTML, CSS og JavaScript, hvor indholdet bliver hentet fra et API.

Sitet består af flere sider, hvor brugeren kan:
• se en liste med indhold
• klikke sig videre til en detaljeside
• bruge filtrering
• udfylde en formular

Forklaring

Denne del forklarer kort, hvad projektet er, og hvad det kan. Ideen er, at en underviser eller censor hurtigt skal kunne forstå, hvad gruppen har bygget, uden først at læse al koden.

Links
• GitHub repository: [indsæt link]
• GitHub Pages: [indsæt link]
• Figma: [indsæt link]
• Trello: [indsæt link]

Forklaring

Her samler vi de vigtigste links til projektet. Det gør det nemt at finde både kode, live version og procesmateriale.

⸻

Struktur i projektet

Projektet er opdelt i HTML, CSS og JavaScript-filer.

project/
├── index.html
├── productlist.html
├── productdetails.html
├── form.html
├── css/
│ └── style.css
├── js/
│ ├── index.js
│ ├── productlist.js
│ ├── productdetails.js
│ └── form.js
└── README.md

Kort forklaring
• index.html er forsiden
• productlist.html viser en liste med data fra API’et
• productdetails.html viser detaljer om et valgt produkt
• form.html indeholder formularen
• style.css styrer designet
• JavaScript-filerne styrer det dynamiske indhold på de forskellige sider

Forklaring

Det her afsnit viser, hvordan projektet er bygget op i mapper og filer. Det hjælper med at skabe overblik og viser, at gruppen har arbejdet struktureret.

⸻

Hvordan koden fungerer

Vi har opdelt JavaScript, så hver side har sin egen fil.

index.js

Bruges på forsiden.
Her bliver indhold vist dynamisk, fx links eller kategorier.

Forklaring
Ved at have en separat fil til forsiden bliver koden mere overskuelig. Det betyder også, at man ikke blander kode til forsiden sammen med kode til de andre sider.

productlist.js

Henter data fra API’et og viser en liste med produkter på siden.

Eksempel på det flow vi bruger:

Siden loader
↓
JavaScript kører
↓
Data hentes fra API
↓
Data bliver gennemgået med loop
↓
HTML bliver indsat i DOM'en
↓
Brugeren kan klikke på et produkt

Forklaring
Denne fil er vigtig, fordi det er her data bliver hentet og vist. Flowet viser rækkefølgen i, hvordan siden går fra tom HTML til en side med rigtige data.

productdetails.js

Bruges til detaljesiden.
Den læser et id fra URL’en og henter derefter det rigtige produkt fra API’et.

Forklaring
Det gør det muligt at genbruge den samme HTML-side til mange produkter. I stedet for at lave én side per produkt, bruger vi ét id i URL’en til at vise det rigtige indhold.

form.js

Styrer formularen og validering af inputfelter.

Forklaring
Denne fil bruges til at sikre, at brugeren udfylder formularen korrekt. Det gør formularen mere brugervenlig og mindsker fejl.

⸻

Navngivning

Vi har prøvet at navngive vores filer, variabler og funktioner så tydeligt som muligt.

Eksempler på variabler

const productContainer
const productId
const selectedCategory

Eksempler på funktioner

fetchProducts()
showProducts()
showProductDetails()
validateForm()

Vi har brugt camelCase i JavaScript, fordi det gør koden mere ensartet og lettere at læse.

Forklaring

Gode navne gør det lettere at forstå koden, både for os selv og for andre. Hvis en variabel eller funktion hedder noget tydeligt, er det nemmere at se, hvad den bruges til.

⸻

Kommentarer i koden

Vi har kommenteret de steder i koden, hvor det giver mening.
Fx ved funktioner, fetch-kald og steder hvor der sker DOM-manipulation.

Eksempel:

// Henter produkter fra API'et
async function fetchProducts() {
const res = await fetch(apiURL);
const data = await res.json();
return data.products;
}

Vi har prøvet ikke at skrive kommentarer til helt åbenlyse ting, men kun dér hvor det hjælper forståelsen.

Forklaring

Kommentarer skal hjælpe med at forklare det, der ikke er helt oplagt. For mange kommentarer kan gøre koden rodet, men de rigtige kommentarer gør det lettere at følge logikken.

⸻

Data og JSON-struktur

Vi henter data fra et API i JSON-format.

Et objekt kan fx se sådan ud:

{
"id": 1,
"title": "Produktnavn",
"description": "Kort beskrivelse",
"category": "beauty",
"price": 99,
"thumbnail": "billede.jpg"
}

De felter vi især bruger, er:
• id
• title
• description
• category
• price
• thumbnail

Vi bruger id til at sende brugeren videre til detaljesiden, og de andre felter bliver vist i listen eller på produktets egen side.

Forklaring

Det her afsnit viser, hvordan data ser ud, før det bliver vist på websitet. Det er vigtigt, fordi hele det dynamiske site bygger på, at vi forstår strukturen i de data, vi henter.

⸻

Formular og validering

Vi har lavet en formular, hvor brugeren kan indtaste oplysninger.

Vi har brugt HTML-validering som fx:
• required
• type="email"
• type="number"

Det gør, at brugeren ikke kan sende formularen, hvis felterne ikke er udfyldt korrekt.

Forklaring

Validering er vigtig, fordi den hjælper brugeren med at udfylde formularen rigtigt. Samtidig sikrer den, at de data, der bliver sendt, er mere brugbare.

⸻

Git og branches

Vi har brugt GitHub til at samarbejde om projektet.

Vi har arbejdet med branches, så vi ikke sad og ændrede i det samme på samme tid.

Eksempler på branches:
• feature-forside
• feature-produktliste
• feature-detaljeside
• feature-formular

Vores workflow har været: 1. lave en branch 2. kode en feature 3. committe ændringer 4. pushe til GitHub 5. merge til main når det virkede

Det gjorde det nemmere at holde styr på, hvem der lavede hvad.

Forklaring

Branches gør samarbejdet mere sikkert og overskueligt. På den måde kan flere arbejde samtidig, uden at ødelægge hinandens kode i main.

⸻

Bæredygtighed

Vi har tænkt bæredygtighed ind i projektet ved at holde løsningen forholdsvis enkel.

Det har vi gjort ved fx at:
• bruge få og lette filer
• undgå tunge frameworks
• genbruge kode
• optimere billeder og indhold

Forklaring

Et lettere website kræver færre ressourcer at loade og bruge. Det gør ikke projektet perfekt bæredygtigt, men det viser, at vi har tænkt over digitale ressourcer.

⸻

Udfordringer undervejs

En af vores udfordringer var at få data fra API’et vist korrekt på siderne.
Det var også lidt svært at få id med videre i URL’en til detaljesiden.

Vi løste det ved at:
• console.logge data undervejs
• teste fetch-kald separat
• bruge URLSearchParams
• dele opgaverne mere tydeligt i gruppen

Forklaring

Det her afsnit viser, hvad vi lærte undervejs. Det er vigtigt, fordi teknisk dokumentation ikke kun handler om det færdige produkt, men også om processen bag.

⸻

Konklusion

Vi har lavet et dynamisk website, hvor indhold bliver hentet fra et API og vist på flere sider.
Projektet har givet os erfaring med JavaScript, fetch, DOM-manipulation, formularer og samarbejde i GitHub.

Forklaring

Konklusionen samler op på, hvad projektet viser, og hvad gruppen har arbejdet med. Den giver en kort afslutning på dokumentationen.

⸻

Mulige forbedringer

Hvis vi skulle arbejde videre med projektet, kunne vi forbedre det ved at tilføje:
• søgefunktion
• flere filtre
• bedre error handling
• loading state
• mere avanceret formular
• bedre responsivt design

Forklaring

Her viser vi, at vi kan se projektets begrænsninger og tænke videre. Det viser refleksion og forståelse for, hvordan løsningen kunne udvikles.

⸻

Gruppemedlemmer
• [navn 1]
• [navn 2]
• [navn 3]
• [navn 4]

Forklaring

Til sidst skriver vi, hvem der har lavet projektet. Det gør dokumentationen komplet og tydelig.
