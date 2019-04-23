---
title: Erstellen eines BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 600bf9b394078ffc1b1bc97390bd0de406d64338
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115166"
---
# <a name="creating-a-bindingelement"></a>Erstellen eines BindingElement
Bindungen und Bindungselemente (Objekte, die erweitern <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> und <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>bzw.) der Ort, in dem das Anwendungsmodell Windows Communication Foundation (WCF) mit kanalfactorys und Kanallistenern verknüpft ist, sind. Ohne Bindungen erfordern benutzerdefinierte Kanäle Programmierung auf Kanalebene wie beschrieben in [Programmieren auf Kanalebene von Dienst](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) und [Client Kanals auf Serverebene Programmierung](../../../../docs/framework/wcf/extending/client-channel-level-programming.md). In diesem Thema wird erläutert, die Mindestanforderungen für die Aktivierung Ihres Kanals in die Entwicklung von WCF ein <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal und Verwendung von der Anwendung, wie in Schritt 4 beschrieben aktivieren [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="overview"></a>Übersicht  
 Erstellen einer <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal Entwickler ihn in eine WCF-Anwendung verwenden kann. <xref:System.ServiceModel.Channels.BindingElement> Objekte können verwendet werden, aus der <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> Klasse, um einen WCF-Anwendung mit Ihrem Kanal eine Verbindung herstellen, ohne dem genauen Informationstyp Ihres Kanals.  
  
 Nach einem <xref:System.ServiceModel.Channels.BindingElement> wurde erstellt, Sie können mehr Funktionalität, die abhängig von Ihren Anforderungen durch die verbleibenden kanalentwicklungsschritte ausführen, die in beschriebenen folgenden [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Hinzufügen eines Bindungselements  
 Um ein benutzerdefiniertes <xref:System.ServiceModel.Channels.BindingElement> zu implementieren, schreiben Sie eine Klasse, die von <xref:System.ServiceModel.Channels.BindingElement> erbt. Wenn Sie beispielsweise einen `ChunkingChannel` entwickelt haben, der große Nachrichten segmentieren und sie am anderen Ende wieder zusammensetzen kann, können Sie diesen Kanal in jeder Bindung verwenden, indem Sie ein <xref:System.ServiceModel.Channels.BindingElement> implementieren und die Bindung für die entsprechende Verwendung konfigurieren. In diesem Thema wird der `ChunkingChannel` als Beispiel zur Demonstration der Implementierungsanforderungen eines Bindungselements verwendet.  
  
 Ein `ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich. Es überschreibt die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A>-Implementierung und die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>-Implementierung und überprüft, ob der Typparameter <xref:System.ServiceModel.Channels.IDuplexSessionChannel> lautet (in unserem Beispiel ist dies die einzige Kanalform, die von `ChunkingChannel` unterstützt wird) und ob die anderen Bindungselemente der Bindung diese Kanalform unterstützen.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> überprüft zunächst, ob die angeforderte Kanalform erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichtenaktionen auf. Es erstellt dann eine neue `ChunkingChannelFactory` und übergibt diese an die innere Kanalfactory. (Wenn Sie ein Transportbindungselement erstellen, ist dieses Element das letzte im Bindungsstapel und muss daher einen Kanallistener oder eine Kanalfactory erstellen.)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.  
  
 Ein weiteres Beispiel: einen Transportkanal der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel bietet die folgenden außer Kraft setzen.  
  
 Im Beispiel ist das Bindungselement `UdpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird. Es überschreibt die folgenden Methoden zum Erstellen der dem Kanal zugeordneten Factorys.  
  
```csharp  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 Es enthält auch Member zum Klonen des `BindingElement` und Zurückgeben unseres Schemas (soap.udp).  
  
#### <a name="protocol-binding-elements"></a>Protokollbindungselemente  
 Neue Bindungselemente können einbezogene Bindungselemente ersetzen oder erweitern sowie neue Transporte, Codierungen oder Protokolle auf höherer Ebene hinzufügen. Um ein neues Protokollbindungselement zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse. Zumindest müssen anschließend implementieren Sie die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> und Implementieren der `ChannelProtectionRequirements` mit <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. Dadurch werden die <xref:System.ServiceModel.Security.ChannelProtectionRequirements> für dieses Bindungselement zurückgegeben.  Weitere Informationen finden Sie unter <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> sollte eine neue Kopie dieses Bindungselements zurückgeben. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
#### <a name="transport-binding-elements"></a>Transportbindungselemente  
 Um ein neues Transportbindungselement zu erstellen, erweitern Sie die <xref:System.ServiceModel.Channels.TransportBindingElement>-Schnittstelle. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode und die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Sollte eine neue Kopie dieses Bindungselements zurückgeben.  Es wird empfohlen, dass Autoren von Bindungselementen einen Klon implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – Die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> get-Eigenschaft gibt das URI-Schema für das Transportprotokoll zurück, das vom Bindungselement dargestellt wird. Z. B. die <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> und <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> Zurückgeben von "http" und "net.tcp" von ihren jeweiligen <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> Eigenschaften.  
  
#### <a name="encoding-binding-elements"></a>Codierungsbindungselemente  
 Um neue Codierungsbindungselemente zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse und implementieren die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>-Klasse. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode, die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType>-Methode und die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Gibt eine neue Kopie dieses Bindungselements zurück. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Gibt <xref:System.ServiceModel.Channels.MessageEncoderFactory> zurück, die ein Handle für eine tatsächliche Klasse bereitstellt, die den neuen Encoder implementiert und <xref:System.ServiceModel.Channels.MessageEncoder> erweitern sollte. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncoderFactory> und <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Gibt die in dieser Codierung verwendete <xref:System.ServiceModel.Channels.MessageVersion> zurück, die die verwendeten Versionen von SOAP und WS-Adressierung darstellt.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften zu benutzerdefinierten Codierungsbindungselementen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Weitere Informationen zum Erstellen eines neuen Bindungselements finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Nachdem Sie ein Bindungselement für den Kanal erstellt haben, zurück zu den [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md) Thema finden, ob Sie Unterstützung der Konfigurationsdatei zu Ihrem Bindungselement hinzufügen möchten wenn "und" Gewusst wie: Hinzufügen von metadatenunterstützung für Veröffentlichung, und ob und wie eine benutzerdefinierte Bindung erstellen, die Ihr Bindungselement verwendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.BindingElement>
- [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md)
- [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
