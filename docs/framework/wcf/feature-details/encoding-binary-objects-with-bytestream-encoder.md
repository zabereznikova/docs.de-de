---
title: Codieren von binären Objekten mit dem ByteStream-Encoder
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: cc63cb8de1e245c3b58fb69819e59cb815b777d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276736"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Codieren von binären Objekten mit dem ByteStream-Encoder

Das Senden und empfangen von unformatierten Binärdaten mit Windows Communication Foundation (WCF) wird mithilfe von konfiguriert <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> .  
  
## <a name="byte-stream-message-encoder-architecture"></a>Bytestream-Nachrichtenencoder-Architektur  

 Der von WCF verwendete binäre Nachrichten Encoder verfügt nicht über die Möglichkeit, die zugrunde liegenden Binärdaten in der Nachricht zu verarbeiten, zu validieren oder zu identifizieren. Das Datenpaket wird in XML codiert, gesendet, empfangen und decodiert. Der Encoder verarbeitet die Daten, nachdem diese an den Transport übergeben wurden und bevor die Nachricht an die Nachrichtenwarteschlange gesendet wird. Der Funktion nach schließt der binäre Encoder die Nachrichtendaten zum Senden in `<binary>`-Elemente ein und entfernt die Elemente, nachdem die Nachricht empfangen wurde.  
  
## <a name="using-the-byte-stream-message-encoder"></a>Verwenden des Bytestream-Nachrichtenencoders  

 Das folgende Beispiel zeigt einen Dienstvertrag, der den Bytestream-Nachrichtenencoder implementiert.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 Das folgende Beispiel zeigt, wie der Dienst aufgerufen wird.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 Falls Sie einen Dienst verwenden, der eine Nachrichteninfrastruktur implementiert (zum Beispiel ein Router), wird die Nachricht verarbeitet, ohne dass diese untersucht bzw. überprüft oder dass auf andere Art damit interagiert wird. Dies wird im folgenden Beispiel veranschaulicht.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>Szenarien  

 Der Bytestreamencoder ist in folgenden Szenarios nützlich.  
  
- Übertragen eines JPEG-Bilds zwischen Computern mithilfe von WCF. In diesem Szenario wird das Bild über den Transport von einer externen Quelle empfangen. Bei den gesendeten Daten handelt es sich um die unformatierten Bytes, aus denen das Bild besteht. Ein Dienst empfängt die Binärdaten und zeigt das Bild an.  
  
- Lesen von Informationen aus einer Meldungswarteschlange und Verarbeiten der Informationen. Die Meldung wird von einem Meldungswarteschlangen-Manager gelesen und zur Verarbeitung an den Meldungswarteschlangenkanal übergeben. Der Nachrichten Warteschlangen-Kanal fungiert als Warteschlangen-Manager im WCF-Kanal Stapel.  
  
 Wenn eine Meldung über einen Meldungswarteschlangenkanal gesendet wird, hat der Absender keine Kontrolle über die vom Warteschlangen-Manger empfangenen Bytes. Wenn im Empfängerprozess keine unformatierten Bytes gelesen werden können, wird die Meldung als falsch formatierte Meldung empfangen und nicht verarbeitet. Es wird davon ausgegangen, dass der Empfängerprozess die empfangenen Bytes in ein akzeptables Format übersetzen kann.
