---
title: "Dienst-Kanalebenenprogrammierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Dienst-Kanalebenenprogrammierung
In diesem Thema wird das Schreiben einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Dienstanwendung ohne Verwenden des <xref:System.ServiceModel.ServiceHost?displayProperty=fullName> und der zugehörigen Objektmodelle beschrieben.  
  
## Empfangen von Meldungen  
 Um bereit zu sein, Meldungen zu empfangen und zu verarbeiten, sind die folgenden Schritte erforderlich:  
  
1.  Erstellen Sie eine Bindung.  
  
2.  Erstellen Sie einen Kanallistener.  
  
3.  Öffnen Sie den Kanallistener.  
  
4.  Lesen Sie die Anforderung, und senden Sie eine Antwort.  
  
5.  Schließen Sie alle Kanalobjekte.  
  
#### Erstellen einer Bindung  
 Der erste Schritt beim Lauschen und Empfangen von Meldungen ist das Erstellen einer Bindung.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird mit verschiedenen integrierten und vom System bereitgestellten Bindungen ausgeliefert, die direkt durch Instanziierung verwendet werden können.Außerdem können Sie eigene benutzderdefinierte Bindungen durch Instanziieren einer CustomBinding\-Klasse erstellen. Diese Aufgabe übernimmt beispielsweise der Code im Programmbeispiel 1.  
  
 Das Codebeispiel unten erstellt eine Instanz von <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> und fügt ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> zur Elementesammlung hinzu, die einer Sammlung von Bindungselementen entspricht, die zum Erstellen des Kanalstapels verwendet werden.Da die Elementesammlung in diesem Beispiel nur das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> aufweist, hat der resultierende Kanalstapel nur einen HTTP\-Transportkanal.  
  
#### Erstellen eines Kanallisteners.  
 Nach dem Erstellen einer Bindung wird <xref:System.ServiceModel.Channels.Binding.BuildChannelListener%601%2A?displayProperty=fullName> aufgerufen, um den Kanallistener zu erstellen, wobei der Typparameter der zu erstellenden Kanalform entspricht.In diesem Beispiel wird <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=fullName> verwendet, da eingehende Meldungen in einem Anforderungs\-\/Antwort\-Meldungsaustauschmuster abgehört werden sollen.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel> wird zum Empfangen von Anforderungsmeldungen und Senden von Antwortnachrichten verwendet.Durch das Aufrufen von <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=fullName> wird ein <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName> zurückgegeben, der zum Empfang der Anforderungsmeldung und zum Senden einer Antwortmeldung verwendet werden kann.  
  
 Beim Erstellen des Listeners wird die Netzwerkadresse übergeben, die dieser abhört, in diesem Fall `http://localhost:8080/channelapp`.Allgemein unterstützt jeder Transportkanal mindestens ein Adressenschema. So unterstützt beispielsweise der HTTP\-Transport HTTP\- und HTTPS\-Schemas.  
  
 Außerdem wird beim Erstellen des Listeners eine leere <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=fullName> übergeben.Ein Bindungsparameter ist ein Mechanismus, um Parameter zu übergeben, die steuern, wie der Listener erstellt werden soll.In diesem Beispiel werden keine solchen Parameter verwendet, daher wird eine leere Auflistung übergeben.  
  
#### Abhören von eingehenden Nachrichten  
 Dann wird <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> auf dem Listener aufgerufen und damit begonnen, Kanäle zu akzeptieren.Das Verhalten von <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=fullName> hängt davon ab, ob der Transport verbindungsorientiert oder verbindungslos ist.Bei einem verbindungsorientierten Transport blockiert <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A>, bis eine neue Verbindungsanforderung eingeht. Dann wird ein neuer Kanal zurückgegeben, der diese neue Verbindung darstellt.Bei einem verbindungslosen Transport, wie z. B. HTTP, gibt <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> unverzüglich den einzigen Kanal zurück, den der Transportlistener erstellt.  
  
 In diesem Beispiel gibt der Listener einen Kanal zurück, der <xref:System.ServiceModel.Channels.IReplyChannel> implementiert.Um Meldungen auf diesem Kanal zu empfangen, wird zuerst <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> aufgerufen, um ihn in einen kommunikationsbereiten Status zu versetzen.Dann wird <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> aufgerufen, der blockiert, bis eine Nachricht eingeht.  
  
#### Lesen der Anforderung und Senden einer Antwort  
 Wenn <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> einen <xref:System.ServiceModel.Channels.RequestContext> zurückgibt, geht die empfangene Meldung mithilfe der <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A>\-Eigenschaft ein.Die Aktion und der Textinhalt der Meldung \(es wird angenommen, dass es sich um eine Zeichenfolge handelt\) wird geschrieben.  
  
 Zum Senden einer Antwort wird eine neue Antwortmeldung erstellt, in diesem Fall durch Zurücksenden der Zeichenfolgendaten, die in der Anforderung eingegangen sind.Dann wird <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> aufgerufen, um die Antwortmeldung zu senden.  
  
#### Schließen von Objekten  
 Um Ressourcenverluste zu vermeiden, sollten Sie in Kommunikationsvorgängen verwendete Objekte schließen, wenn sie nicht mehr benötigt werden.In diesem Beispiel werden die Anforderungsmeldung, der Anforderungskontext, der Kanal und der Listener geschlossen.  
  
 Im folgenden Codebeispiel wird ein grundlegender Dienst, in dem ein Kanallistener nur eine Nachricht empfängt, veranschaulicht.Ein wirklicher Dienst akzeptiert Kanäle und empfängt Meldungen, bis der Dienst beendet wird.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]