---
title: "Nachrichtenverschl&#252;sselung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Nachrichtenverschl&#252;sselung
Beim Kodieren werden Unicode\-Zeichen in eine Bytefolge transformiert.  Beim Decodieren wird dieser Prozess umgekehrt.  Windows Communication Foundation \(WCF\) enthält drei Typen für die Codierung von SOAP\-Nachrichten: Text, binär und Message Transmission Optimization Mechanism \(MTOM\).  
  
 Der `binaryMessageEncoding`\-Konfigurationsabschnitt gibt die Zeichenkodierung und die für binäre XML\-Nachrichten verwendete Nachrichtenversionierung an.  Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation \(WCF\)\-Nachrichten bei der Übertragung im Binärformat.  Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS\-\*\-Standards basierende Interoperabilität geht aber verloren.  
  
 Der `mtomMessageEncoding`\-Konfigurationsabschnitt gibt die Zeichenkodierung und die für eine Nachricht mit der MTOM\-Verschlüsselung \(Message Transmission Optimization Mechanism\) verwendete Nachrichtenversionierung an.  MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in Windows Communication Foundation \(WCF\)\-Nachrichten.  Der MTOM\-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu erreichen.  Die MTOM\-Verschlüsselung überträgt die meisten XML\-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung.  
  
 Der `textMessageEncoding`\-Konfigurationsabschnitt gibt einen Textencoder an, der bei der Übertragung textbasierte Nachrichten erstellt.  Von diesem Encoder erzeugte Nachrichten sind für die WS\-\*\-basierte Interoperabilität geeignet.  Der Webdienst oder Webdienstclient kann im Allgemeinen Text\-XML verstehen.  Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML\-Nachrichten.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)