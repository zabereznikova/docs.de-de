---
title: "Erstellen eines BindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 01a35307-a41f-4ef6-a3db-322af40afc99
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Erstellen eines BindingElement
Bindungen und Bindungselemente \(Objekte, die <xref:System.ServiceModel.Channels.Binding?displayProperty=fullName> bzw. <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> erweitern\) sind die Orte, an denen das [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Anwendungsmodell mit Kanalfactorys und Kanallistenern verknüpft wird.Ohne Bindungen erfordern benutzerdefinierte Kanäle das Programmieren auf Kanalebene, wie in [Dienst\-Kanalebenenprogrammierung](../../../../docs/framework/wcf/extending/service-channel-level-programming.md) und [Client\-Kanalebenenprogrammierung](../../../../docs/framework/wcf/extending/client-channel-level-programming.md) beschrieben.In diesem Thema werden die Mindestanforderungen für die Aktivierung Ihres Kanals in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], für die Entwicklung eines <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal und für die Aktivierung von der Anwendung aus erläutert, wie in Schritt 4 unter [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md) beschrieben.  
  
## Übersicht  
 Durch Erstellen von <xref:System.ServiceModel.Channels.BindingElement> für Ihren Kanal können Entwickler ihn in einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung nutzen.<xref:System.ServiceModel.Channels.BindingElement>\-Objekte können aus der <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>\-Klasse verwendet werden, um eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung mit Ihrem Kanal zu verbinden, ohne dem genauen Informationstyp Ihres Kanals entsprechen zu müssen..  
  
 Sobald ein <xref:System.ServiceModel.Channels.BindingElement> erstellt wurde, können Sie je nach Anforderungen weitere Funktionen aktivieren, indem Sie die unter [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md) beschriebenen verbleibenden Kanalentwicklungsschritte ausführen.  
  
## Hinzufügen eines Bindungselements  
 Um ein benutzerdefiniertes <xref:System.ServiceModel.Channels.BindingElement> zu implementieren, schreiben Sie eine Klasse, die von <xref:System.ServiceModel.Channels.BindingElement> erbt.Wenn Sie beispielsweise einen `ChunkingChannel` entwickelt haben, der große Nachrichten segmentieren und sie am anderen Ende wieder zusammensetzen kann, können Sie diesen Kanal in jeder Bindung verwenden, indem Sie ein <xref:System.ServiceModel.Channels.BindingElement> implementieren und die Bindung für die entsprechende Verwendung konfigurieren.In diesem Thema wird der `ChunkingChannel` als Beispiel zur Demonstration der Implementierungsanforderungen eines Bindungselements verwendet.  
  
 Ein `ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich.Es überschreibt die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelFactory%2A>\-Implementierung und die <xref:System.ServiceModel.Channels.BindingElement.CanBuildChannelListener%2A>\-Implementierung und überprüft, ob der Typparameter <xref:System.ServiceModel.Channels.IDuplexSessionChannel> lautet \(in unserem Beispiel ist dies die einzige Kanalform, die von `ChunkingChannel` unterstützt wird\) und ob die anderen Bindungselemente der Bindung diese Kanalform unterstützen.  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> überprüft zunächst, ob die angeforderte Kanalform erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichtenaktionen auf.Es erstellt dann eine neue `ChunkingChannelFactory` und übergibt diese an die innere Kanalfactory.\(Wenn Sie ein Transportbindungselement erstellen, ist dieses Element das letzte im Bindungsstapel und muss daher einen Kanallistener oder eine Kanalfactory erstellen.\)  
  
 <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.  
  
 Im Beispiel [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) wird die folgende Überschreibung als weitere Möglichkeit für einen Transportkanal bereitgestellt.  
  
 Im Beispiel ist das Bindungselement `UdpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird.Es überschreibt die folgenden Methoden zum Erstellen der dem Kanal zugeordneten Factorys.  
  
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
  
 Es enthält auch Member zum Klonen des `BindingElement` und Zurückgeben unseres Schemas \(soap.udp\).  
  
