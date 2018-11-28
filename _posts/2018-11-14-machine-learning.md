---
title: "SoapShopSessie #1 BLOG, plus 'making of'"
excerpt: "Aan de slag met Kunstmatige intelligentie"
author: Than van Nispen

header:
  overlay_image: /blog/assets/images/smile-or-else-mosaic-ANIMATION.gif
  image_description: "smile-or-else-mosaic-ANIMATION"
  teaser: /blog/assets/images/smile-or-else-mosaic-ANIMATION.gif

tags: 
  - artificial intelligence
  - SoapShopSessie
  - machine learning
  
gallery:
  - url: /blog/assets/images/smile-or-else-mosaic-ANIMATION.gif
    image_path: /blog/assets/images/smile-or-else-mosaic-ANIMATION.gif
    alt: "smile-or-else-mosaic-ANIMATION"
    title: "smile-or-else-mosaic-ANIMATION"
  - url: /blog/assets/images/Smile-or-Else-diagram.png
    image_path: /blog/assets/images/Smile-or-Else-diagram.png
    alt: ""
    title: ""
  - url: /blog/assets/images/IMG_8264-Than-Smile-or-Else.JPG
    image_path: /blog/assets/images/IMG_8264-Than-Smile-or-Else.JPG
    alt: "Smile-or-Else demo"
    title: "Smile-or-Else demo"

---

Het Expertisecentrum Creatieve Technologie (ECT) organiseert sinds studiejaar 2018/2019 maandelijks een zogeheten SoapShopSessie rond een bepaald thema dat raakt aan technologie en kunsten. Het is deels een open podium (soapbox) en deels een workshop, vandaar ‘SoapShop’. Deelnemers zijn medewerkers van het centrum, andere HKU-medewerkers, gemotiveerde studenten en eventueel externen.
De eerste SoapShopSessie, #1, liet zich ‘Aan de slag met Kunstmatige intelligentie’ noemen.

Direct bij binnenkomst voor de koffie & thee, kwam elke deelnemer in contact en aanraking met een eenvoudige toepassing van machine learning: “Smile or Else” door Veltkamp & van Nispen. Een beeldscherm direct bij de ingang opgesteld fungeerde als een soort van spiegel met de tekst “Smile or Else” in beeld. Bij een glimlach werd automatisch een foto geschoten, andere gelaatsuitdrukkingen deden ‘niets’...
In een korte inleiding met de meest basale informatie om aan de slag te kunnen, werd ook deze Smile-or-Else-installatie uitgeplozen en kwamen zodoende onder ander classificatie-algoritmes en ‘computer visie’-bibliotheken als feature extractor voor gefilterde data aan bod. Tevens was het een eenvoudige illustratie van de kracht van het programma Wekinator, een ‘suite’ van Machine Learning Algoritmes, gebruikersvriendelijk verpakt in een applicatie voor ‘creatives’ door Rebecca Fiebrink.
Na de korte inleiding werd er in teamverband voorbereid om een potje (sound) Pong te spelen! 
Pong kennen we als een spel uit de jaren zeventig waarbij twee spelers een “|” verticaal balkje op een neer bewegen, om zo een vierkantje terug te kaatsen. In deze variatie werd het spel gespeeld door het balkje middels geluiden en klanken aan te sturen. Elk team had een korte tijd om een kunstmatige intelligentie te trainen op verschillende geluiden.
Het werd een bijzondere ervaring om de verschillende teams met verschillende strategieën aan het werk te zien (en horen) gaan. Een team wist gedurende het verloop van het spel hun algoritmes in Wekinator nog van nieuwe trainings-data te voorzien en daarmee betere resultaten te boeken!
De winnaars van de eerste ronde mochten tegen elkaar om de eer strijden door hun zojuist getrainde k-Nearest Neighbour algoritme nog wat bij te stellen (technisch gezien de standaard van k=1 naar k=3 omzetten, waardoor er betere resultaten geboekt konden worden èn er beter begrip voor de instellingen ontstond).
In het tweede deel van de ochtend werden de deelnemers uitgedaagd om ‘iets nieuws’ te ontwerpen met kunstmatige intelligentie middels een aantal van de aangeboden ‘input’-toepassingen richting een van de half-fabrikaten aan outputs.
Zo gingen sommige deelnemers aan de slag met emoties in gezichtsherkenning, anderen met een chat-geschiedenis van zichzelf om een chatbot mee te ontwerpen en natuurlijk ‘Dynamic Time Warping’, oftewel partoon-herkenning in de tijd (waarbij gedacht kan worden aan gesture control). 
Als afsluiter kregen de deelnemers de foto van zichzelf (lachend) toegestuurd welke middels een Style Transfer model (domein van deep learning) in verschillende stijlen was gemonteerd.

![Smile-or-Else-style-transfer-souvenir](/blog/assets/images/smile-or-else-mosaic-ANIMATION.gif)


