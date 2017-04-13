---
title: "&lt;dns&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;dns&gt;
Gibt die erwartete Identität des Servers an.  Diese Identität ist für den X.509\-Zertifikat\-Authentifizierungsmodus gültig, wenn das Serverzertifikat eine DNS mit dem gleichen Wert enthält.  Sie ist auch für den Windows\-Authentifizierungsmodus gültig, wenn der SPN den gleichen Wert hat.  
  
 Weitere Informationen zum Festlegen der Elementwerte finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Syntax  
  
```  
  
<dns value = "String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Wert|Der DNS des Zertifikats.  DNS ist ein standardmäßiges Protokoll, das verwendet wird, um Computer in einem IP\-basierten Netzwerk zu suchen.  Die Benutzer können sich Anzeigenamen, beispielsweise [http:\/\/go.microsoft.com\/fwlink\/?prd\=10929](http://go.microsoft.com/fwlink/?prd=10929) oder [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=96165](http://go.microsoft.com/fwlink/?LinkID=96165), leichter merken als zahlenbasierte Adressen, beispielsweise 207.46.131.137.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Gibt die Identität des Diensts für die Authentifizierung durch den Client an.|  
  
## Beispiel  
 Der folgende Konfigurationscode gibt den DNS eines X.509\-Zertifikats an, das für die Authentifizierung eines Servers verwendet wird.  
  
```  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.DnsEndpointIdentity>   
 [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<Identität\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)