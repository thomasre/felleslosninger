-----

layout: default  
title: PullRequest  
headtitle: Begrepskatalog for Sikker digital post -  
group: transportlag

id: PullRequest

next: Receipt  
prev: SignalMessage

-----

  - Identifikator  
    “http://begrep.difi.no{{ page.url | remove:”.html"
    }}":{{page.title}}
  - Term  
    {{page.title}}
  - Definisjon  
    Forespørsel om å få sendt en melding
  - Datatype  
    complexType
  - Kilde  
    [ebMS 3.0](http://docs.oasis-open.org/ebxml-msg/ebms/v3.0/core/ebms-header-3_0-200704.xsd)

#### Egenskaper

Forespørsel om å få tilsendt en melding. Må angi
[mpc](../UserMessage/mpc) attributten til å identifisere hvilken
organisasjon en ønsker å hente meldinger for.

| Identifikator | Type                      | Kardinalitet | Kommentar |
| ------------- | ------------------------- | ------------ | --------- |
| mpc           | [mpc](../UserMessage/mpc) | 1..1         |           |

#### Xml eksempel

``` brush: xml; toolbar: false
    <eb:PullRequest mpc="normal:"/>
```