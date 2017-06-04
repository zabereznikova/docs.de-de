---
title: "&lt;webMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;webMessageEncoding&gt;
Aktiviert Klartext\-XML, JavaScript Object Notation \(JSON\)\-Nachrichtencodierungen und unformatierten binären Inhalt, die bei der Verwendung in einer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Bindung gelesen und geschrieben werden sollen.  
  
## Syntax  
  
```  
  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding=”UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`maxReadPoolSize`|Die Anzahl von Nachrichten, die gleichzeitig gelesen werden können, ohne neue Reader zuzuordnen.  Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.  Der Standard ist 64 Reader für jeden der inneren Encoder \(Text, JSON und "unformatiert"\).<br /><br /> Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg eingehender Nachrichten vorbereitet, da er Reader aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Reader erstellt werden.|  
|`maxWritePoolSize`|Die maximale Anzahl von Nachrichten, die gleichzeitig gesendet werden können, ohne neue Writer zuzuordnen.  Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets.  Der Standard ist 16 Writer für jeden der inneren Encoder \(Text, JSON und "unformatiert"\).<br /><br /> Durch das Erhöhen dieser Zahl wird der Speicherverbrauch gesteigert, jedoch wird der Encoder auf einen plötzlichen Anstieg ausgehender Nachrichten vorbereitet, da er Writer aus dem Pool verwenden kann, die bereits erstellt wurden, sodass keine neuen Writer erstellt werden.|  
|`writeEncoding`|Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.  Gültige Werte sind:<br /><br /> -   UnicodeFffeTextEncoding: Unicode Big Endian\-Codierung.<br />-   Utf16TextEncoding: Unicode\-Codierung.<br />-   Utf8TextEncoding: 8\-Bit\-Codierung.<br /><br /> Der Standardwert ist Utf8TextEncoding.  Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Definiert die Beschränkungen der Komplexität von SOAP\-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Beim Codieren wird eine Nachricht in eine Bytefolge transformiert.  Beim Decodieren wird dieser Prozess umgekehrt.  Diese Vorgänge erfordern die Angabe einer Zeichencodierung.  
  
 Dazu delegiert das `webMessageEncoding`\-Element Vorgänge an eine Reihe innerer Encoder, um die Klartext\-XML und JSON\-Codierungen sowie die unformatierten binären Daten zu verarbeiten.  Diese Delegierung wird von einem zusammengesetzten Nachrichtenencoder durchgeführt.  
  
 Dieses Bindungselement und die zusammengesetzten Encoder werden zur Steuerung der Codierung in Szenarien eingesetzt, in denen keine SOAP\-Nachrichten vom `webHttpBinding`\-Element verwendet werden.  Zu den Szenarien gehören u.&\#160;a. "Plain Old XML" \(POX\), Representational State Transfer \(REST\), Really Simple Syndication \(RSS\) And Atom Syndication sowie Asynchronous JavaScript And XML \(AJAX\).  Der zusammengesetzte Nachrichtenencoder unterstützt SOAP oder WS\-Addressing nicht.  
  
 Das Bindungselement kann mit dem `writeEncoding`\-Attribut mit einer Schreibzeichencodierung konfiguriert werden.  Der bereitgestellte <xref:System.Text.Encoding>\-Wert gibt das Verhalten beim Schreiben für die JSON\- und Text\-XML\-Fälle an.  Beim Lesen wird jede gültige Nachrichtencodierung und Textcodierung interpretiert.  
  
 `maxReadPoolSize` und `maxWritePoolSize` können auch zum Festlegen der maximalen Anzahl an jeweils zuzuweisenden Readern und Writern verwendet werden.  Standardmäßig werden 64 Reader und 16 Writer zugeordnet.  
  
 Standardkomplexitätseinschränkungen werden darüber hinaus mit dem [\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)\-Element festgelegt, um vor einer Klasse von DOS\-Angriffen \(Denial Of Service\) zu schützen, die versuchen, die Nachrichtenkomplexität zum Binden von Endpunkt\-Verarbeitungsressourcen zu verwenden.  
  
## Beispiel  
  
```  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding=”utf-8”   
/>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>   
 [Nachrichtenverschlüsselung](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)