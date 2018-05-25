---
title: 'Client: Kanalfactorys und Kanäle'
ms.date: 03/30/2017
ms.assetid: ef245191-fdab-4468-a0da-7c6f25d2110f
ms.openlocfilehash: a42042eaf9a8bc5461f680e3cf8dc5fcc78cebb5
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="client-channel-factories-and-channels"></a>Client: Kanalfactorys und Kanäle
In diesem Thema wird die Erstellung von Kanalfactorys und Kanälen erläutert.  
  
## <a name="channel-factories-and-channels"></a>Kanalfactorys und Kanäle  
 Kanalfactorys sind für das Erstellen von Kanälen zuständig. Von Kanalfactorys erstellte Kanäle werden zum Senden von Nachrichten verwendet. Diese Kanäle dienen dem Abrufen von Nachrichten von der oberen Ebene. Die Kanäle führen jede erforderliche Verarbeitung aus und senden anschließend die Nachricht an die untere Ebene. Dieser Vorgang wird in der folgenden Grafik dargestellt.  
  
 ![Clientfactorys und-Kanäle](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure2highlevelfactgoriesc.gif "wcfc_WCFChannelsigure2HIghLevelFactgoriesc")  
Eine Kanalfactory dient zum Erstellen von Kanälen.  
  
 Bei der Schließung von Kanalfactorys sind diese für das Schließen aller von ihnen erstellten Kanäle zuständig, die noch nicht geschlossen wurden. Das Modell wird hier asymmetrisch dargestellt, da ein Kanallistener bei seiner Schließung zwar keine neuen Kanäle mehr akzeptiert, vorhandene Kanäle jedoch geöffnet bleiben, damit von diesen weiterhin Nachrichten empfangen werden können.  
  
 WCF stellt basisklassenhilfen für diesen Prozess bereit. (Ein Diagramm der Kanal Hilfsklassen, die in diesem Thema erläutert, finden Sie unter [Übersicht über das Kanalmodell](../../../../docs/framework/wcf/extending/channel-model-overview.md).)  
  
-   Die <xref:System.ServiceModel.Channels.CommunicationObject> -Klasse implementiert <xref:System.ServiceModel.ICommunicationObject> und erzwingt die in Schritt 2 beschriebenen Zustandsautomaten [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   Die <xref:System.ServiceModel.Channels.ChannelManagerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.CommunicationObject> und bietet eine einheitliche Basisklasse für <xref:System.ServiceModel.Channels.ChannelFactoryBase?displayProperty=nameWithType> und <xref:System.ServiceModel.Channels.ChannelListenerBase?displayProperty=nameWithType>. Die <xref:System.ServiceModel.Channels.ChannelManagerBase>-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.
  
-   Die <xref:System.ServiceModel.Channels.ChannelFactoryBase> -Klasse implementiert <xref:System.ServiceModel.Channels.ChannelManagerBase> und <xref:System.ServiceModel.Channels.IChannelFactory> konsolidiert die `CreateChannel` Überladungen in einem `OnCreateChannel` abstrakte Methode.
  
-   Die <xref:System.ServiceModel.Channels.ChannelListenerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.IChannelListener>. Die Klasse wird für grundlegende Zustandsverwaltung verwendet. 
  
 Die folgende Diskussion basiert auf der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.  
  
### <a name="creating-a-channel-factory"></a>Erstellen einer Kanalfactory  
 Die `UdpChannelFactory` wird von <xref:System.ServiceModel.Channels.ChannelFactoryBase> abgeleitet. Das Beispiel überschreibt <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A>, um Zugriff auf die Nachrichtenversion des Nachrichtenencoders zu gewähren. Das Beispiel überschreibt auch <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, um beim Übergang des Zustandsautomaten die Instanz von <xref:System.ServiceModel.Channels.BufferManager> zu beenden.  
  
#### <a name="the-udp-output-channel"></a>Der UDP-Ausgabekanal  
 Der `UdpOutputChannel` implementiert <xref:System.ServiceModel.Channels.IOutputChannel>. Der Konstruktor überprüft die Argumente und erstellt ein Ziel-<xref:System.Net.EndPoint>-Objekt, das auf der übergebenen <xref:System.ServiceModel.EndpointAddress> basiert.  
  
 Durch die Überschreibung von <xref:System.ServiceModel.Channels.CommunicationObject.OnOpen%2A> wird ein Socket erstellt, der zum Senden von Nachrichten an diesen <xref:System.Net.EndPoint> verwendet wird.  
  
 `this.socket = new Socket(`  
  
 `this.remoteEndPoint.AddressFamily,`  
  
 `SocketType.Dgram,`  
  
 `ProtocolType.Udp`  
  
 `);`  
  
 Der Kanal kann ordnungsgemäß oder nicht ordnungsgemäß geschlossen werden. Bei ordnungsgemäßer Schließung wird der Socket geschlossen, und die `OnClose`-Methode der Basisklasse wird aufgerufen. Wenn dadurch eine Ausnahme ausgelöst wird, ruft die Infrastruktur `Abort` auf, um sicherzustellen, dass der Kanal bereinigt wird.  
  
```  
this.socket.Close();  
base.OnClose(timeout);  
```  
  
 Implementieren `Send()` und `BeginSend()` / `EndSend()`. Dieser Vorgang ist in zwei Hauptabschnitte unterteilt. Serialisieren Sie zuerst die Nachricht in ein Bytearray:  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 Senden Sie anschließend die resultierenden Daten:  
  
```  
this.socket.SendTo(  
  messageBuffer.Array,   
  messageBuffer.Offset,   
  messageBuffer.Count,   
  SocketFlags.None,   
  this.remoteEndPoint  
);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md)
