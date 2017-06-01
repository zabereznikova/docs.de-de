---
title: "&lt;enableWebScript&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;enableWebScript&gt;
Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX\-Webseiten genutzt werden kann.  
  
## Syntax  
  
```  
  
<enableWebScript />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt den Satz an Endpunktverhalten an.|  
  
## Hinweise  
 Dieses Verhalten sollte nur in Verbindung mit entweder der [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)\-Standardbindung oder dem [\<webMessageEncoding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)\-Bindungselement verwendet werden.  Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>   
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>   
 [AJAX\-Integration und JSON\-Unterstützung](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)