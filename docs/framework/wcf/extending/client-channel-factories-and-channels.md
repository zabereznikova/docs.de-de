---
title: 'Client: Kanalfactorys und Kanäle'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: 25e2c034d1fefc7728667231040a97c3aeecabbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185694"
---
# <a name="client-channel-factories-and-channels"></a>Client: Kanalfactorys und Kanäle
In diesem Thema wird die Erstellung von Kanalfactorys und Kanälen erläutert.  
  
## <a name="channel-factories-and-channels"></a>Kanalfactorys und Kanäle  
 Kanalfactorys sind für das Erstellen von Kanälen zuständig. Von Kanalfactorys erstellte Kanäle werden zum Senden von Nachrichten verwendet. Diese Kanäle dienen dem Abrufen von Nachrichten von der oberen Ebene. Die Kanäle führen jede erforderliche Verarbeitung aus und senden anschließend die Nachricht an die untere Ebene. Dieser Vorgang wird in der folgenden Grafik dargestellt.  
  
 ![Clientfactorys und Clientkanäle](./media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")  
Eine Kanalfactory dient zum Erstellen von Kanälen.  
  
 Bei der Schließung von Kanalfactorys sind diese für das Schließen aller von ihnen erstellten Kanäle zuständig, die noch nicht geschlossen wurden. Das Modell wird hier asymmetrisch dargestellt, da ein Kanallistener bei seiner Schließung zwar keine neuen Kanäle mehr akzeptiert, vorhandene Kanäle jedoch geöffnet bleiben, damit von diesen weiterhin Nachrichten empfangen werden können.  
  
 WCF stellt Basisklassen-Hilfsprogramme für diesen Prozess bereit. (Ein Diagramm der in diesem Thema behandelten Kanalhilfsklassen finden Sie unter [Kanalmodellübersicht](channel-model-overview.md).)  
  
- Die <xref:System.ServiceModel.Channels.CommunicationObject> Klasse <xref:System.ServiceModel.ICommunicationObject> implementiert und erzwingt die Zustandsmaschine, die in Schritt 2 von [Developing Channels](developing-channels.md)beschrieben wird.  
  
- Die <xref:System.ServiceModel.Channels.ChannelManagerBase> Klasse <xref:System.ServiceModel.Channels.CommunicationObject> implementiert und stellt eine <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>einheitliche Basisklasse für und bereit. Die <xref:System.ServiceModel.Channels.ChannelManagerBase>-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.
  
- Die <xref:System.ServiceModel.Channels.ChannelFactoryBase> Klasse <xref:System.ServiceModel.Channels.ChannelManagerBase> implementiert <xref:System.ServiceModel.Channels.IChannelFactory> und konsolidiert `CreateChannel` die Überladungen in einer `OnCreateChannel` abstrakten Methode.
  
- Die <xref:System.ServiceModel.Channels.ChannelListenerBase> Klasse <xref:System.ServiceModel.Channels.IChannelListener>implementiert . Die Klasse wird für grundlegende Zustandsverwaltung verwendet.
  
 Die folgende Diskussion basiert auf dem [Beispiel Transport: UDP.](../samples/transport-udp.md)  
  
### <a name="creating-a-channel-factory"></a>Erstellen einer Kanalfactory  
 Die `UdpChannelFactory` wird von <xref:System.ServiceModel.Channels.ChannelFactoryBase> abgeleitet. Das Beispiel überschreibt <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A>, um Zugriff auf die Nachrichtenversion des Nachrichtenencoders zu gewähren. Das Beispiel überschreibt auch <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, um beim Übergang des Zustandsautomaten die Instanz von <xref:System.ServiceModel.Channels.BufferManager> zu beenden.  
  
#### <a name="the-udp-output-channel"></a>Der UDP-Ausgabekanal  
 Der `UdpOutputChannel` implementiert <xref:System.ServiceModel.Channels.IOutputChannel>. Der Konstruktor überprüft die Argumente und erstellt ein Ziel-<xref:System.Net.EndPoint>-Objekt, das auf der übergebenen <xref:System.ServiceModel.EndpointAddress> basiert.  
  
 Durch die Überschreibung von <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> wird ein Socket erstellt, der zum Senden von Nachrichten an diesen <xref:System.Net.EndPoint> verwendet wird.  
  
 ```csharp
this.socket = new Socket(  
this.remoteEndPoint.AddressFamily,
   SocketType.Dgram,
   ProtocolType.Udp
);  
```  

 Der Kanal kann ordnungsgemäß oder nicht ordnungsgemäß geschlossen werden. Bei ordnungsgemäßer Schließung wird der Socket geschlossen, und die `OnClose`-Methode der Basisklasse wird aufgerufen. Wenn dadurch eine Ausnahme ausgelöst wird, ruft die Infrastruktur `Abort` auf, um sicherzustellen, dass der Kanal bereinigt wird.  
  
```csharp  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 Implementieren `Send()` `BeginSend()` / `EndSend()`und . Dieser Vorgang ist in zwei Hauptabschnitte unterteilt. Serialisieren Sie zuerst die Nachricht in ein Bytearray:  
  
```csharp  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 Senden Sie anschließend die resultierenden Daten:  
  
```csharp  
this.socket.SendTo(  
  messageBuffer.Array,
  messageBuffer.Offset,
  messageBuffer.Count,
  SocketFlags.None,
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Entwickeln von Kanälen](developing-channels.md)
