---
layout: page
title: Forberedelse til teknisk implementering
permalink: /komigang/tekniskimplementering/
---

                   <img width="400" height="460" alt="image" src="https://github.com/user-attachments/assets/f5317e82-75f1-47b0-afdf-ebbcab280601" />

Der er et par ting, som I allerede nu kan sætte gang i, som bringer jer tættere på at kunne implementere FleetOptimiser. Blandt andet har FleetOptimiser brug for data fra det system, som indsamler GPS-data fra jeres køretøjer, f.eks. jeres flådestyringssystem. Derfor skal der laves en integration via flådestyringssytemets API, hvorfra data kan trækkes ud.
Nedenfor finder I en oversigt over de ting der er brug for, og som I kan sætte i gang nu, for at blive klar til den tekniske implementering.

To do 1: Fremskaf dokumentation på API fra flådestyringsleverandør*
---

Droids Agency, der udvikler og drifter FleetOptimiser, har brug for at vide, hvordan jeres flådestyringssystems API er bygget op, og hvilke oplysninger/felter FleetOptimiser skal spørge efter når der skal trækkes data. De har brug for dokumentation på API for at kunne lave en god og stabil integration mellem FleetOptimiser og jeres flådestyringssystem.
*Bruger I Mileage Book, Fleet Complete, Skyhost eller Clevertrack som leverandør, behøver I ikke at fremskaffe dokumentation, da FleetOptimiser allerede har integrationer til disse flådestyringssystemer.

To do 2: Fremskaf API-nøgle til kontoen/de konti hvorfra der skal trækkes data
---

API-nøglen kan ofte findes i flådestyringssystemet under indstillinger for kontoen. Ellers kan jeres flådestyringsleverandør helt sikkert hjælpe med at generere en API-nøgle til jer.
Eksempel på hvordan en API-nøgle kan se ud: gWCqezwlerkMIfu5hItQJ2Sg/Wc5Sk1tzltChi4kaHQdqNu1


To do 3: Kontakt jeres interne GDPR-ansvarlige
---

Det er en god idé at kontakte jeres informationssikkerheds-/GDPR-ansvarlige allerede nu og orientere om den igangværende proces med anskaffelsen af FleetOptimiser. På den måde er de klar til at hjælpe jer med at få indgået en databehandleraftale, når I kommer dertil.
Vi har samlet de vigtigste pointer til den indledende dialog med med jeres GDPR-ansvarlige herunder:
•	FleetOptimiser er hostet på en cloudløsning i Tyskland - dvs. ingen dataoverførsel til usikre tredjelande. Droids Agency bruger en dansk underleverandør af serverhosting, Servicepoint, som køber serverkapaciteten i Tyskland
•	Der behandles udelukkende alm. personoplysninger i FleetOptimiser. Én gang i døgnet trækker FleetOptimiser nye GPS-data fra flådestyringssystemet, som behandles i max 10 sekunder. Herefter slettes de rå data permanent, og tilbage er kun de mest nødvendige (ikke-følsomme) data der skal til for at FleetOptimiser kan fungere
•	Der er udarbejdet en databehandleraftale i Datatilsynets skabelon, en konsekvensanalyse (DPIA) i KL og Kammeradvokatens skabelon til AI-løsninger, databeskrivelse og risikovurdering. Alt dette materiale udleveres fra FleetOptimisers sekretariat, hvis I beslutter jer for at implementere løsningen
•	Ovenstående materiale, tekniske løsninger og foranstaltninger bygger på tre års overvejelser omkring informationssikkerheden i FleetOptimiser. Vi er ret godt tilfredse med resultatet hvis vi selv skal sige det ;-)

To do 4: Få overblik over metadata på køretøjerne
---

Udover GPS-data fra jeres flådestyringssystem, har FleetOptimiser også brug for nogle metadata på køretøjerne for at virke. Begynd allerede nu at få overblik over om I har metadata på bilerne og få udfyldt det i jeres flådestyringssystem de steder, hvor det eventuelt mangler.
For at virke skal FleetOptimiser som minimum have følgende metadata:

•	Køretøjstype (fossilbil, elbil, cykel, elcykel)

•	Drivmiddel (benzin, diesel, el, hybrid, plug-in hybrid

•	Drivmiddelforbrug, km/L eller Wh/km

•	CO2-udledning g/km

•	Lokation - bilens hjemlokation 

•	Leasingperiode, start- og slutdato, hvis jeres biler er leaset
