---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e684c21c0b1360a9b270214ebe7b3ad00b42657f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861959"
---
# <a name="lttextmessageencodinggt"></a>&lt;textMessageEncoding&gt;
Gibt die Zeichencodierung und die für textbasierte XML-Nachrichten verwendete Nachrichtenversionierung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<textMessageEncoding>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|maxReadPoolSize|Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gelesen werden können, ohne neue Leser zuzuordnen. Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets. Der Standard ist 64.|  
|maxWritePoolSize|Eine ganze Zahl, die bestimmt, wie viele Nachrichten gleichzeitig gesendet werden können, ohne neue Schreiber zuzuordnen. Durch größere Poolgrößen wird das System toleranter gegenüber Aktivitätsspitzen auf Kosten eines umfangreicheren Workingsets. Der Standard ist 16.|  
|messageVersion|Gibt die SOAP-Version der Nachrichten an, die mithilfe der Bindung gesendet werden. Folgende Werte sind gültig:<br /><br /> -Soap11Addressing10<br />-Soap12Addressing10<br /><br /> Der Standardwert ist Soap12Addressing10. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -UnicodeFffeTextEncoding: Unicode BigEndian-Codierung<br />-Utf16TextEncoding: Unicode-Codierung<br />-Utf8TextEncoding: 8-Bit-Codierung<br /><br /> Der Standardwert ist Utf8TextEncoding. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Codieren wird eine Nachricht in eine Bytefolge transformiert. Beim Decodieren wird dieser Prozess umgekehrt. Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, binär und Message Transmission Optimization Mechanism (MTOM).  
  
 Die vom `textMessageEncoding`-Element dargestellte Textcodierung ist am besten für die Interoperabilität geeignet, jedoch der am wenigsten effektive Encoder für XML-Nachrichten.  Der Textencoder erstellt textbasierte Nachrichten. Von diesem Encoder erzeugte Nachrichten sind für die WS-*-basierte Interoperabilität geeignet. Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen. Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Meldungen.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Nachrichtencodierung](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
