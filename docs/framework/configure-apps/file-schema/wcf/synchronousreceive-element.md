---
title: "&lt;synchronousReceive&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;synchronousReceive&gt;-Element
Dieses Konfigurationselement wird zum Angeben des Laufzeitverhaltens für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung verwendet.  Es enthält keine Attribute oder untergeordnete Elemente.  
  
## Syntax  
  
```  
  
<synchronousReceive />  
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
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## Hinweise  
 Hiermit weisen Sie den Kanallistener an, anstatt der Standardeinstellung \(asynchroner Empfang\) einen synchronen Empfang zu verwenden.  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] gibt einen neuen Thread zur Weiterleitung für jeden akzeptierten Kanal aus.  Bei einer großen Anzahl von Kanälen besteht die Gefahr, dass nicht genügend Threads verfügbar sind.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>   
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>