---
title: "&lt;webHttpEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;webHttpEndpoint&gt;
Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)\-Bindung, die das [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)\-Verhalten automatisch hinzufügt.  Verwenden Sie diesen Endpunkt, wenn Sie einen REST\-Dienst schreiben.  
  
## Syntax  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <webHttpEndpoint>   
          <standardEndpoint  
             automaticFormatSelectionEnabled="String"   
             defaultOutgoingResponseFormat=”Xml/Json”  
             helpEnabled=”Boolean”  
             webEndpointType=”String”/>        
       </webHttpEndpoint>   
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|automaticFormatSelectionEnabled|Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.<br /><br /> Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`\-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.  Wenn der `Accept`\-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`\-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.|  
|defaultOutgoingResponseFormat|Ein Attribut mit dem Standardformat für ausgehende Antworten.  Dieses Attribut ist vom Typ <xref:System.Servicemodel.Web.Webmessageformat>.|  
|helpEnabled|Ein boolescher Wert, der angibt, ob die HTTP\-Hilfeseite für den Endpunkt aktiviert ist.|  
|webEndpointType|Eine Zeichenfolge, die den Typ des Endpunkts angibt.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften \(Adresse, Bindung, Vertrag\) fest vorgegeben sind.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>   
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>