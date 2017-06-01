---
title: "&lt;useRequestHeadersForMetadataAddress&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;useRequestHeadersForMetadataAddress&gt;
Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.  
  
## Syntax  
  
```  
  
<useRequestHeadersForMetadataAddress>  
   <defaultPorts>  
      <add scheme="http" port="integer" />  
   </defaultPorts>  
</useRequestHeadersForMetadataAddress>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<defaultPorts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>