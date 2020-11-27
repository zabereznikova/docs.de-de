---
title: 'Transport: WSE 3.0-TCP-Interoperabilität'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: c268043a9d5c3f6a48b7b66dc807e4e30f029f61
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292505"
---
# <a name="transport-wse-30-tcp-interoperability"></a>Transport: WSE 3.0-TCP-Interoperabilität

Das WSE 3,0 TCP-Interoperabilitäts Transport-Beispiel veranschaulicht, wie eine TCP-Duplex Sitzung als benutzerdefinierter Windows Communication Foundation (WCF)-Transport implementiert wird. Außerdem zeigt es, wie Sie die Erweiterbarkeit der Kanalschicht verwenden können, um über das Netzwerk auf vorhandene bereitgestellte Systeme zuzugreifen. Die folgenden Schritte zeigen, wie dieser benutzerdefinierte WCF-Transport erstellt wird:  
  
1. Beginnen Sie mit einem TCP-Socket. Erstellen Sie Client- und Serverimplementierungen von <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, die Nachrichtenbegrenzungen mittels DIME Framing voneinander abgrenzen.  
  
2. Erstellen Sie eine Kanalfactory, die mit einem WSE-TCP-Dienst verbunden wird und begrenzte Nachrichten über die <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s sendet.  
  
3. Erstellen Sie einen Kanallistener zum Entgegennehmen eingehender TCP-Verbindungen, und generieren Sie entsprechende Kanäle.  
  
4. Stellen Sie sicher, dass alle netzwerkspezifischen Ausnahmen zu der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden.  
  
5. Fügen Sie ein Bindungselement hinzu, das den benutzerdefinierten Transport einem Kanalstapel hinzufügt. Weitere Informationen finden Sie unter [Hinzufügen eines Bindungs Elements].  
  
## <a name="creating-iduplexsessionchannel"></a>Erstellen von IDuplexSessionChannel  

 Der erste Schritt beim Schreiben des WSE 3.0-TCP-Interoperabilitätstransports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IDuplexSessionChannel> auf einem <xref:System.Net.Sockets.Socket>. `WseTcpDuplexSessionChannel` wird von <xref:System.ServiceModel.Channels.ChannelBase> abgeleitet. Die Logik zum Senden von Nachrichten besteht aus zwei Hauptteilen: (1) dem Codieren der Nachricht in Bytes und (2) dem Einrahmen und Senden dieser Bytes über das Netzwerk.  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 Außerdem wird eine Sperre angewendet, sodass die Send()-Aufrufe die IduplexSessionChannel-Reihenfolgen-Garantie beibehalten und Aufrufe an den zugrunde liegenden Socket korrekt synchronisiert werden.  
  
 `WseTcpDuplexSessionChannel` verwendet einen <xref:System.ServiceModel.Channels.MessageEncoder> zum Übersetzen eines <xref:System.ServiceModel.Channels.Message> in und aus Byte[]. Da es sich um einen Transport handelt, ist `WseTcpDuplexSessionChannel` auch dafür verantwortlich, dass die Remoteadresse angewendet wird, mit der der Kanal konfiguriert wurde. `EncodeMessage` kapselt die Logik für diese Konvertierung.  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 Wenn die <xref:System.ServiceModel.Channels.Message>-Instanz in Bytes codiert ist, muss sie über das Netzwerk gesendet werden. Dazu ist ein System zum Definieren von Nachrichtenbegrenzungen erforderlich. WSE 3,0 verwendet eine Version von [Dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) als Rahmen Protokoll. `WriteData` kapselt die Framinglogik zum Einschließen eines Byte[] in einen Satz von DIME-Datensätzen.  
  
 Die Logik zum Empfangen von Nachrichten ist ähnlich. Die Haupt Komplexität besteht darin, die Tatsache zu behandeln, dass ein Socketlesevorgang weniger Bytes zurückgeben kann, als angefordert wurden. Zum Empfangen einer Nachricht liest `WseTcpDuplexSessionChannel` Bytes aus dem Netzwerk, decodiert das DIME-Framing und wandelt dann mithilfe von <xref:System.ServiceModel.Channels.MessageEncoder> das Byte[] in eine <xref:System.ServiceModel.Channels.Message> um.  
  
 Der Basis-`WseTcpDuplexSessionChannel` geht davon aus, dass er einen verbundenen Socket empfängt. Die Basisklasse behandelt das Herunterfahren des Sockets. Es gibt drei Stellen, die mit einer Schließung des Sockets in Verbindung stehen:  
  
- OnAbort -- schließt den Socket nicht ordnungsgemäß ("hartes" Schließen).  
  
- On[Begin]Close -- schließt den Socket ordnungsgemäß ("weiches" Schließen).  
  
- Sitzung. CloseOutputSession: Beenden Sie den ausgehenden Datenstrom (halbnah).  
  
## <a name="channel-factory"></a>Kanalfactory  

 Der nächste Schritt beim Schreiben des TCP-Transports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle.  
  
- `WseTcpChannelFactory`wird von abgeleitet <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> . Das ist eine Factory, die `OnCreateChannel` überschreibt, um Clientkanäle zu erzeugen.  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- `ClientWseTcpDuplexSessionChannel` Fügt der Basis Logik hinzu `WseTcpDuplexSessionChannel` , um zum Zeitpunkt eine Verbindung mit einem TCP-Server herzustellen `channel.Open` . Zuerst wird der Hostname zu einer IP-Adresse aufgelöst, wie im folgenden Code dargestellt.  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- Dann wird der Hostname in einer Schleife mit der ersten verfügbaren IP-Adresse verbunden, wie im folgenden Code dargestellt.  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- Als Teil des Kanalvertrags werden alle domänenspezifischen Ausnahmen eingebunden (wie `SocketException` in <xref:System.ServiceModel.CommunicationException>).  
  
