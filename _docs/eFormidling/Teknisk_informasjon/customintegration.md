---
title: Egen integrasjon mot eFormidling
description: Beskrivelse av hvordan man kan ta i bruk DPO via egenutviklet kode
summary: ""
permalink: eformidling_nm_customintegration.html
product: eFormidling
sidebar: eformidling_technical_sidebar
---

## Capability oppslag

<div class="mermaid">

graph LR  
  subgraph DigDir
    Maskinporten[Maskinporten]
    sr[SR]
  end
  subgraph API-konsument
     klient[Klient]
  end
  Maskinporten -->|2.utsteder token med tildelt scope|klient
  klient -->|1. forspør tilgang til scope|Maskinporten
  klient -->|3.bruker token mot|sr

</div>


SR response
```json
{% include /eformidling/nextmove/sr_response.json %}
```


| Identifier | Type        | Maskinporten scope  | Wsdl| Tjenestebeskrivelse |
| -----------|-------------|---------------------|-----|---------------------|
| DPO        | SOAP        | move/dpo.read       | [BrokerServiceExternalBasic](https://www.altinn.no/ServiceEngineExternal/BrokerServiceExternalBasic.svc?wsdl) <br> [BrokerServiceExternalBasicStreamed](https://www.altinn.no/ServiceEngineExternal/BrokerServiceExternalBasicStreamed.svc?wsdl) |[Brokerservice dokumentasjon](https://altinn.github.io/docs/api/soap/grensesnitt/#brokerservice-formidlingstjenester-ws) |
 		

## Meldingsoppbygging

Eksempler på hvordan meldingene bygges opp

[Kryptering](https://github.com/difi/move-integrasjonspunkt/blob/master/dokumentpakking/src/main/java/no/difi/meldingsutveksling/dokumentpakking/service/CmsUtil.java)


[Maskinporten](https://github.com/difi/move-integrasjonspunkt/blob/master/security/src/main/java/no/difi/meldingsutveksling/auth/OidcTokenClient.java)


[Asic](https://github.com/difi/move-integrasjonspunkt/blob/master/integrasjonspunkt/src/main/java/no/difi/meldingsutveksling/nextmove/AsicHandler.java)

## Kvitteringsmeldinger og logging