---
title: Erstellen eines BindingElement
ms.date: 03/30/2017
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
ms.openlocfilehash: 96924e97ad3fcc121ef7b28125301060d8448514
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="creating-a-bindingelement"></a>Erstellen eines BindingElement
Bindungen und Bindungselemente (Objekte, die erweitern <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType> und <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>bzw.) sind die Orte, wo das Anwendungsmodell für Windows Communication Foundation (WCF) mit kanalfactorys und Kanallistenern verknüpft ist. Ohne Bindungen mithilfe von benutzerdefinierten Kanälen erfordert Programmierung auf Kanalebene wie beschrieben in [Programmierung auf Kanalebene Dienst](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) und [Programmierung auf Kanalebene Client](../../../../docs/framework/wcf/extending/client-channel-level-programming.md). In diesem Thema wird erläutert, die Mindestanforderung zu aktivieren, verwenden den Kanal in WCF, die Entwicklung von einem <xref:System.ServiceModel.Channels.BindingElement> für Ihr Kanal, und aktivieren, verwenden Sie aus der Anwendung, wie in Schritt 4 des beschrieben [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="overview"></a>Übersicht  
 Erstellen einer <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal Entwicklern für die Verwendung in einer WCF-Anwendung ermöglicht. <xref:System.ServiceModel.Channels.BindingElement> Objekte können verwendet werden, aus der <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> Klasse, um einen WCF-Anwendung mit Ihrem Kanal zu verbinden, ohne dass die genauen Informationstyp Ihres Kanals erforderlich.  
  
 Einmal eine <xref:System.ServiceModel.Channels.BindingElement> wurde erstellt, Sie können weitere Funktionen, die abhängig von Ihren Anforderungen durch die verbleibenden Kanal Entwicklungsschritte beschrieben, die folgende [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
## <a name="adding-a-binding-element"></a>Hinzufügen eines Bindungselements  
 Um ein benutzerdefiniertes <xref:System.ServiceModel.Channels.BindingElement> zu implementieren, schreiben Sie eine Klasse, die von <xref:System.ServiceModel.Channels.BindingElement> erbt. Wenn Sie beispielsweise einen `ChunkingChannel` entwickelt haben, der große Nachrichten segmentieren und sie am anderen Ende wieder zusammensetzen kann, können Sie diesen Kanal in jeder Bindung verwenden, indem Sie ein <xref:System.ServiceModel.Channels.BindingElement> implementieren und die Bindung für die entsprechende Verwendung konfigurieren. In diesem Thema wird der `ChunkingChannel` als Beispiel zur Demonstration der Implementierungsanforderungen eines Bindungselements verwendet.  
  
 Ein `ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich. Es überschreibt die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A>-Implementierung und die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>-Implementierung und überprüft, ob der Typparameter <xref:System.ServiceModel.Channels.IDuplexSessionChannel> lautet (in unserem Beispiel ist dies die einzige Kanalform, die von `ChunkingChannel` unterstützt wird) und ob die anderen Bindungselemente der Bindung diese Kanalform unterstützen.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> überprüft zunächst, ob die angeforderte Kanalform erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichtenaktionen auf. Es erstellt dann eine neue `ChunkingChannelFactory` und übergibt diese an die innere Kanalfactory. (Wenn Sie ein Transportbindungselement erstellen, ist dieses Element das letzte im Bindungsstapel und muss daher einen Kanallistener oder eine Kanalfactory erstellen.)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.  
  
 Ein weiteres Beispiel: einen Transportkanal mithilfe der [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel bietet die folgenden Außerkraftsetzung.  
  
 Im Beispiel ist das Bindungselement `UdpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird. Es überschreibt die folgenden Methoden zum Erstellen der dem Kanal zugeordneten Factorys.  
  
```  
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
 Neue Bindungselemente können einbezogene Bindungselemente ersetzen oder erweitern sowie neue Transporte, Codierungen oder Protokolle auf höherer Ebene hinzufügen. Um ein neues Protokollbindungselement zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse. Sie müssen dann implementieren, mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=nameWithType> und Implementieren der `ChannelProtectionRequirements` mit <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=nameWithType>. Dadurch werden die <xref:System.ServiceModel.Security.ChannelProtectionRequirements> für dieses Bindungselement zurückgegeben.  Weitere Informationen finden Sie unter <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> sollte eine neue Kopie dieses Bindungselements zurückgeben. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
#### <a name="transport-binding-elements"></a>Transportbindungselemente  
 Um ein neues Transportbindungselement zu erstellen, erweitern Sie die <xref:System.ServiceModel.Channels.TransportBindingElement>-Schnittstelle. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode und die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Sollte eine neue Kopie dieses Bindungselements zurückgeben.  Es wird empfohlen, dass Autoren von Bindungselementen einen Klon implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – Die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> get-Eigenschaft gibt das URI-Schema für das Transportprotokoll zurück, das vom Bindungselement dargestellt wird. Z. B. die <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> und <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType> Zurückgeben von "http" und "net.tcp" von ihren jeweiligen <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> Eigenschaften.  
  
#### <a name="encoding-binding-elements"></a>Codierungsbindungselemente  
 Um neue Codierungsbindungselemente zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>-Klasse und implementieren die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>-Klasse. Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>-Methode, die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=nameWithType>-Methode und die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=nameWithType>-Eigenschaft implementieren.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> Gibt eine neue Kopie dieses Bindungselements zurück. Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> Gibt <xref:System.ServiceModel.Channels.MessageEncoderFactory> zurück, die ein Handle für eine tatsächliche Klasse bereitstellt, die den neuen Encoder implementiert und <xref:System.ServiceModel.Channels.MessageEncoder> erweitern sollte. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncoderFactory> und <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A> Gibt die in dieser Codierung verwendete <xref:System.ServiceModel.Channels.MessageVersion> zurück, die die verwendeten Versionen von SOAP und WS-Adressierung darstellt.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften zu benutzerdefinierten Codierungsbindungselementen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Weitere Informationen zum Erstellen eines neuen Bindungselements finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Nachdem Sie ein Bindungselement für den Kanal erstellt haben, zurück zu den [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md) Thema, um anzuzeigen, ob Sie Ihr Bindungselement konfigurationsdateiunterstützung hinzuzufügende Wenn und zum Hinzufügen von metadatenunterstützung für Veröffentlichung, und ob und wie die zur Erstellung einer benutzerdefinierten Bindung, die Ihr Bindungselement verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md)  
 [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)
