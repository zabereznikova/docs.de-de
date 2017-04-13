---
title: "&lt;binaryMessageEncoding&gt; | Microsoft Docs"
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
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;binaryMessageEncoding&gt;
Definiert einen Binärnachrichtenencoder, der die Windows Communication Foundation \(WCF\)\-Nachrichten bei der Übertragung im Binärformat verschlüsselt.  
  
## Syntax  
  
```  
  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10” />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|maxReadPoolSize|Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen.  Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.  Der Standard ist 64.|  
|maxSessionSize|Eine positive ganze Zahl, die die Größe des Puffers in Bytes festlegt, der zum Verschlüsseln von Nachrichten verwendet wird.  Eine größerer Puffer erhöht die Codierungsgeschwindigkeit auf Kosten der Größe des Workingsets.  Der Standard ist 2048.|  
|maxWritePoolSize|Eine ganze Zahl, die definiert, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen.  Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.  Der Standard ist 16.|  
|messageVersion|Gibt die Versionen der SOAP\-Nachricht und WS\-Adressierung an, die verwendet oder erwartet werden.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Definiert die Beschränkungen der Komplexität von SOAP\-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.  Beim Decodieren wird dieser Prozess umgekehrt.  Windows Communication Foundation \(WCF\) enthält drei Typen für die Codierung von SOAP\-Nachrichten: Text, binär und Message Transmission Optimization Mechanism \(MTOM\).  
  
 Das `binaryMessageEncoding`\-Element gibt das .NET Binary\-Format für XML an und bietet Optionen zum Festlegen der Zeichencodierung und der zu verwendenden SOAP\- und WS\-Adressierungsversion.  Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation \(WCF\)\-Nachrichten bei der Übertragung im Binärformat.  Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS\-\*\-Standards basierende Interoperabilität geht aber verloren.  
  
## Beispiel  
  
```  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>   
 [Nachrichtenverschlüsselung](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)