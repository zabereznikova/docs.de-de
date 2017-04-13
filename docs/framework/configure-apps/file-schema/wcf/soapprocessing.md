---
title: "&lt;soapProcessing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;soapProcessing&gt;
Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.  
  
## Syntax  
  
```  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Element|Beschreibung|  
|-------------|------------------|  
|processMessages|Ein boolescher Wert, der angibt, ob Nachrichten zwischen SOAP\-Nachrichtenversionen gemarshallt werden sollen.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## Hinweise  
 SOAP\-Verarbeitung ist der Prozess, bei dem Nachrichten zwischen Nachrichtenversionen konvertiert werden.  
  
 Der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Routingdienst kann Nachrichten von einem Protokoll in ein anderes konvertieren.  Wenn die Versionen eingehender und ausgehender Nachrichten unterschiedlich sind, wird eine neue Nachricht mit der richtigen Version erstellt.  Nachrichten werden von einer <xref:System.ServiceModel.Channel.MessageVersion> in eine andere geändert, indem eine neue [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht erstellt wird, die den Textteil und relevante Header der eingehenden [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Nachricht enthält.  Header, die adressierungsspezifisch sind oder auf Routerebene verstanden werden, werden während der Erstellung der neuen WCF\-Nachricht nicht verwendet, da diese Header entweder eine andere Version haben \(im Fall von Adressierungsheadern\) oder als Teil der Kommunikation zwischen dem Client und dem Router verarbeitet wurden.  
  
 Ob ein Header in der ausgehenden Nachricht eingefügt wird, wird dadurch bestimmt, ob er als verstanden markiert wurde, als er die eingehende Channelebene durchlief.  Nicht akzeptierte Header \(z. B. benutzerdefinierte Header\) werden nicht entfernt und durchlaufen den Routingdienst, indem sie in die ausgehende Nachricht kopiert werden.  Der Nachrichtentext wird in die ausgehende Nachricht kopiert.  Die Nachricht wird dann über den Kanal für ausgehende Nachrichten gesendet. Zu diesem Zeitpunkt werden alle relevanten Header und anderen für das Kommunikationsprotokoll\/den Transport relevanten Umschlagdaten erstellt und hinzugefügt.  
  
 Diese Verarbeitungsschritte erfolgen, wenn das SOAP\-Verarbeitungsverhalten angegeben ist.  Dieses [\<soapProcessingExtension\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)\-Verhalten ist ein Endpunktverhalten, das auf alle \(ausgehenden\) Clientendpunkte angewendet wird, wenn der Routingdienst startet.  Durch das [\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)\-Verhalten wird standardmäßig ein neues [\<soapProcessingExtension\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)\-Verhalten erstellt und angefügt, wobei `processMessages` für jeden Clientendpunkt auf `true` festgelegt ist.  Wenn Sie über ein Protokoll verfügen, das vom Routingdienst nicht interpretiert werden kann, oder das Standardverarbeitungsverhalten überschreiben möchten, können Sie die SOAP\-Verarbeitung entweder für den gesamten Routingdienst oder für bestimmte Endpunkte deaktivieren. Um die SOAP\-Verarbeitung für den gesamten Routingdienst auf allen Endpunkten zu deaktivieren, legen Sie das `soapProcessing`\-Attribut des [\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)\-Verhaltens auf `false` fest.  Um die SOAP\-Verarbeitung für einen bestimmten Endpunkt zu deaktivieren, verwenden Sie dieses Verhalten und legen dessen `processMessages`\-Attribut auf `false` fest. Fügen Sie das Verhalten dann an den Endpunkt an, für den der Standardverarbeitungscode nicht ausgeführt werden soll. Wenn der Routingdienst durch das [\<Routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)\-Verhalten eingerichtet wird, wird das Endpunktverhalten nicht erneut angewendet, da bereits eines vorhanden ist.  
  
## Siehe auch  
 <xref:System.ServiceModel.Routing.Configuration.> SoapProcessingExtensionElement?qualifyHint=False&autoUpgrade=True   
 <xref:System.ServiceModel.Routing.SoapProcessingBehavior>