#### Protokollbindungselemente  
 Neue Bindungselemente können einbezogene Bindungselemente ersetzen oder erweitern sowie neue Transporte, Codierungen oder Protokolle auf höherer Ebene hinzufügen.Um ein neues Protokollbindungselement zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>\-Klasse.Anschließend müssen Sie mindestens das <xref:System.ServiceModel.Channels.BindingElement.Clone%2A?displayProperty=fullName> und die `ChannelProtectionRequirements` unter Verwendung von <xref:System.ServiceModel.Channels.IChannel.GetProperty%2A?displayProperty=fullName> implementieren.Dadurch werden die <xref:System.ServiceModel.Security.ChannelProtectionRequirements> für dieses Bindungselement zurückgegeben.Weitere Informationen finden Sie unter <xref:System.ServiceModel.Security.ChannelProtectionRequirements>.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> sollte eine neue Kopie dieses Bindungselements zurückgeben.Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen\-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
#### Transportbindungselemente  
 Um ein neues Transportbindungselement zu erstellen, erweitern Sie die <xref:System.ServiceModel.Channels.TransportBindingElement>\-Schnittstelle.Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>\-Methode und die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A?displayProperty=fullName>\-Eigenschaft implementieren.  
  
 <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> – Sollte eine neue Kopie dieses Bindungselements zurückgeben.Es wird empfohlen, dass Autoren von Bindungsemelenten einen Klon implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen\-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
 <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> – Die <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A> get\-Eigenschaft gibt das URI\-Schema für das Transportprotokoll zurück, das vom Bindungselement dargestellt wird.Das <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> und das <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=fullName> geben z. B. "http" und "net.tcp" von ihren jeweiligen <xref:System.ServiceModel.Channels.TransportBindingElement.Scheme%2A>\-Eigenschaften zurück.  
  
#### Codierungsbindungselemente  
 Um neue Codierungsbindungselemente zu erstellen, erweitern Sie zunächst die <xref:System.ServiceModel.Channels.BindingElement>\-Klasse und implementieren die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=fullName>\-Klasse.Anschließend müssen Sie mindestens die <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>\-Methode, die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A?displayProperty=fullName>\-Methode und die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A?displayProperty=fullName>\-Eigenschaft implementieren.  
  
-   <xref:System.ServiceModel.Channels.BindingElement.Clone%2A>.Gibt eine neue Kopie dieses Bindungselements zurück.Es wird empfohlen, dass Autoren von Bindungselementen <xref:System.ServiceModel.Channels.BindingElement.Clone%2A> implementieren, indem sie einen Kopierkonstruktor verwenden, der den Basisklassen\-Kopierkonstruktor aufruft, und anschließend zusätzliche Felder in dieser Klasse klonen.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>.Gibt <xref:System.ServiceModel.Channels.MessageEncoderFactory> zurück, die ein Handle für eine tatsächliche Klasse bereitstellt, die den neuen Encoder implementiert und <xref:System.ServiceModel.Channels.MessageEncoder> erweitern sollte.Weitere Informationen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncoderFactory> und <xref:System.ServiceModel.Channels.MessageEncoder>.  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.MessageVersion%2A>.Gibt die in dieser Codierung verwendete <xref:System.ServiceModel.Channels.MessageVersion> zurück, die die verwendeten Versionen von SOAP und WS\-Adressierung darstellt.  
  
 Eine vollständige Liste optionaler Methoden und Eigenschaften zu benutzerdefinierten Codierungsbindungselementen finden Sie unter <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.  
  
 Weitere Informationen zum Erstellen eines neuen Bindungselements finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
 Nachdem Sie ein Bindungselement für Ihren Kanal erstellt haben, kehren Sie zum Thema [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md) zurück. Hier können Sie entscheiden, ob Sie Unterstützung für die Konfigurationsdatei zu Ihrem Bindungselement hinzufügen möchten, ob und wie Sie Unterstützung für die Metadatenveröffentlichung hinzufügen möchten und ob und wie Sie eine benutzerdefinierte Bindung erstellen, die Ihr Bindungselement verwendet.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.BindingElement>   
 [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md)   
 [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)