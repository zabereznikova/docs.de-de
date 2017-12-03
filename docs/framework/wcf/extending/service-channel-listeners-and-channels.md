---
title: "Dienst: Kanallistener und Kanäle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e614abd2f9fb84f6012a3b00d90c16015287e18
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="service-channel-listeners-and-channels"></a>Dienst: Kanallistener und Kanäle
Es gibt drei Kategorien von Kanalobjekten: Kanäle, Kanallistener und Kanalfactorys. Kanäle sind die Schnittstelle zwischen der Anwendung und dem Kanalstapel. Kanallistener sind für die Erstellung von Kanälen auf der Empfänger- (oder Abhör-)Seite zuständig, normalerweise als Reaktion auf eine neue eingehende Nachricht oder Verbindung. Kanalfactorys sind dafür zuständig, Kanäle auf der Senderseite zu erstellen, um eine Kommunikation mit einem Endpunkt zu initiieren.  
  
## <a name="channel-listeners-and-channels"></a>Kanallistener und Kanäle  
 Kanallistener sind für die Erstellung von Kanälen und den Empfang von Nachrichten von der unteren Ebene oder vom Netzwerk zuständig. Empfangene Nachrichten werden der oberen Ebene mithilfe eines Kanals, der durch den Kanallistener erstellt wird, zugestellt.  
  
 Im folgenden Diagramm wird der Prozess des Empfangs von Nachrichten und ihrer Übermittlung an die obere Ebene veranschaulicht.  
  
 ![Kanallistener und Kanäle](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")  
Ein Kanallistener, der Nachrichten empfängt und sie der oberen Ebene über Kanäle zustellt.  
  
 Der Prozess kann in jedem Kanal als Warteschlange konzipiert werden, obwohl die Implementierung möglicherweise keine Warteschlange verwendet. Der Kanallistener ist dafür zuständig, Nachrichten von der unteren Ebene oder vom Netzwerk zu empfangen und sie in die Warteschlange zu stellen. Der Kanal ist für das Abrufen von Nachrichten aus der Warteschlange und ihre Übergabe an die obere Ebene zuständig, wenn diese Ebene eine Nachricht anfordert, z. B. durch Aufrufen von `Receive` im Kanal.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt Basisklassenhilfen für diesen Prozess bereit. (Ein Diagramm der Kanal Hilfsklassen, die in diesem Thema erläutert, finden Sie unter [Übersicht über das Kanalmodell](../../../../docs/framework/wcf/extending/channel-model-overview.md).)  
  
-   Die <xref:System.ServiceModel.Channels.CommunicationObject> -Klasse implementiert <xref:System.ServiceModel.ICommunicationObject> und erzwingt die in Schritt 2 beschriebenen Zustandsautomaten [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   Die <xref:System.ServiceModel.Channels.ChannelManagerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.CommunicationObject> und bietet eine einheitliche Basisklasse für <xref:System.ServiceModel.Channels.ChannelFactoryBase> und <xref:System.ServiceModel.Channels.ChannelListenerBase>. Die <xref:System.ServiceModel.Channels.ChannelManagerBase>-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.  
  
-   Die "<xref:System.ServiceModel.Channels.ChannelFactoryBase> -Klasse implementiert <xref:System.ServiceModel.Channels.ChannelManagerBase> und <xref:System.ServiceModel.Channels.IChannelFactory> konsolidiert die `CreateChannel` Überladungen in einem `OnCreateChannel` abstrakte Methode.  
  
-   Die <xref:System.ServiceModel.Channels.ChannelListenerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.IChannelListener>. Die Klasse wird für grundlegende Zustandsverwaltung verwendet.  
  
 Die folgende Diskussion basiert auf der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.  
  
## <a name="creating-a-channel-listener"></a>Erstellen eines Kanallisteners  
 Die "ableitet, UdpChannelListener, die das Beispiel implementiert die <xref:System.ServiceModel.Channels.ChannelListenerBase> Klasse. Er verwendet einen einzelnen UDP-Socket, um Datagramme zu empfangen. Die `OnOpen`-Methode empfängt Daten mit dem UDP-Socket in einer asynchronen Schleife. Die Daten werden dann mit dem Nachrichtencodierungssystem in Nachrichten konvertiert:  
  
```  
message = UdpConstants.MessageEncoder.ReadMessage(  
  new ArraySegment<byte>(buffer, 0, count),   
  bufferManager  
);  
```  
  
 Da derselbe Datagrammkanal Nachrichten darstellt, die aus einer Reihe von Quellen eintreffen, ist der `UdpChannelListener` ein Singletonlistener. Ist auf den meisten ein aktives <xref:System.ServiceModel.Channels.IChannel>'' diesem Listener zu einem Zeitpunkt zugeordnet. In diesem Beispiel wird nur dann ein weiterer generiert, wenn ein Kanal, der mit der <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>-Methode zurückgegeben wird, anschließend freigegeben wird. Wenn eine Nachricht empfangen wird, wird sie in diesem Singletonkanal in die Warteschlange eingereiht.  
  
### <a name="udpinputchannel"></a>UdpInputChannel  
 Die `UdpInputChannel` -Klasse implementiert <xref:System.ServiceModel.Channels.IInputChannel>. Sie besteht aus einer Warteschlange mit eingehenden Nachrichten, die vom `UdpChannelListener`-Socket gefüllt wird. Diese Nachrichten werden mit der <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>-Methode aus der Warteschlange entfernt.
