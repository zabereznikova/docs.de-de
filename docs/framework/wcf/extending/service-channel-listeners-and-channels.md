---
title: 'Dienst: Kanallistener und Kanäle'
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 0a740f5dcf682c3c140adb9c4c7c9678c4eae132
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797182"
---
# <a name="service-channel-listeners-and-channels"></a>Dienst: Kanallistener und Kanäle

Es gibt drei Kategorien von Kanal Objekten: Kanäle, Kanallistener und Kanalfactorys. Kanäle sind die Schnittstelle zwischen der Anwendung und dem Kanalstapel. Kanallistener sind für die Erstellung von Kanälen auf der Empfänger- (oder Abhör-)Seite zuständig, normalerweise als Reaktion auf eine neue eingehende Nachricht oder Verbindung. Kanalfactorys sind dafür zuständig, Kanäle auf der Senderseite zu erstellen, um eine Kommunikation mit einem Endpunkt zu initiieren.

## <a name="channel-listeners-and-channels"></a>Kanallistener und Kanäle

Kanallistener sind für die Erstellung von Kanälen und den Empfang von Nachrichten von der unteren Ebene oder vom Netzwerk zuständig. Empfangene Nachrichten werden der oberen Ebene mithilfe eines Kanals, der durch den Kanallistener erstellt wird, zugestellt.

Im folgenden Diagramm wird der Prozess des Empfangs von Nachrichten und ihrer Übermittlung an die obere Ebene veranschaulicht.

![Kanallistener und Kanäle](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")

Ein Kanallistener, der Nachrichten empfängt und sie der oberen Ebene über Kanäle zustellt.

Der Prozess kann in jedem Kanal als Warteschlange konzipiert werden, obwohl die Implementierung möglicherweise keine Warteschlange verwendet. Der Kanallistener ist dafür zuständig, Nachrichten von der unteren Ebene oder vom Netzwerk zu empfangen und sie in die Warteschlange zu stellen. Der Kanal ist für das Abrufen von Nachrichten aus der Warteschlange und ihre Übergabe an die obere Ebene zuständig, wenn diese Ebene eine Nachricht anfordert, z. B. durch Aufrufen von `Receive` im Kanal.

WCF stellt Basisklassen Hilfen für diesen Prozess bereit. (Ein Diagramm der in diesem Artikel beschriebenen channelhilfsobjekte finden Sie unter [Übersicht über das Kanal Modell](channel-model-overview.md).)

- Die <xref:System.ServiceModel.Channels.CommunicationObject> -Klasse <xref:System.ServiceModel.ICommunicationObject> implementiert und erzwingt den Zustands Automat, der in Schritt 2 der [Entwicklung von Kanälen](developing-channels.md)beschrieben wird.

- Die <xref:System.ServiceModel.Channels.ChannelManagerBase> -Klasse <xref:System.ServiceModel.Channels.CommunicationObject> implementiert und stellt eine einheitliche Basisklasse <xref:System.ServiceModel.Channels.ChannelFactoryBase> für <xref:System.ServiceModel.Channels.ChannelListenerBase>und bereit. Die <xref:System.ServiceModel.Channels.ChannelManagerBase>-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.

- Die <xref:System.ServiceModel.Channels.ChannelFactoryBase> -Klasse <xref:System.ServiceModel.Channels.ChannelManagerBase> implementiert <xref:System.ServiceModel.Channels.IChannelFactory> und und konsolidiert die `CreateChannel` -über Ladungen in `OnCreateChannel` einer abstrakten Methode.

- Die <xref:System.ServiceModel.Channels.ChannelListenerBase> -Klasse <xref:System.ServiceModel.Channels.IChannelListener>implementiert. Die Klasse wird für grundlegende Zustandsverwaltung verwendet.

Die folgende Erörterung basiert auf dem [-Transport: UDP](../samples/transport-udp.md) -Beispiel.

## <a name="creating-a-channel-listener"></a>Erstellen eines Kanallistener

Der `UdpChannelListener` , den das Beispiel implementiert, wird <xref:System.ServiceModel.Channels.ChannelListenerBase> von der-Klasse abgeleitet. Er verwendet einen einzelnen UDP-Socket, um Datagramme zu empfangen. Die `OnOpen`-Methode empfängt Daten mit dem UDP-Socket in einer asynchronen Schleife. Die Daten werden dann mit dem Nachrichtencodierungssystem in Nachrichten konvertiert:

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

Da derselbe Datagrammkanal Nachrichten darstellt, die aus einer Reihe von Quellen eintreffen, ist der `UdpChannelListener` ein Singletonlistener. Es ist höchstens eine aktive <xref:System.ServiceModel.Channels.IChannel> diesem Listener gleichzeitig zugeordnet. In diesem Beispiel wird nur dann ein weiterer generiert, wenn ein Kanal, der mit der <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>-Methode zurückgegeben wird, anschließend freigegeben wird. Wenn eine Nachricht empfangen wird, wird Sie in die Warteschlange dieses Singleton Kanals eingereiht.

### <a name="udpinputchannel"></a>UdpInputChannel

Die `UdpInputChannel` -Klasse <xref:System.ServiceModel.Channels.IInputChannel>implementiert. Sie besteht aus einer Warteschlange mit eingehenden Nachrichten, die vom `UdpChannelListener`-Socket gefüllt wird. Diese Nachrichten werden mit der <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>-Methode aus der Warteschlange entfernt.