# making of SoapShopSessie #1 
De opzet van de SoapShopSessie en gebruik van applicaties was niet mogelijk geweest zonder de inspiratie en vele bijdragen van Gene Kogan & Andreas Refsgaard (zie oa het verslag van Report ML4A @ CCU van Juni 2018) en Rebecca Fiebrink (zie de overige links naar cursussen ed), alsmede Christobal Valenzuela van Runway, maar vooral de bijdragen van collega’s van het ECT, Machiel Veltkamp en Arnaud Loonstra.
In het volgende gedeelte worden de verschillende bouwstenen, alsmede applicaties toegelicht om de SoapShopSessie als het ware te kunnen reproduceren. De beschreven toepassingen zijn terug te vinden op de GitHub van het ECT via : [SoapShopSession] (https://github.com/hku-ect/SoapShopSessions )

## Smile or Else
Deze processing-applicatie is een lichte aanpassing op Andreas Refsgaard's PhotoBooth toepassing, met vooral extra visuals bovenop de bestaande functionaliteit.
De applicatie reageert op OSC berichten "/wek/outputs" waarbij de geaccepteerde waardes 1 & 2 zijn.
De waardes worden gegenereerd door een combinatie van FaceOSC (als zogeheten "feature extractor" van de camera-input) in combinatie met Wekinator. 
Wekinator is daarbij getraind op neutrale (en andere) gezichten (voor waarde "1") en specifiek op verschillende lachende gezichten (value 2)
Op deze manier kan deze applicatie een foto schieten wanneer iemand lacht (smile) en blijft de 'Photo Booth' 'stil' bij andere gelaatsuitdrukkingen ("or else" :) 
<img src="{{ "/assets/images/Smile-or-Else-diagram.png" | relative_url }}" width="400" class="align-left">

![Smile-or-Else diagram](/blog/assets/images/Smile-or-Else-diagram.png)

In het diagram (zie afbeelding) wordt de installatie uitgelegd als:


1. Webcam als input. De Webcam stuurt 'ruwe videodata' uit.

2. FaceTracker2OSC. FaceTracker2OSC is een OpenFrameworks applicatie, welke gebruik van OpenCV bibliotheek en ingezet wordt als een feature extractor. 
Een feature extractor is te zien als een filter om bepaalde informatie, zoals patronen, te halen uit een bepaalde datastroom, om in dit geval een kunstmatige intelligentie te trainen. Het trainen van een neuraal netwerk op de ruwe video-data zou een veel ingewikkeldere toepassing worden.
Vergelijk alleen al de 640 x 480 pixels resolutie x 3 kanalen aan input (miljoen inputs) met de 136 waardes (68 xy-punten) die de gezichtsdata 'samenvatten'... Daar zijn de in de SoapShop gebruikte kunstmatige intelligentie algoritmes een stuk eenvoudiger en eenduidiger op te trainen.
FaceTracker2OSC is een variatie op FaceOSC en te verkrijgen via [FaceTracker2OSC](https://github.com/genekogan/osc-modules/tree/master/FaceTracker2OSC)
 
3. Wekinator. Wekinator is te zien als een suite aan kunstmatige intelligentie algoritmes, waarbij vrij gemakkelijk en gebruikersvriendelijk verschillende vormen van classificatie- en regressie-algoritmes ingezet kunnen worden om op OSC-date getraind te worden en vervolgens voorspellingen te doen (output) aan de hand van nieuwe data (input).

4. Processing-toepassing "Smile or Else" om webcam te laten zien, alsmede foto te schieten en te laten zien.
Deze processing-applicatie is een lichte aanpassing op Andreas Refsgaard's PhotoBooth toepassing, met vooral extra visuals bovenop de bestaande functionaliteit. 
De applicatie is te verkrijgen via [HKU ECT GitHub](https://github.com/hku-ect/SoapShopSessions/tree/master/Session%231_MachineLearning)

![Smile-or-Else demo](/blog/assets/images/IMG_8264-Than-Smile-or-Else.JPG)


## Pong
Voor Pong werd een bestaande toepassing (van Limulo.net ) aangepast, zodat deze geschikt werd voor een koppeling aan een OSC-stroom vanuit Wekinator en derhalve over een netwerk gespeeld kan worden.
In Wekinator stelde het team wat ging spelen als OSC output dan in : "/wek/player1" resp. "/wek/player2" voor variabele oscTeam1, of oscTeam2 
Zie : https://github.com/hku-ect/SoapShopSessions/tree/master/Session%231_MachineLearning
 

## Style Transfer 
Op een eigen ECT-server werd een zogeheten fast-style-transfer algoritme voorbereid waarbij de afbeeldingen gemaakt door de 'Smile or Else'-applicatie werden 'gestijl-transformeert' middels een voorgetraind convolutie (neuraal) netwerk.

Afbeeldingen kunnen een goede manier zijn om ons verschillende perspectieven te bieden om naar dingen te kijken. Soms leidt het bewerken / toevoegen van  een bepaalde "stijl" aan een bepaalde afbeelding tot iets bijzonders. Met het doel om 'iets nieuws' te creeëren , is relatief recent gewerkt aan het concept van een "Fast Style Transfer", dat werkt met Tensorflow (een specifieke bibliotheek voor Kunstmatige intelligentie).
In de Fast Style Transfer wordt de beschrijving van één afbeelding gecombineerd met de stijl(analyse) van een ander beeld via convolutional neural networks. Fast Style-Transfer voegt stijlen van een aantal beroemde schilderijen toe aan een afbeelding, waardoor het een heel nieuw 'kunstwerk' wordt. De neurale netwerken zijn reeds getraind en in deze SoapShopSessie maakten we gebruik van deze voorgetrainde netwerken, 'modellen' geheten (bestanden met de extensie ckpt, wat staat voor een 'checkpoint' in de training van het netwerk).
Meer informatie over deze techniek is oa te vinden op:
https://www.techleer.com/articles/466-insight-into-fast-style-transfer-in-tensorflow/

Een repository van de fast style transfer network zoals gebruikt in de SoapShopSessie is te vinden op:
https://github.com/lengstrom/fast-style-transfer



# Links

Meer informatie op:

* Playlist met AI muziek bij binnenkomst: https://youtu.be/TqH6ionF94I
* handige links rondom deze specifieke SoapShopSessie, inclusief pdf van de keynote : https://projectcamp.us/projects/ai-machine-learning/items
* algemeen worden voor HKU medewerkers en studenten relevante ontwikkelingen bijgehouden op: https://projectcamp.us/projects/ai-machine-learning/items




