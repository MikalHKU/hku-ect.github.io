---
title: "SoapShopSessie #1 BLOG"
excerpt: "Aan de slag met Kunstmatige intelligentie"
author: Than van Nispen
tags: 
  - artificial intelligence
  - SoapShopSessie
  - machine learning
---

# SoapShopSessie #1 BLOG, plus 'making of'

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


# making of SoapShopSessie #1 
De opzet van de SoapShopSessie en gebruik van applicaties was niet mogelijk geweest zonder de inspiratie en vele bijdragen van Gene Kogan & Andreas Refsgaard (zie oa het verslag van Report ML4A @ CCU van Juni 2018) en Rebecca Fiebrink (zie de overige links naar cursussen ed), alsmede Christobal Valenzuela van Runway, maar vooral de bijdragen van collega’s van het ECT, Machiel Veltkamp en Arnaud Loonstra.
In het volgende gedeelte worden de verschillende bouwstenen, alsmede applicaties toegelicht om de SoapShopSessie als het ware te kunnen reproduceren. De beschreven toepassingen zijn terug te vinden op de GitHub van het ECT via : https://github.com/hku-ect/SoapShopSessions 

## Smile or Else
Deze processing-applicatie is een lichte aanpassing op Andreas Refsgaard's PhotoBooth toepassing, met vooral extra visuals bovenop de bestaande functionaliteit.
De applicatie reageert op OSC berichten "/wek/outputs" waarbij de geaccepteerde waardes 1 & 2 zijn.
De waardes worden gegenereerd door een combinatie van FaceOSC (als feature extractor van de camera-input) in combinatie met Wekinator. 
Wekinator is daarbij getraind op neutrale (en andere) gezichten (voor waarde "1") en specifiek op verschillende lachende gezichten (value 2)
Op deze manier kan deze applicatie een foto schieten wanneer iemand lacht (smile) en blijft de 'Photo Booth' 'stil' bij andere gelaatsuitdrukkingen (or else :) 
Webcam 
FaceOSC (een OpenFrameworks applicatie, welke gebruik van OpenCV bibliotheek)
Wekinator 
Processing-toepassing om webcam te laten zien, alsmede foto te schieten en te laten zien



## Pong
Voor Pong werd een bestaande toepassing (van Limulo.net ) aangepast, zodat deze geschikt werd voor een koppeling aan een OSC-stroom vanuit Wekinator en derhalve over een netwerk gespeeld kan worden.
In Wekinator stelde het team wat ging spelen als OSC output dan in : "/wek/player1" resp. "/wek/player2" voor variabele oscTeam1, of oscTeam2 

 

## Style Transfer 



# Links

Meer informatie op:

* Playlist met AI muziek bij binnenkomst: ( https://youtu.be/TqH6ionF94I ) 
* handige links rondom de SoapShopSessie : ( http://home.hku.nl/~than.vannispen/soapshop-nr-1/ ) 
* algemeen worden voor HKU medewerkers en studenten relevante ontwikkelingen bijgehouden op: ( https://projectcamp.us/projects/ai-machine-learning/items ) 




