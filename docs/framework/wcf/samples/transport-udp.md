---
title: "Transport: UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
caps.latest.revision: 48
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 48
---
# Transport: UDP
Das Beispiel zum UDB\-Transport veranschaulicht, wie UDP\-Unicast und \-Multicast als benutzerdefinierter [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Transport implementiert werden können.In dem Beispiel wird die empfohlene Vorgehensweise zum Erstellen eines benutzerdefinierten Transports in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] anhand des Kanalframeworks und der empfohlenen Vorgehensweisen für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] beschrieben.Die Schritte zum Erstellen eines benutzerdefinierten Transports lauten wie folgt:  
  
1.  Legen Sie fest, welche [Nachrichtenaustauschmuster](#MessageExchangePatterns) für den Kanal \(IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel oder IReplyChannel\) von der ChannelFactory und vom ChannelListener unterstützt werden sollen.Dann entscheiden Sie sich, ob Sie die sitzungsbasierten Variationen dieser Schnittstellen unterstützen.  
  
2.  Erstellen Sie eine Kanalfactory und einen Kanallistener, die Ihr Nachrichtenaustauschmuster unterstützen.  
  
3.  Stellen Sie sicher, dass alle netzwerkspezifischen Ausnahmen zu der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden.  
  
4.  Fügen Sie ein [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Element hinzu, das den benutzerdefinierten Transport einem Kanalstapel hinzufügt.Weitere Informationen finden Sie unter [Hinzufügen eines Bindungselements](#AddingABindingElement).  
  
5.  Fügen Sie einen Bindungselementerweiterungs\-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen.  
  
6.  Fügen Sie Metadatenerweiterungen hinzu, um anderen Endpunkten Funktionen mitzuteilen.  
  
7.  Fügen Sie eine Bindung hinzu, die einen Stapel mit Bindungselementen entsprechend einem genau definierten Profil vorkonfiguriert.Weitere Informationen finden Sie unter [Hinzufügen einer Standardbindung](#AddingAStandardBinding).  
  
8.  Fügen Sie einen Bindungsabschnitt und ein Bindungskonfigurationselement hinzu, um die Bindung für das Konfigurationssystem verfügbar zu machen.Weitere Informationen finden Sie unter [Hinzufügen von Konfigurationsunterstützung](#AddingConfigurationSupport).  
  
<a name="MessageExchangePatterns"></a>   
## Nachrichtenaustauschmuster  
 Der erste Schritt beim Schreiben eines benutzerdefinierten Transports besteht darin zu entscheiden, welche Nachrichtenaustauschmuster für den Transport erforderlich sind.Es stehen drei Nachrichtenaustauschmuster zur Auswahl:  
  
-   Datagramm \(IInputChannel\/IOutputChannel\)  
  
     Bei Verwendung eines Datagramm\-Nachrichtenaustauschmusters sendet ein Client eine Nachricht mit einem "fire and forget"\-Austausch.Ein "fire and forget"\-Austausch erfordert eine Out\-of\-Band\-Bestätigung für die erfolgreiche Zustellung.Die Nachricht könnte unterwegs verloren gehen und den Dienst nicht erreichen.Wenn der Sendevorgang auf der Clientseite erfolgreich abgeschlossen wird, stellt dies keine Garantie dar, dass der Remoteendpunkt die Nachricht erhalten hat.Das Datagramm ist ein wesentlicher Baustein für den Nachrichtenaustausch, da Sie eigene Protokolle damit erstellen können, einschließlich zuverlässiger Protokolle und sicherer Protokolle.Clientdatagrammkanäle implementieren die <xref:System.ServiceModel.Channels.IOutputChannel>\-Schnittstelle, und Dienstdatagrammkanäle implementieren die <xref:System.ServiceModel.Channels.IInputChannel>\-Schnittstelle.  
  
-   Anforderung\-Antwort \(IRequestChannel\/IReplyChannel\)  
  
     In diesem Nachrichtenaustauschmuster wird eine Nachricht gesendet, und eine Antwort wird empfangen.Das Muster besteht aus Anforderungs\-Antwort\-Paaren.Beispiele für Anforderungs\-Antwort\-Aufrufe sind Remoteprozeduraufrufe \(RPC\) und Browser\-GET\-Anforderungen.Dieses Muster wird auch als Halbduplex bezeichnet.In diesem Nachrichtenaustauschmuster implementieren Clientkanäle <xref:System.ServiceModel.Channels.IRequestChannel>, und Dienstkanäle implementieren <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
-   Duplex \(IDuplexChannel\)  
  
     Das Duplex\-Nachrichtenaustauschmuster ermöglicht, dass eine willkürliche Anzahl von Nachrichten von einem Client gesendet und in beliebiger Reihenfolge empfangen wird.Das Duplex\-Nachrichtenaustauschmuster ist mit einem Telefongespräch vergleichbar, bei dem jedes gesprochene Wort einer Nachricht entspricht.Da beide Teilnehmer in diesem Nachrichtenaustauschmuster senden und empfangen können, ist die vom Client und von den Dienstkanälen implementierte Schnittstelle <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 Jedes dieser Nachrichtenaustauschmuster kann außerdem Sitzungen unterstützen.Die neue Funktion von sitzungsfähigen Kanälen besteht darin, dass alle in einem Kanal gesendeten und empfangenen Nachrichten korreliert werden.Das Anforderungs\-Antwort\-Muster ist eine eigenständige, aus zwei Nachrichten bestehende Sitzung, da die Anforderung und die Antwort korreliert werden.Demgegenüber impliziert das Anforderungs\-Antwort\-Muster, das Sitzungen unterstützt, dass alle Anforderungs\-\/Antwort\-Paare in diesem Kanal miteinander korreliert werden.Dadurch ergeben sich sechs Nachrichtenaustauschmuster zur Auswahl: Datagramm, Anforderung\-Antwort, Duplex, Datagramm mit Sitzungen, Anforderung\-Antwort mit Sitzungen und Duplex mit Sitzungen.  
  
> [!NOTE]
>  Für den UDP\-Transport wird nur das Nachrichtenaustauschmuster Datagramm unterstützt, da UDP grundsätzlich ein "fire and forget"\-Protokoll ist.  
  
### Der ICommunicationObject\- und der WCF\-Objektlebenszyklus  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hat einen allgemeinen Zustandsautomaten, der zum Verwalten des Legenszyklus von Objekten wie <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory> und <xref:System.ServiceModel.Channels.IChannelListener> verwendet wird, die für die Kommunikation verwendet werden.Es gibt fünf Zustände, in denen diese Kommunikationsobjekte vorhanden sein können.Die Zustände werden durch die <xref:System.ServiceModel.CommunicationState>\-Enumeration dargestellt und lauten wie folgt:  
  
-   Created: Dies ist der Zustand eines <xref:System.ServiceModel.ICommunicationObject>, wenn es zuerst instanziiert wird.In diesem Zustand tritt keine Eingabe\/Ausgabe \(E\/A\) auf.  
  
-   Opening: Das Objekt geht zu diesem Zustand über, wenn <xref:System.ServiceModel.ICommunicationObject.Open%2A> aufgerufen wird.An diesem Punkt werden Eigenschaften unveränderlich gemacht, und Eingabe\/Ausgabe kann beginnen.Dieser Übergang ist nur vom Created\-Zustand aus gültig.  
  
-   Opened: Das Objekt geht zu diesem Zustand über, wenn der geöffnete Prozess abgeschlossen wird.Dieser Übergang ist nur vom Opening\-Zustand aus gültig.An diesem Punkt ist das Objekt für die Übertragung voll verwendbar.  
  
-   Closing: Das Objekt geht zu diesem Zustand über, wenn <xref:System.ServiceModel.ICommunicationObject.Close%2A> für ein ordnungsgemäßes Herunterfahren aufgerufen wird.Dieser Übergang ist nur vom Opened\-Zustand aus gültig.  
  
-   Closed: Objekte im Closed\-Zustand sind nicht mehr verwendbar.Im Allgemeinen steht der größte Teil der Konfiguration noch zur Ansicht bereit, es kann aber keine Kommunikation auftreten.Dieser Zustand ist mit "Verworfen" vergleichbar.  
  
-   Faulted: Auf Objekte im Faulted\-Zustand kann für die Inspektion zugegriffen werden, sie sind aber nicht mehr verwendbar.Wenn ein nicht behebbarer Fehler auftritt, geht das Objekt in diesen Zustand über.Von diesem Zustand ist nur der Übergang in den `Closed`\-Zustand gültig.  
  
 Es gibt Ereignisse, die für jeden Zustandsübergang ausgelöst werden.Die <xref:System.ServiceModel.ICommunicationObject.Abort%2A>\-Methode kann jederzeit aufgerufen werden und sorgt dafür, dass das Objekt sofort vom aktuellen Zustand in den Closed\-Zustand übergeht.Beim Aufrufen von <xref:System.ServiceModel.ICommunicationObject.Abort%2A> wird nicht abgeschlossene Arbeit beendet.  
  
<a name="ChannelAndChannelListener"></a>   
## Kanalfactory und Kanallistener  
 Der nächste Schritt beim Schreiben eines benutzerdefinierten Transports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle und von <xref:System.ServiceModel.Channels.IChannelListener> für Dienstkanäle.Die Kanalschicht verwendet ein Factorymuster zum Erstellen von Kanälen.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt Basisklassenhilfen für diesen Prozess bereit.  
  
-   Die <xref:System.ServiceModel.Channels.CommunicationObject>\-Klasse implementiert <xref:System.ServiceModel.ICommunicationObject> und setzt den zuvor in Schritt 2 beschriebenen Zustandsautomaten durch.  
  
-   Die``<xref:System.ServiceModel.Channels.ChannelManagerBase>\-Klasse implementiert <xref:System.ServiceModel.Channels.CommunicationObject> und stellt eine einheitliche Basisklasse für <xref:System.ServiceModel.Channels.ChannelFactoryBase> und <xref:System.ServiceModel.Channels.ChannelListenerBase> bereit.Die <xref:System.ServiceModel.Channels.ChannelManagerBase>\-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.  
  
-   Die``<xref:System.ServiceModel.Channels.ChannelFactoryBase>\-Klasse implementiert <xref:System.ServiceModel.Channels.ChannelManagerBase> und <xref:System.ServiceModel.Channels.IChannelFactory> und konsolidiert die `CreateChannel`\-Überladungen in einer abstrakten `OnCreateChannel`\-Methode.  
  
-   Die <xref:System.ServiceModel.Channels.ChannelListenerBase>\-Klasse implementiert <xref:System.ServiceModel.Channels.IChannelListener>.Die Klasse wird für grundlegende Zustandsverwaltung verwendet.  
  
 In diesem Beispiel ist die Factoryimplementierung in "UdpChannelFactory.cs" enthalten, und die Listenerimplementierung ist in "UdpChannelListener.cs" enthalten.Die <xref:System.ServiceModel.Channels.IChannel>\-Implementierungen sind in "UdpOutputChannel.cs" und "UdpInputChannel.cs" enthalten.  
  
### Die UDP\-Kanalfactory  
 Die `UdpChannelFactory` wird von <xref:System.ServiceModel.Channels.ChannelFactoryBase> abgeleitet.Das Beispiel überschreibt <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A>, um Zugriff auf die Nachrichtenversion des Nachrichtenencoders zu gewähren.Das Beispiel überschreibt auch <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, um beim Übergang des Zustandsautomaten die Instanz von <xref:System.ServiceModel.Channels.BufferManager> zu beenden.  
  
#### Der UDP\-Ausgabekanal  
 Der `UdpOutputChannel` implementiert <xref:System.ServiceModel.Channels.IOutputChannel>.Der Konstruktor überprüft die Argumente und erstellt ein Ziel\-<xref:System.Net.EndPoint>\-Objekt, das auf der übergebenen <xref:System.ServiceModel.EndpointAddress> basiert.  
  
```  
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
  
```  
  
 Der Kanal kann ordnungsgemäß oder nicht ordnungsgemäß geschlossen werden.Bei ordnungsgemäßer Schließung wird der Socket geschlossen, und die `OnClose`\-Methode der Basisklasse wird aufgerufen.Wenn dadurch eine Ausnahme ausgelöst wird, ruft die Infrastruktur `Abort` auf, um sicherzustellen, dass der Kanal bereinigt wird.  
  
```  
this.socket.Close(0);  
  
```  
  
 Implementieren Sie anschließend `Send()` und `BeginSend()`\/`EndSend()`.Dieser Vorgang ist in zwei Hauptabschnitte unterteilt.Serialisieren Sie zuerst die Nachricht in ein Bytearray:  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
  
```  
  
 Senden Sie anschließend die resultierenden Daten:  
  
```  
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### Der UdpChannelListener  
 Der ``UdpChannelListener, der in dem Beispiel implementiert wird, wird von der <xref:System.ServiceModel.Channels.ChannelListenerBase>\-Klasse abgeleitet.Er verwendet einen einzelnen UDP\-Socket, um Datagramme zu empfangen.Die `OnOpen`\-Methode empfängt Daten mit dem UDP\-Socket in einer asynchronen Schleife.Die Daten werden dann mit dem Nachrichtencodierungsframework in Nachrichten konvertiert:  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 Da derselbe Datagrammkanal Nachrichten darstellt, die aus einer Reihe von Quellen eintreffen, ist der `UdpChannelListener` ein Singletonlistener.Es gibt höchstens einen aktiven <xref:System.ServiceModel.Channels.IChannel>``, der diesem Listener gleichzeitig zugeordnet ist.In diesem Beispiel wird nur dann ein weiterer generiert, wenn ein Kanal, der mit der `AcceptChannel`\-Methode zurückgegeben wird, anschließend freigegeben wird.Wenn eine Nachricht empfangen wird, wird sie in diesem Singletonkanal in die Warteschlange eingereiht.  
  
#### UdpInputChannel  
 Die `UdpInputChannel`\-Klasse implementiert `IInputChannel`.Sie besteht aus einer Warteschlange mit eingehenden Nachrichten, die vom `UdpChannelListener`\-Socket gefüllt wird.Diese Nachrichten werden mit der `IInputChannel.Receive```\-Methode aus der Warteschlange entfernt.  
  
<a name="AddingABindingElement"></a>   
## Hinzufügen eines Bindungselements  
 Nachdem nun die Factorys und Kanäle erstellt sind, müssen sie der ServiceModel\-Laufzeit über eine Bindung verfügbar gemacht werden.Eine Bindung ist eine Auflistung von Bindungselementen, die den mit einer Dienstadresse verknüpften Kommunikationsstapel darstellt.Jedes Element im Stapel wird durch ein [\<Bindung\>](../../../../docs/framework/misc/binding.md)\-Element dargestellt.  
  
 Im Beispiel ist das Bindungselement `UdpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird.Es überschreibt die folgenden Methoden zum Erstellen der der Bindung zugeordneten Factorys.  
  
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
  
## Hinzufügen von Metadatenunterstützung für ein Transportbindungselement  
 Um den Transport in ein Metadatensystem zu integrieren, muss dieser sowohl den Import als auch den Export von Richtlinien unterstützen.Dadurch können mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) die Clients für die Bindung generiert werden.  
  
### Hinzufügen von WSDL\-Unterstützung  
 Das Transportbindungselement in einer Bindung ist für den Export und Import von Adressierungsinformationen in\/zu Metadaten verantwortlich.Bei der Nutzung einer SOAP\-Bindung sollte das Transportbindungselement ebenfalls einen korrekten Transport\-URI in die Metadaten exportieren.  
  
#### WSDL\-Export  
 Um Adressierungsinformationen zu exportieren, implementiert das `UdpTransportBindingElement` die `IWsdlExportExtension`\-Schnittstelle.Die `ExportEndpoint`\-Methode fügt dem WSDL\-Port die richtigen Adressierungsinformationen hinzu.  
  
```  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 Die `UdpTransportBindingElement`\-Implementierung der `ExportEndpoint`\-Methode exportiert ebenfalls einen Transport\-URI, wenn der Endpunkt eine SOAP\-Bindung verwendet.  
  
```  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### WSDL\-Import  
 Um das WSDL\-Importsystem auf die Handhabung des Imports von Adressen zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für "Svcutil.exe" hinzu \(wie in der Datei "Svcutil.exe.config" gezeigt\):  
  
```  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Bei der Ausführung von "Svcutil.exe" gibt es zwei Optionen, um "Svcutil.exe" dazu zu bewegen, die WSDL\-Importerweiterungen zu laden:  
  
1.  Verweisen Sie "Svcutil.exe" mithilfe der \/SvcutilConfig:\<\-Datei\> auf die Konfigurationsdatei.  
  
2.  Fügen Sie den Konfigurationsabschnitt zu "Svcutil.exe.config" im gleichen Verzeichnis wie Svcutil.exe hinzu.  
  
 Der `UdpBindingElementImporter`\-Typ implementiert die `IWsdlImportExtension`\-Schnittstelle.Die `ImportEndpoint`\-Methode importiert die Adresse vom WSDL\-Port.  
  
```  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### Hinzufügen von Richtlinienunterstützung  
 Das benutzerdefinierte Bindungselement kann Richtlinienassertionen in die WSDL\-Bindung für einen Dienstendpunkt exportieren, um die Funktionen dieses Bindungselements auszudrücken.  
  
#### Richtlinienexport  
 Der `UdpTransportBindingElement`\-Typ implementiert```IPolicyExportExtension`, um den Export von Richtlinien zu unterstützen.Als Ergebnis schließt `System.ServiceModel.MetadataExporter``UdpTransportBindingElement` in die Generierung der Richtlinie für eine Bindung, die dieses enthält, ein.  
  
 Fügen Sie in `IPolicyExportExtension.ExportPolicy` eine Assertion für UDP und eine weitere Assertion ein, wenn Sie sich im Multicastmodus befinden.Grund hierfür ist, dass der Multicastmodus Einfluss auf die Art und Weise hat, in der der Kommunikationsstapel erstellt wird, weshalb eine Koordinierung zwischen beiden Seiten stattfinden muss.  
  
```  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Da benutzerdefinierte Transportbindungselemente für die Handhabung der Adressierung verantwortlich sind, muss die `IPolicyExportExtension`\-Implementierung auf dem `UdpTransportBindingElement` auch den Export der geeigneten WS\-Adressierungsrichtlinienassertionen handhaben, um die Version der verwendeten WS\-Adressierung anzugeben.  
  
```  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### Richtlinienimport  
 Um das Richtlinienimportsystem zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für "Svcutil.exe" hinzu \(wie in der Datei "Svcutil.exe.config" gezeigt\):  
  
```  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Dann implementieren Sie `IPolicyImporterExtension` aus der registrierten Klasse \(`UdpBindingElementImporter`\).Prüfen Sie in `ImportPolicy()` die Assertionen im entsprechenden Namespace, verarbeiten Sie sie für die Generierung des Transports, und prüfen Sie, ob Multicast vorliegt.Entfernen Sie darüber hinaus die gehandhabten Assertionen aus der Liste der Bindungsassertionen.Erneut stehen bei der Ausführung von "Svcutil.exe" zwei Optionen für die Integration zur Verfügung:  
  
1.  Verweisen Sie Svcutil.exe mithilfe der \/SvcutilConfig:\<\-Datei\> auf die Konfigurationsdatei.  
  
2.  Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.  
  
<a name="AddingAStandardBinding"></a>   
## Hinzufügen einer Standardbindung  
 Das Bindungselement kann auf die beiden folgenden Arten verwendet werden:  
  
-   Über eine benutzerdefinierte Bindung: Benutzerdefinierte Bindungen erlauben Benutzern, basierend auf einer beliebigen Gruppe von Bindungselementen, eigene Bindungen zu definieren.  
  
-   Über eine vom System zur Verfügung gestellte Bindung, die die erstellte Bindung enthält.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält verschiedene vom System definierte Bindungen, z. B. `BasicHttpBinding`, `NetTcpBinding` und `WsHttpBinding`.Jede dieser Bindungen wird einem genau definierten Profil zugeordnet.  
  
 Das Beispiel implementiert eine Profilbindung in `SampleProfileUdpBinding`, die von <xref:System.ServiceModel.Channels.Binding> abgeleitet wurde.`SampleProfileUdpBinding` enthält bis zu vier Bindungselemente: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` und `ReliableSessionBindingElement`.  
  
```  
public override BindingElementCollection CreateBindingElements()  
{     
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### Hinzufügen eines benutzerdefinierten Standardbindungsimportprogramms  
 "Svcutil.exe" und der `WsdlImporter`\-Typ erkennen und importieren vom System definierte Bindungen standardmäßig.Andernfalls wird die Bindung als `CustomBinding`\-Instanz importiert.Zur Aktivierung des Imports der `SampleProfileUdpBinding` für Svcutil.exe und den `WsdlImporter`, fungiert der `UdpBindingElementImporter` auch als benutzerdefiniertes Standardbindungsimportprogramm.  
  
 Ein benutzerdefiniertes Standardbindungsimportprogramm implementiert die `ImportEndpoint`\-Methode auf der `IWsdlImportExtension`\-Schnittstelle, um zu prüfen, ob die aus den Metadaten importierte `CustomBinding`\-Instanz von einer spezifischen Standardbindung hätte generiert werden können.  
  
```  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 Allgemein beinhaltet die Implementierung eines benutzerdefinierten Standardbindungsimportprogramms die Überprüfung der Eigenschaften der importierten Bindungen, um zu bestätigen, dass sich nur Eigenschaften geändert haben, die von der Standardbindung hätten festgelegt werden können, und es sich bei allen anderen Eigenschaften um die Standardwerte handelt.Eine grundlegende Strategie für die Implementierung eines Standardbindungsimportprogramms ist die Erstellung einer Standardbindung, die Weitergabe der Eigenschaften von den Bindungselementen an die von der Standardbindung unterstützte Standardbindungsinstanz und der Vergleich der Bindungselemente der Standardbindung mit den importierten Bindungselementen.  
  
<a name="AddingConfigurationSupport"></a>   
## Hinzufügen von Konfigurationsunterstützung  
 Um unseren Transport durch Konfiguration verfügbar zu machen, müssen Sie zwei Konfigurationsabschnitte implementieren.Der erste ist ein `BindingElementExtensionElement` für `UdpTransportBindingElement`.Auf diese Weise können `CustomBinding`\-Implementierungen auf das im Beispiel erstellte Bindungselement verweisen.Der zweite ist eine `Configuration` für `SampleProfileUdpBinding`.  
  
### Element für Bindungselementerweiterungen  
 Der``Abschnitt```UdpTransportElement` ist ein `BindingElementExtensionElement`, das `UdpTransportBindingElement` für das Konfigurationssystem verfügbar macht.Mit wenigen grundlegenden Überschreibungen definiert das Beispiel den Konfigurationsabschnittsnamen, den Typ des Bindungselements und wie das Bindungselement erstellt wird.Benutzer können dann wie im folgenden Code den Erweiterungsabschnitt in einer Konfigurationsdatei registrieren.  
  
```  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
  
```  
  
 Auf die Erweiterung kann von benutzerdefinierten Bindungen verwiesen werden, um UDP als Transport zu nutzen.  
  
```  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
  
```  
  
### Bindungsabschnitt  
 Der Abschnitt `SampleProfileUdpBindingCollectionElement` ist ein `StandardBindingCollectionElement`, das die `SampleProfileUdpBinding` für das Konfigurationssystem verfügbar macht.Dem `SampleProfileUdpBindingConfigurationElement`, das sich von `StandardBindingElement` herleitet, wird der Großteil der Implementierung übertragen.Das `SampleProfileUdpBindingConfigurationElement` verfügt über Eigenschaften, die mit den Eigenschaften auf `SampleProfileUdpBinding` übereinstimmen, sowie über Funktionen für die Zuordnung von der `ConfigurationElement` \-Bindung.Schließlich wird die `OnApplyConfiguration`\-Methode in der `SampleProfileUdpBinding` überschrieben. Dies wird im folgenden Beispielcode veranschaulicht.  
  
```  
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,  
                    "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",  
                    typeof(SampleProfileUdpBinding).AssemblyQualifiedName,  
                    binding.GetType().AssemblyQualifiedName));  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
  
```  
  
 Um diesen Handler mit dem Konfigurationssystem zu registrieren, fügen Sie der relevanten Konfigurationsdatei den folgenden Abschnitt hinzu.  
  
```  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 Darauf kann dann vom serviceModel\-Konfigurationsabschnitt verwiesen werden.  
  
```  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## Der UDP\-Testdienst und der Client  
 Testcode für die Verwendung dieses Beispieltransports ist in den UdpTestService\- und UdpTestClient\-Verzeichnissen verfügbar.Der Dienstcode besteht aus zwei Tests: Ein Test richtet die Bindungen und Endpunkte über den Code ein und der andere über die Konfiguration.Beide Tests verwenden zwei Endpunkte.Ein Endpunkt verwendet die `SampleUdpProfileBinding` mit [\<reliableSession\>](http://msdn.microsoft.com/de-de/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b), die auf `true` festgelegt wird.Der andere Endpunkt verwendet eine benutzerdefinierte Bindung mit `UdpTransportBindingElement`.Diese Vorgehensweise entspricht der Verwendung von `SampleUdpProfileBinding` mit [\<reliableSession\>](http://msdn.microsoft.com/de-de/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b), die auf `false` festgelegt ist.Beide Tests erstellen einen Dienst, fügen einen Endpunkt für jede Bindung hinzu, öffnen den Dienst und warten anschließend darauf, dass der Benutzer die EINGABETASTE drückt, bevor der Dienst beendet wird.  
  
 Wenn Sie die Testanwendung für den Dienst starten, sollte folgende Ausgabe angezeigt werden:  
  
```  
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 Sie können dann die Testclientanwendung für die veröffentlichten Endpunkte ausführen.Die Clienttestanwendung erstellt für jeden Endpunkt einen Client und sendet fünf Nachrichten an jeden Endpunkt.Im Folgenden finden Sie die Ausgabe auf dem Client:  
  
```  
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 Im Folgenden finden Sie die vollständige Ausgabe auf dem Dienst:  
  
```  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 Um die Clientanwendung für Endpunkte auszuführen, die mithilfe einer Konfiguration veröffentlicht wurden, drücken Sie die EINGABETASTE im Dienst, und führen Sie den Testclient erneut aus.Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:  
  
```  
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 Durch das erneute Ausführen des Clients werden die gleichen Ergebnisse erzielt wie zuvor.  
  
 Um den Clientcode und die Konfiguration mithilfe von "Svcutil.exe" neu zu generieren, starten Sie die Dienstanwendung, und führen Sie dann "Svcutil.exe" wie folgt aus dem Stammverzeichnis des Beispiels aus:  
  
```  
svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 Beachten Sie, dass "Svcutil.exe" nicht die Bindungserweiterungskonfiguration für `SampleProfileUdpBinding` generiert. Sie müssen diese daher manuell hinzufügen.  
  
```  
<configuration>  
    <system.serviceModel>      
        …  
        <extensions>  
            <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
            <bindingExtensions>  
                <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
            </bindingExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Folgen Sie den unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen, um die Projektmappe zu erstellen.  
  
2.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend ausführen möchten, folgen Sie den unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
3.  Informationen finden Sie im vorhergehenden Abschnitt "Der UDP\-Testdienst und der Client".  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`  
  
## Siehe auch