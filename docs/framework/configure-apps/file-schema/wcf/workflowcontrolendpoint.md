---
title: "&lt;workflowControlEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;workflowControlEndpoint&gt;
Dieses Konfigurationselement definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen \(create, run, suspend, terminate usw.\).  
  
## Syntax  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <workflowControlEndpoint>   
          <standardEndpoint  
                  name="String" />   
       </workflowControlEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Name|Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.  Der Name wird im `endpointConfiguration`\-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften \(Adresse, Bindung, Vertrag\) fest vorgegeben sind.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Activites.WorkflowControlEndpoint>