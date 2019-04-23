---
title: Nachrichtenverschlüsselung
ms.date: 03/30/2017
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
ms.openlocfilehash: 7fb0d4a994eaf1497841691eb76261329a48599d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168752"
---
# <a name="message-encoding"></a>Nachrichtenverschlüsselung
Beim Kodieren werden Unicode-Zeichen in eine Bytefolge transformiert. Beim Decodieren wird dieser Prozess umgekehrt. Windows Communication Foundation (WCF) enthält drei Typen für die Codierung von SOAP-Nachrichten: Text, Binär und Message Transmission Optimization Mechanism (MTOM).  
  
 Der `binaryMessageEncoding`-Konfigurationsabschnitt gibt die Zeichenkodierung und die für binäre XML-Nachrichten verwendete Nachrichtenversionierung an. Der Binärnachrichtenencoder verschlüsselt die Windows Communication Foundation (WCF)-Nachrichten bei der Übertragung im Binärformat. Diese Verschlüsselung resultiert zwar in einer schnellen Nachrichtenübertragung, die auf den WS-*-Standards basierende Interoperabilität geht aber verloren.  
  
 Der `mtomMessageEncoding`-Konfigurationsabschnitt gibt die Zeichenkodierung und die für eine Nachricht mit der MTOM-Verschlüsselung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversionierung an. MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in Windows Communication Foundation (WCF)-Nachrichten. Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu erreichen. Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung.  
  
 Der `textMessageEncoding`-Konfigurationsabschnitt gibt einen Textencoder an, der bei der Übertragung textbasierte Nachrichten erstellt. Von diesem Encoder erzeugte Nachrichten sind für die WS-*-basierte Interoperabilität geeignet. Der Webdienst oder Webdienstclient kann im Allgemeinen Text-XML verstehen. Das Übertragen großer Binärdatenblöcke als Text ist allerdings die am wenigsten effiziente Methode zum Verschlüsseln von XML-Nachrichten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Auswählen eines Nachrichtenencoders](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