## <a name="channel-listener"></a>Kanallistener  

 Im nächsten Schritt wird eine Implementierung von <xref:System.ServiceModel.Channels.IChannelListener> zum Entgegennehmen von Serverkanälen erstellt.  
  
- `WseTcpChannelListener`wird von abgeleitet und überschreibt <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> on [begin] Open und on [begin] Close, um die Lebensdauer des Abhör Sockets zu steuern. In OnOpen wird ein Socket zum Lauschen an IP_ANY erstellt. Weiter fortgeschrittene Implementierungen können einen zweiten Socket erstellen, um auch an IPv6 zu lauschen. Sie können außerdem zulassen, dass die IP-Adresse im Hostnamen angegeben wird.  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 Wenn ein neuer Socket entgegengenommen ist, wird ein Serverkanal mit diesem Socket initialisiert. Alle Ein- und Ausgaben sind bereits in der Basisklasse implementiert, daher dient dieser Kanal zum Initialisieren des Sockets.  
  
## <a name="adding-a-binding-element"></a>Hinzufügen eines Bindungselements  

 Nachdem nun die Factorys und Kanäle erstellt sind, müssen Sie der ServiceModel-Laufzeit über eine Bindung verfügbar gemacht werden. Eine Bindung ist eine Auflistung von Bindungselementen, die den mit einer Dienstadresse verknüpften Kommunikationsstapel darstellt. Jedes Element im Stapel wird durch ein Bindungselement dargestellt.  
  
 Im Beispiel ist das Bindungselement `WseTcpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird. Es unterstützt <xref:System.ServiceModel.Channels.IDuplexSessionChannel> und überschreibt die folgenden Methoden, um die mit unserer Bindung verknüpften Factorys zu erstellen.  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 Es enthält auch Members zum Klonen des `BindingElement` und Zurückgeben unseres Schemas (wse.tcp).  
  
## <a name="the-wse-tcp-test-console"></a>Die WSE-TCP-Testkonsole  

 Testcode zum Verwenden dieses Beispieltransports ist in TestCode.cs verfügbar. Die folgenden Anweisungen zeigen, wie das WSE-`TcpSyncStockService`-Beispiel erstellt wird.  
  
 Der Testcode erstellt eine benutzerdefinierte Bindung, die MTOM als Codierung und `WseTcpTransport` als Transport verwendet. Außerdem richtet er die AddressingVersion so ein, dass sie mit WSE 3.0 kompatibel ist, wie im folgenden Code dargestellt.  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 Er besteht aus zwei Tests: Der erste Test richtet einen typisierten Client mithilfe von aus WSE 3.0 WSDL generiertem Code ein. Im zweiten Test wird WCF sowohl als Client als auch als Server verwendet, indem Nachrichten direkt oberhalb der Channel-APIs gesendet werden.  
  
 Beim Ausführen des Beispiels sollte die Ausgabe wie folgt aussehen.  
  
 Client:  
  
```console  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 Server:   
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels  
  
1. Um dieses Beispiel ausführen zu können, müssen Sie über die [Web Services-Erweiterungen (WSE) 3,0 für Microsoft .net](https://www.microsoft.com/download/details.aspx?id=14089) und das WSE- `TcpSyncStockService` Beispiel verfügen.
  
> [!NOTE]
> Da WSE 3,0 nicht unter Windows Server 2008 unterstützt wird, können Sie das Beispiel nicht `TcpSyncStockService` auf diesem Betriebssystem installieren oder ausführen.  
  
1. Führen Sie nach der Installation des `TcpSyncStockService`-Beispiels folgende Schritte aus:  
  
    1. Öffnen Sie `TcpSyncStockService` in Visual Studio. (Das TcpSyncStockService-Beispiel wird mit WSE 3,0 installiert. Es ist nicht Bestandteil dieses Beispielcodes.)  
  
    2. Legen Sie das StockService-Projekt als Startprojekt fest.  
  
    3. Öffnen Sie StockService.cs im StockService-Projekt, und kommentieren Sie das [Policy]-Attribut in der `StockService`-Klasse aus. Dadurch werden die Sicherheitsfunktionen im Beispiel deaktiviert. Obwohl WCF mit sicheren WSE 3,0-Endpunkten interagieren kann, ist die Sicherheit deaktiviert, damit dieses Beispiel auf den benutzerdefinierten TCP-Transport fokussiert ist.  
  
    4. Drücken Sie F5, um `TcpSyncStockService` zu starten. Der Dienst wird in einem neuen Konsolenfenster gestartet.  
  
    5. Öffnen Sie dieses TCP-Transportbeispiel in Visual Studio.  
  
    6. Aktualisieren Sie die Variable "hostname" in TestCode.cs so, dass sie mit dem Namen des Computers übereinstimmt, auf dem `TcpSyncStockService` ausgeführt wird.  
  
    7. Drücken Sie F5, um das TCP-Transportbeispiel zu starten.  
  
    8. Der TCP-Transporttest-Client wird in einem neuen Konsolenfenster gestartet. Der Client fordert beim Dienst Aktienkurse an und zeigt die Ergebnisse dann in seinem Konsolenfenster an.
