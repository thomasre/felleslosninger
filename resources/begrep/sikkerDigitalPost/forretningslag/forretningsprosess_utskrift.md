-----

layout: default  
title: Sending av post til utskrift og forsendelse  
headtitle: Sikker digital post  
group: forretningslag

id: Forretningslag/Forretningsprosess\_utskrift

next: Forretningslag/Forretningsprosess\_kvittering

-----

## Prosess for sending av papir post

[Meldingen](../meldinger/) i Sikker digital post flyter mellom
[Aktørene](Aktorer) slik det beskrives i flytdiagrammet under.

Ovordnet er meldingsflyten slik:

1.  Avsender\[1\] sender en [Digital
    postmelding](../meldinger/DigitalPostMelding) via Meldingsformidler
    til Utskriftstjeneste
2.  Postkasse sender en eller fler
    [Kvitteringsmeldinger](../meldinger/KvitteringsMelding) til
    Meldingsformidler
3.  Avsender henter
    [Kvitteringsmeldinger](../meldinger/KvitteringsMelding) fra
    Meldingsformidler

(Meldinger prefikset **eb:** i diagrammet tilhører transportlaget, men
er tatt med for å vise sammenhengen)

[![Prosess for sending av digital
post](prosess_for_sending_av_papirpost.png
"Prosess for sending av digital post")](prosess_for_sending_av_papirpost.png)

| Prosess                                                       | Fra                          | Til                          | Beskrivelse                                                                                                                                                                         |
| ------------------------------------------------------------- | ---------------------------- | ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [DigitalPostmelding](../meldinger/DigitalPostMelding)         | [Avsender](Aktorer)          | [Meldingsformidler](Aktorer) | Avsender sender alltid sine meldinger til meldingsformidler. Transportkvittering fra meldingsformidler indikerer at denne har tatt over ansvaret for videre formidling av meldingen |
| DigitalPostmelding                                            | [Meldingsformidler](Aktorer) | [Utskriftstjeneste](Aktorer) | Meldingsformidler mellomlagrer meldingen inntil Utskriftstjeneste har returnert en transportkvittering.                                                                             |
| [MottaksKvittering](../meldinger/MottaksKvittering) \[2\]     | [Utskriftstjeneste](Aktorer) | [Meldingsformidler](Aktorer) | Utskriftstjeneste sender en [MottaksKvittering](../meldinger/MottaksKvittering) for å signalisere at utskriftstjenesten har mottatt og lagt meldingen klar til behandling.          |
| [LeveringsKvittering](../meldinger/LeveringsKvittering) \[3\] | [Utskriftstjeneste](Aktorer) | [Meldingsformidler](Aktorer) | Utskriftstjeneste sender en [LeveringsKvittering](../meldinger/LeveringsKvittering) for å signalisere at posten er skrevet ut, konvolutert og postlagt.                             |
| [ReturpostKvittering](../meldinger/ReturpostKvittering) \[4\] | [Utskriftstjeneste](Aktorer) | [Meldingsformidler](Aktorer) | Utskriftstjeneste sender en [ReturpostKvittering](../meldinger/ReturpostKvittering) for å signalisere at posten har kommet tilbake og ikke kan leveres til innbygger.               |
| HentKvittering                                                | [Avsender](Aktorer)          | [Meldingsformidler](Aktorer) | Avsender sender forespørsel til Meldingsformidler om å få levert ventende kvitteringer\[5\]                                                                                         |

1.  Avsender bør også ha et aktivt forhold til statusen til en melding.
    Meldingsflytdiagrammet kan med fordel ses i sammenheng med
    [tilstandsdiagrammet](avsender_tilstanddiagram) for sikker digital
    post.

2.  [Mottakskvittering](../meldinger/Mottakskvittering) sendes så fort
    utskriftstjenesten har mottatt
    [DigitalPostmelding](../meldinger/DigitalPostMelding) og lagt den i
    kø for utskrift. Altså kort tid etter at
    [DigitalPostmelding](../meldinger/DigitalPostMelding) er sendt.

3.  Utskriftstjenesten samler sammen alle utskrifter til en
    utskriftsjobb hver dag. Når dette er fullført og posten er postlagt
    vil utskriftstjenesten sende over
    [LeveringsKvittering](../meldinger/LeveringsKvittering). Disse vil
    dermed komme tilbake i daglige puljer til Avsender.

4.  [ReturPostkvittering](../meldinger/ReturPostkvittering) blir kun
    dersom returpost håndtering er bestilt i
    [DigitalPostmelding](../meldinger/DigitalPostMelding). Returpost som
    er fysisk ødelagt slik at ikke posten kan identifiseres vil bli
    levert til returadressen oppgitt så lenge denne er leselig.

5.  Dette kan være alle typer kvitteringer, ikke bare Mottakskvitter og
    LeveringsKvittering