---
title: Codieren von binären Objekten mit dem ByteStream-Encoder
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: 09a919e11971f81bc76dca0e45a7eb0e70ef749e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626930"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Codieren von binären Objekten mit dem ByteStream-Encoder
Senden und Empfangen von unformatierten Binärdaten mit Windows Communication Foundation (WCF) erfolgt über <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.  
  
## <a name="byte-stream-message-encoder-architecture"></a>Bytestream-Nachrichtenencoder-Architektur  
 Der binäre Nachrichtenencoder, die von WCF verwendet hat keine Möglichkeit zur Verarbeitung, überprüfen oder Identifizieren der zugrunde liegenden binäre Daten in der Nachricht. Das Datenpaket wird in XML codiert, gesendet, empfangen und decodiert. Der Encoder verarbeitet die Daten, nachdem diese an den Transport übergeben wurden und bevor die Nachricht an die Nachrichtenwarteschlange gesendet wird. Der Funktion nach schließt der binäre Encoder die Nachrichtendaten zum Senden in `<binary>`-Elemente ein und entfernt die Elemente, nachdem die Nachricht empfangen wurde.  
  
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
  
- Übertragen eines JPEG-Bilds zwischen Computern, die mithilfe von WCF. In diesem Szenario wird das Bild über den Transport von einer externen Quelle empfangen. Bei den gesendeten Daten handelt es sich um die unformatierten Bytes, aus denen das Bild besteht. Ein Dienst empfängt die Binärdaten und zeigt das Bild an.  
  
- Lesen von Informationen aus einer Meldungswarteschlange und Verarbeiten der Informationen. Die Meldung wird von einem Meldungswarteschlangen-Manager gelesen und zur Verarbeitung an den Meldungswarteschlangenkanal übergeben. Der meldungswarteschlangenkanal fungiert als ein Warteschlangen-Manager in der WCF-Kanalstapel.  
  
 Wenn eine Meldung über einen Meldungswarteschlangenkanal gesendet wird, hat der Absender keine Kontrolle über die vom Warteschlangen-Manger empfangenen Bytes. Wenn im Empfängerprozess keine unformatierten Bytes gelesen werden können, wird die Meldung als falsch formatierte Meldung empfangen und nicht verarbeitet. Es wird davon ausgegangen, dass der Empfängerprozess die empfangenen Bytes in ein akzeptables Format übersetzen kann.
