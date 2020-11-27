---
title: Erstellen eines BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 285bed029cf8487b37757de6a56075abe448f3ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257866"
---
# <a name="creating-a-bindingelement"></a>Erstellen eines BindingElement

Bindungen und Bindungs Elemente (Objekte, die <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> bzw. erweitern, sind die Stelle, an der das Windows Communication Foundation (WCF)-Anwendungsmodell Kanalfactorys und Kanallistener zugeordnet ist. Ohne Bindungen erfordert die Verwendung von benutzerdefinierten Kanälen die Programmierung auf Kanal Ebene, wie unter [Service Channel-Level Programming](service-channel-level-programming.md) and [Client Channel-Level Programming](client-channel-level-programming.md)beschrieben. In diesem Thema werden die Mindestanforderungen für die Aktivierung der Verwendung Ihres Kanals in WCF, die Entwicklung eines <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal und die Verwendung von der Anwendung, wie in Schritt 4 der [Entwicklung von Kanälen](developing-channels.md)beschrieben, erläutert.  
  
## <a name="overview"></a>Übersicht  

 <xref:System.ServiceModel.Channels.BindingElement>Wenn Sie einen für Ihren Kanal erstellen, können Entwickler ihn in einer WCF-Anwendung verwenden. <xref:System.ServiceModel.Channels.BindingElement> -Objekte können von der- <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> Klasse verwendet werden, um eine WCF-Anwendung mit Ihrem Channel zu verbinden, ohne die genauen Typinformationen Ihres Kanals zu benötigen.  
  
 Nachdem ein <xref:System.ServiceModel.Channels.BindingElement> erstellt wurde, können Sie je nach Ihren Anforderungen weitere Funktionen aktivieren, indem Sie die verbleibenden Schritte für die Kanalentwicklung befolgen, die unter [entwickeln von Kanälen](developing-channels.md)beschrieben werden.  
  
## <a name="adding-a-binding-element"></a>Hinzufügen eines Bindungselements  

 Um ein benutzerdefiniertes <xref:System.ServiceModel.Channels.BindingElement> zu implementieren, schreiben Sie eine Klasse, die von <xref:System.ServiceModel.Channels.BindingElement> erbt. Wenn Sie beispielsweise einen `ChunkingChannel` entwickelt haben, der große Nachrichten segmentieren und sie am anderen Ende wieder zusammensetzen kann, können Sie diesen Kanal in jeder Bindung verwenden, indem Sie ein <xref:System.ServiceModel.Channels.BindingElement> implementieren und die Bindung für die entsprechende Verwendung konfigurieren. In diesem Thema wird der `ChunkingChannel` als Beispiel zur Demonstration der Implementierungsanforderungen eines Bindungselements verwendet.  
  
 Ein `ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich. Es überschreibt die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A>-Implementierung und die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>-Implementierung und überprüft, ob der Typparameter <xref:System.ServiceModel.Channels.IDuplexSessionChannel> lautet (in unserem Beispiel ist dies die einzige Kanalform, die von `ChunkingChannel` unterstützt wird) und ob die anderen Bindungselemente der Bindung diese Kanalform unterstützen.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> überprüft zunächst, ob die angeforderte Kanalform erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichtenaktionen auf. Es erstellt dann eine neue `ChunkingChannelFactory` und übergibt diese an die innere Kanalfactory. (Wenn Sie ein Transportbindungselement erstellen, ist dieses Element das letzte im Bindungsstapel und muss daher einen Kanallistener oder eine Kanalfactory erstellen.)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.  
  
 Ein weiteres Beispiel [für die Verwendung eines Transport Kanals](../samples/transport-udp.md) ist die folgende außer Kraft Setzung.  
  
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

 Neue Bindungselemente können einbezogene Bindungselemente ersetzen oder erweitern sowie neue Transporte, Codierungen oder Protokolle auf höherer Ebene hinzufügen. Um ein neues Protokollbindungselement zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse. Sie müssen mindestens die implementieren <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> und mithilfe von implementieren `ChannelProtectionRequirements` <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType> . Dadurch werden die <xref:System.ServiceModel.Security.ChannelProtectionRequirements> für dieses Bindungselement zurückgegeben.  Weitere Informationen finden Sie unter <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> sollte eine neue Kopie dieses Bindungselements zurückgeben. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
#### <a name="transport-binding-elements"></a>Transportbindungselemente  

 Um ein neues Transportbindungselement zu erstellen, erweitern Sie die <xref:System.ServiceModel.Channels.TransportBindingElement>-Schnittstelle. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode und die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Sollte eine neue Kopie dieses Bindungselements zurückgeben.  Es wird empfohlen, dass Autoren von Bindungselementen einen Klon implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – Die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> get-Eigenschaft gibt das URI-Schema für das Transportprotokoll zurück, das vom Bindungselement dargestellt wird. Beispielsweise <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> geben und "http" und "net. TCP" aus ihren jeweiligen <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> Eigenschaften zurück.  
  
#### <a name="encoding-binding-elements"></a>Codierungsbindungselemente  

 Um neue Codierungsbindungselemente zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse und implementieren die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>-Klasse. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode, die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType>-Methode und die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
- <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>. Gibt eine neue Kopie dieses Bindungselements zurück. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>. Gibt <xref:System.ServiceModel.Channels.MessageEncoderFactory> zurück, die ein Handle für eine tatsächliche Klasse bereitstellt, die den neuen Encoder implementiert und <xref:System.ServiceModel.Channels.MessageEncoder> erweitern sollte. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncoderFactory> und <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>. Gibt die in dieser Codierung verwendete <xref:System.ServiceModel.Channels.MessageVersion> zurück, die die verwendeten Versionen von SOAP und WS-Adressierung darstellt.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften zu benutzerdefinierten Codierungsbindungselementen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Weitere Informationen zum Erstellen eines neuen Bindungs Elements finden Sie unter [Erstellen von User-Defined Bindungen](creating-user-defined-bindings.md).  
  
 Nachdem Sie ein Bindungs Element für Ihren Kanal erstellt haben, kehren Sie zum Thema [entwickeln von Kanälen](developing-channels.md) zurück, um zu sehen, ob Sie dem Bindungs Element Konfigurationsdatei Unterstützung hinzufügen, ob und wie Sie Unterstützung für Metadatenveröffentlichung hinzufügen möchten und ob und wie Sie eine benutzerdefinierte Bindung erstellen, die ihr Bindungs Element verwendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.BindingElement>
- [Entwickeln von Kanälen](developing-channels.md)
- [Transport: UDP](../samples/transport-udp.md)
