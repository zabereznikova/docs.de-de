---
title: Dienst-Kanalebenenprogrammierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
ms.openlocfilehash: db50d385bd396ba4de74e08fc1c6d93a67f320b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290217"
---
# <a name="service-channel-level-programming"></a>Dienst-Kanalebenenprogrammierung

In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Dienst Anwendung schreiben, ohne das <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> und das zugehörige-Objektmodell zu verwenden.  
  
## <a name="receiving-messages"></a>Empfangen von Nachrichten  

 Um bereit zu sein, Meldungen zu empfangen und zu verarbeiten, sind die folgenden Schritte erforderlich:  
  
1. Erstellen Sie eine Bindung.  
  
2. Erstellen Sie einen Kanallistener.  
  
3. Öffnen Sie den Kanallistener.  
  
4. Lesen Sie die Anforderung, und senden Sie eine Antwort.  
  
5. Schließen Sie alle Kanalobjekte.  
  
#### <a name="creating-a-binding"></a>Erstellen einer Bindung  

 Der erste Schritt beim Lauschen und Empfangen von Meldungen ist das Erstellen einer Bindung. WCF ist mit mehreren integrierten oder vom System bereitgestellten Bindungen ausgeliefert, die direkt verwendet werden können, indem eines von Ihnen instanziiert wird. Außerdem können Sie eigene benutzderdefinierte Bindungen durch Instanziieren einer CustomBinding-Klasse erstellen. Diese Aufgabe übernimmt beispielsweise der Code im Programmbeispiel 1.  
  
 Das Codebeispiel unten erstellt eine Instanz von <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> und fügt ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> zur Elementesammlung hinzu, die einer Sammlung von Bindungselementen entspricht, die zum Erstellen des Kanalstapels verwendet werden. Da die Elementesammlung in diesem Beispiel nur das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> aufweist, hat der resultierende Kanalstapel nur einen HTTP-Transportkanal.  
  
#### <a name="building-a-channellistener"></a>Erstellen eines Kanallisteners.  

 Nach dem Erstellen einer Bindung wird <xref:System.ServiceModel.Channels.Binding.BuildChannelListener%2A?displayProperty=nameWithType> aufgerufen, um den Kanallistener zu erstellen, wobei der Typparameter der zu erstellenden Kanalform entspricht. In diesem Beispiel wird <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> verwendet, da eingehende Meldungen in einem Anforderungs-/Antwort-Meldungsaustauschmuster abgehört werden sollen.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel> wird zum Empfangen von Anforderungsmeldungen und Senden von Antwortnachrichten verwendet. Durch das Aufrufen von <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=nameWithType> wird ein <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType> zurückgegeben, der zum Empfang der Anforderungsmeldung und zum Senden einer Antwortmeldung verwendet werden kann.  
  
 Beim Erstellen des Listeners wird die Netzwerkadresse übergeben, die dieser abhört, in diesem Fall `http://localhost:8080/channelapp`. Allgemein unterstützt jeder Transportkanal mindestens ein Adressenschema. So unterstützt beispielsweise der HTTP-Transport HTTP- und HTTPS-Schemas.  
  
 Außerdem wird beim Erstellen des Listeners eine leere <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=nameWithType> übergeben. Ein Bindungsparameter ist ein Mechanismus, um Parameter zu übergeben, die steuern, wie der Listener erstellt werden soll. In diesem Beispiel werden keine solchen Parameter verwendet, daher wird eine leere Auflistung übergeben.  
  
#### <a name="listening-for-incoming-messages"></a>Abhören von eingehenden Nachrichten  

 Dann wird <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> auf dem Listener aufgerufen und damit begonnen, Kanäle zu akzeptieren. Das Verhalten von <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType> hängt davon ab, ob der Transport verbindungsorientiert oder verbindungslos ist. Bei einem verbindungsorientierten Transport blockiert <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A>, bis eine neue Verbindungsanforderung eingeht. Dann wird ein neuer Kanal zurückgegeben, der diese neue Verbindung darstellt. Bei einem verbindungslosen Transport, wie z. B. HTTP, gibt <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> unverzüglich den einzigen Kanal zurück, den der Transportlistener erstellt.  
  
 In diesem Beispiel gibt der Listener einen Kanal zurück, der <xref:System.ServiceModel.Channels.IReplyChannel> implementiert. Um Meldungen auf diesem Kanal zu empfangen, wird zuerst <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> aufgerufen, um ihn in einen kommunikationsbereiten Status zu versetzen. Dann wird <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> aufgerufen, der blockiert, bis eine Nachricht eingeht.  
  
#### <a name="reading-the-request-and-sending-a-reply"></a>Lesen der Anforderung und Senden einer Antwort  

 Wenn <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> einen <xref:System.ServiceModel.Channels.RequestContext> zurückgibt, geht die empfangene Meldung mithilfe der <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A>-Eigenschaft ein. Die Aktion und der Textinhalt der Meldung (es wird angenommen, dass es sich um eine Zeichenfolge handelt) wird geschrieben.  
  
 Zum Senden einer Antwort wird eine neue Antwortmeldung erstellt, in diesem Fall durch Zurücksenden der Zeichenfolgendaten, die in der Anforderung eingegangen sind. Dann wird <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> aufgerufen, um die Antwortmeldung zu senden.  
  
#### <a name="closing-objects"></a>Schließen von Objekten  

 Um Ressourcenverluste zu vermeiden, sollten Sie in Kommunikationsvorgängen verwendete Objekte schließen, wenn sie nicht mehr benötigt werden. In diesem Beispiel werden die Anforderungsmeldung, der Anforderungskontext, der Kanal und der Listener geschlossen.  
  
 Im folgenden Codebeispiel wird ein grundlegender Dienst, in dem ein Kanallistener nur eine Nachricht empfängt, veranschaulicht. Ein wirklicher Dienst akzeptiert Kanäle und empfängt Meldungen, bis der Dienst beendet wird.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]
