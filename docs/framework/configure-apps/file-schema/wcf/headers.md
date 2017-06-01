---
title: "&lt;Kopfzeilen&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;Kopfzeilen&gt;
Ein Endpunkt kann neben seinem Basis\-URI von einem oder mehreren SOAP\-Headern adressiert werden.  Dies ist beispielsweise in SOAP\-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP\-Header einfügen, die sich an Vermittler richten.  Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.  Einträge in der Endpunktheader\-Auflistung sind benutzerdefinierte XML\-Elemente.  Jedes Element muss ein wohlgeformtes XML\-Element sein.  
  
## Syntax  
  
```  
  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|Region||  
|Member||  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Endpunkt \(endpoint\)\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Konfiguriert unterschiedliche Endpunkttypen.|  
  
## Hinweise  
 Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.  Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>   
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>   
 [Endpunkte: Adressen, Bindungen und Verträge](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)