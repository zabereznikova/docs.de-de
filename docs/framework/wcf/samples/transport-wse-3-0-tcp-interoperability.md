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
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="89efb-102">Transport: WSE 3.0-TCP-Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="89efb-102">Transport: WSE 3.0 TCP Interoperability</span></span>

<span data-ttu-id="89efb-103">Das WSE 3,0 TCP-Interoperabilitäts Transport-Beispiel veranschaulicht, wie eine TCP-Duplex Sitzung als benutzerdefinierter Windows Communication Foundation (WCF)-Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="89efb-103">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="89efb-104">Außerdem zeigt es, wie Sie die Erweiterbarkeit der Kanalschicht verwenden können, um über das Netzwerk auf vorhandene bereitgestellte Systeme zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="89efb-104">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="89efb-105">Die folgenden Schritte zeigen, wie dieser benutzerdefinierte WCF-Transport erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="89efb-105">The following steps show how to build this custom WCF transport:</span></span>  
  
1. <span data-ttu-id="89efb-106">Beginnen Sie mit einem TCP-Socket. Erstellen Sie Client- und Serverimplementierungen von <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, die Nachrichtenbegrenzungen mittels DIME Framing voneinander abgrenzen.</span><span class="sxs-lookup"><span data-stu-id="89efb-106">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2. <span data-ttu-id="89efb-107">Erstellen Sie eine Kanalfactory, die mit einem WSE-TCP-Dienst verbunden wird und begrenzte Nachrichten über die <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s sendet.</span><span class="sxs-lookup"><span data-stu-id="89efb-107">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3. <span data-ttu-id="89efb-108">Erstellen Sie einen Kanallistener zum Entgegennehmen eingehender TCP-Verbindungen, und generieren Sie entsprechende Kanäle.</span><span class="sxs-lookup"><span data-stu-id="89efb-108">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4. <span data-ttu-id="89efb-109">Stellen Sie sicher, dass alle netzwerkspezifischen Ausnahmen zu der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="89efb-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5. <span data-ttu-id="89efb-110">Fügen Sie ein Bindungselement hinzu, das den benutzerdefinierten Transport einem Kanalstapel hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="89efb-110">Add a binding element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="89efb-111">Weitere Informationen finden Sie unter [Hinzufügen eines Bindungs Elements].</span><span class="sxs-lookup"><span data-stu-id="89efb-111">For more information, see [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="89efb-112">Erstellen von IDuplexSessionChannel</span><span class="sxs-lookup"><span data-stu-id="89efb-112">Creating IDuplexSessionChannel</span></span>  

 <span data-ttu-id="89efb-113">Der erste Schritt beim Schreiben des WSE 3.0-TCP-Interoperabilitätstransports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IDuplexSessionChannel> auf einem <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="89efb-113">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="89efb-114">`WseTcpDuplexSessionChannel` wird von <xref:System.ServiceModel.Channels.ChannelBase> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="89efb-114">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="89efb-115">Die Logik zum Senden von Nachrichten besteht aus zwei Hauptteilen: (1) dem Codieren der Nachricht in Bytes und (2) dem Einrahmen und Senden dieser Bytes über das Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="89efb-115">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="89efb-116">Außerdem wird eine Sperre angewendet, sodass die Send()-Aufrufe die IduplexSessionChannel-Reihenfolgen-Garantie beibehalten und Aufrufe an den zugrunde liegenden Socket korrekt synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="89efb-116">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="89efb-117">`WseTcpDuplexSessionChannel` verwendet einen <xref:System.ServiceModel.Channels.MessageEncoder> zum Übersetzen eines <xref:System.ServiceModel.Channels.Message> in und aus Byte[].</span><span class="sxs-lookup"><span data-stu-id="89efb-117">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="89efb-118">Da es sich um einen Transport handelt, ist `WseTcpDuplexSessionChannel` auch dafür verantwortlich, dass die Remoteadresse angewendet wird, mit der der Kanal konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="89efb-118">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="89efb-119">`EncodeMessage` kapselt die Logik für diese Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="89efb-119">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="89efb-120">Wenn die <xref:System.ServiceModel.Channels.Message>-Instanz in Bytes codiert ist, muss sie über das Netzwerk gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="89efb-120">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="89efb-121">Dazu ist ein System zum Definieren von Nachrichtenbegrenzungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89efb-121">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="89efb-122">WSE 3,0 verwendet eine Version von [Dime](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) als Rahmen Protokoll.</span><span class="sxs-lookup"><span data-stu-id="89efb-122">WSE 3.0 uses a version of [DIME](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) as its framing protocol.</span></span> <span data-ttu-id="89efb-123">`WriteData` kapselt die Framinglogik zum Einschließen eines Byte[] in einen Satz von DIME-Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="89efb-123">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="89efb-124">Die Logik zum Empfangen von Nachrichten ist ähnlich.</span><span class="sxs-lookup"><span data-stu-id="89efb-124">The logic for receiving messages is similar.</span></span> <span data-ttu-id="89efb-125">Die Haupt Komplexität besteht darin, die Tatsache zu behandeln, dass ein Socketlesevorgang weniger Bytes zurückgeben kann, als angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="89efb-125">The main complexity is handling the fact that a socket read can return fewer bytes than were requested.</span></span> <span data-ttu-id="89efb-126">Zum Empfangen einer Nachricht liest `WseTcpDuplexSessionChannel` Bytes aus dem Netzwerk, decodiert das DIME-Framing und wandelt dann mithilfe von <xref:System.ServiceModel.Channels.MessageEncoder> das Byte[] in eine <xref:System.ServiceModel.Channels.Message> um.</span><span class="sxs-lookup"><span data-stu-id="89efb-126">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="89efb-127">Der Basis-`WseTcpDuplexSessionChannel` geht davon aus, dass er einen verbundenen Socket empfängt.</span><span class="sxs-lookup"><span data-stu-id="89efb-127">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="89efb-128">Die Basisklasse behandelt das Herunterfahren des Sockets.</span><span class="sxs-lookup"><span data-stu-id="89efb-128">The base class handles socket shutdown.</span></span> <span data-ttu-id="89efb-129">Es gibt drei Stellen, die mit einer Schließung des Sockets in Verbindung stehen:</span><span class="sxs-lookup"><span data-stu-id="89efb-129">There are three places that interface with socket closure:</span></span>  
  
- <span data-ttu-id="89efb-130">OnAbort -- schließt den Socket nicht ordnungsgemäß ("hartes" Schließen).</span><span class="sxs-lookup"><span data-stu-id="89efb-130">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
- <span data-ttu-id="89efb-131">On[Begin]Close -- schließt den Socket ordnungsgemäß ("weiches" Schließen).</span><span class="sxs-lookup"><span data-stu-id="89efb-131">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
- <span data-ttu-id="89efb-132">Sitzung. CloseOutputSession: Beenden Sie den ausgehenden Datenstrom (halbnah).</span><span class="sxs-lookup"><span data-stu-id="89efb-132">session.CloseOutputSession -- shut down the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="89efb-133">Kanalfactory</span><span class="sxs-lookup"><span data-stu-id="89efb-133">Channel Factory</span></span>  

 <span data-ttu-id="89efb-134">Der nächste Schritt beim Schreiben des TCP-Transports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle.</span><span class="sxs-lookup"><span data-stu-id="89efb-134">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
- <span data-ttu-id="89efb-135">`WseTcpChannelFactory`wird von abgeleitet <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="89efb-135">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="89efb-136">Das ist eine Factory, die `OnCreateChannel` überschreibt, um Clientkanäle zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="89efb-136">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- <span data-ttu-id="89efb-137">`ClientWseTcpDuplexSessionChannel` Fügt der Basis Logik hinzu `WseTcpDuplexSessionChannel` , um zum Zeitpunkt eine Verbindung mit einem TCP-Server herzustellen `channel.Open` .</span><span class="sxs-lookup"><span data-stu-id="89efb-137">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="89efb-138">Zuerst wird der Hostname zu einer IP-Adresse aufgelöst, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-138">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- <span data-ttu-id="89efb-139">Dann wird der Hostname in einer Schleife mit der ersten verfügbaren IP-Adresse verbunden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-139">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- <span data-ttu-id="89efb-140">Als Teil des Kanalvertrags werden alle domänenspezifischen Ausnahmen eingebunden (wie `SocketException` in <xref:System.ServiceModel.CommunicationException>).</span><span class="sxs-lookup"><span data-stu-id="89efb-140">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="89efb-141">Kanallistener</span><span class="sxs-lookup"><span data-stu-id="89efb-141">Channel Listener</span></span>  

 <span data-ttu-id="89efb-142">Im nächsten Schritt wird eine Implementierung von <xref:System.ServiceModel.Channels.IChannelListener> zum Entgegennehmen von Serverkanälen erstellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-142">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
- <span data-ttu-id="89efb-143">`WseTcpChannelListener`wird von abgeleitet und überschreibt <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> on [begin] Open und on [begin] Close, um die Lebensdauer des Abhör Sockets zu steuern.</span><span class="sxs-lookup"><span data-stu-id="89efb-143">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="89efb-144">In OnOpen wird ein Socket zum Lauschen an IP_ANY erstellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-144">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="89efb-145">Weiter fortgeschrittene Implementierungen können einen zweiten Socket erstellen, um auch an IPv6 zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="89efb-145">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="89efb-146">Sie können außerdem zulassen, dass die IP-Adresse im Hostnamen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="89efb-146">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="89efb-147">Wenn ein neuer Socket entgegengenommen ist, wird ein Serverkanal mit diesem Socket initialisiert.</span><span class="sxs-lookup"><span data-stu-id="89efb-147">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="89efb-148">Alle Ein- und Ausgaben sind bereits in der Basisklasse implementiert, daher dient dieser Kanal zum Initialisieren des Sockets.</span><span class="sxs-lookup"><span data-stu-id="89efb-148">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="89efb-149">Hinzufügen eines Bindungselements</span><span class="sxs-lookup"><span data-stu-id="89efb-149">Adding a Binding Element</span></span>  

 <span data-ttu-id="89efb-150">Nachdem nun die Factorys und Kanäle erstellt sind, müssen Sie der ServiceModel-Laufzeit über eine Bindung verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="89efb-150">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="89efb-151">Eine Bindung ist eine Auflistung von Bindungselementen, die den mit einer Dienstadresse verknüpften Kommunikationsstapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-151">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="89efb-152">Jedes Element im Stapel wird durch ein Bindungselement dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-152">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="89efb-153">Im Beispiel ist das Bindungselement `WseTcpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="89efb-153">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="89efb-154">Es unterstützt <xref:System.ServiceModel.Channels.IDuplexSessionChannel> und überschreibt die folgenden Methoden, um die mit unserer Bindung verknüpften Factorys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89efb-154">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="89efb-155">Es enthält auch Members zum Klonen des `BindingElement` und Zurückgeben unseres Schemas (wse.tcp).</span><span class="sxs-lookup"><span data-stu-id="89efb-155">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="89efb-156">Die WSE-TCP-Testkonsole</span><span class="sxs-lookup"><span data-stu-id="89efb-156">The WSE TCP Test Console</span></span>  

 <span data-ttu-id="89efb-157">Testcode zum Verwenden dieses Beispieltransports ist in TestCode.cs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89efb-157">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="89efb-158">Die folgenden Anweisungen zeigen, wie das WSE-`TcpSyncStockService`-Beispiel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="89efb-158">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="89efb-159">Der Testcode erstellt eine benutzerdefinierte Bindung, die MTOM als Codierung und `WseTcpTransport` als Transport verwendet.</span><span class="sxs-lookup"><span data-stu-id="89efb-159">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="89efb-160">Außerdem richtet er die AddressingVersion so ein, dass sie mit WSE 3.0 kompatibel ist, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89efb-160">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="89efb-161">Er besteht aus zwei Tests: Der erste Test richtet einen typisierten Client mithilfe von aus WSE 3.0 WSDL generiertem Code ein.</span><span class="sxs-lookup"><span data-stu-id="89efb-161">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="89efb-162">Im zweiten Test wird WCF sowohl als Client als auch als Server verwendet, indem Nachrichten direkt oberhalb der Channel-APIs gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="89efb-162">The second test uses WCF as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="89efb-163">Beim Ausführen des Beispiels sollte die Ausgabe wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="89efb-163">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="89efb-164">Client:</span><span class="sxs-lookup"><span data-stu-id="89efb-164">Client:</span></span>  
  
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
  
 <span data-ttu-id="89efb-165">Server: </span><span class="sxs-lookup"><span data-stu-id="89efb-165">Server:</span></span>  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="89efb-166">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="89efb-166">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="89efb-167">Um dieses Beispiel ausführen zu können, müssen Sie über die [Web Services-Erweiterungen (WSE) 3,0 für Microsoft .net](https://www.microsoft.com/download/details.aspx?id=14089) und das WSE- `TcpSyncStockService` Beispiel verfügen.</span><span class="sxs-lookup"><span data-stu-id="89efb-167">To run this sample, you must have [Web Services Enhancements (WSE) 3.0 for Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) and the WSE `TcpSyncStockService` sample installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89efb-168">Da WSE 3,0 nicht unter Windows Server 2008 unterstützt wird, können Sie das Beispiel nicht `TcpSyncStockService` auf diesem Betriebssystem installieren oder ausführen.</span><span class="sxs-lookup"><span data-stu-id="89efb-168">Because WSE 3.0 is not supported on Windows Server 2008, you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1. <span data-ttu-id="89efb-169">Führen Sie nach der Installation des `TcpSyncStockService`-Beispiels folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="89efb-169">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1. <span data-ttu-id="89efb-170">Öffnen Sie `TcpSyncStockService` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89efb-170">Open the `TcpSyncStockService` in Visual Studio.</span></span> <span data-ttu-id="89efb-171">(Das TcpSyncStockService-Beispiel wird mit WSE 3,0 installiert.</span><span class="sxs-lookup"><span data-stu-id="89efb-171">(The TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="89efb-172">Es ist nicht Bestandteil dieses Beispielcodes.)</span><span class="sxs-lookup"><span data-stu-id="89efb-172">It is not part of this sample's code.)</span></span>  
  
    2. <span data-ttu-id="89efb-173">Legen Sie das StockService-Projekt als Startprojekt fest.</span><span class="sxs-lookup"><span data-stu-id="89efb-173">Set the StockService project as the start-up project.</span></span>  
  
    3. <span data-ttu-id="89efb-174">Öffnen Sie StockService.cs im StockService-Projekt, und kommentieren Sie das [Policy]-Attribut in der `StockService`-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="89efb-174">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="89efb-175">Dadurch werden die Sicherheitsfunktionen im Beispiel deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="89efb-175">This disables security from the sample.</span></span> <span data-ttu-id="89efb-176">Obwohl WCF mit sicheren WSE 3,0-Endpunkten interagieren kann, ist die Sicherheit deaktiviert, damit dieses Beispiel auf den benutzerdefinierten TCP-Transport fokussiert ist.</span><span class="sxs-lookup"><span data-stu-id="89efb-176">While WCF can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4. <span data-ttu-id="89efb-177">Drücken Sie F5, um `TcpSyncStockService` zu starten.</span><span class="sxs-lookup"><span data-stu-id="89efb-177">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="89efb-178">Der Dienst wird in einem neuen Konsolenfenster gestartet.</span><span class="sxs-lookup"><span data-stu-id="89efb-178">The service starts in a new console window.</span></span>  
  
    5. <span data-ttu-id="89efb-179">Öffnen Sie dieses TCP-Transportbeispiel in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89efb-179">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6. <span data-ttu-id="89efb-180">Aktualisieren Sie die Variable "hostname" in TestCode.cs so, dass sie mit dem Namen des Computers übereinstimmt, auf dem `TcpSyncStockService` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89efb-180">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7. <span data-ttu-id="89efb-181">Drücken Sie F5, um das TCP-Transportbeispiel zu starten.</span><span class="sxs-lookup"><span data-stu-id="89efb-181">Press F5 to start the TCP transport sample.</span></span>  
  
    8. <span data-ttu-id="89efb-182">Der TCP-Transporttest-Client wird in einem neuen Konsolenfenster gestartet.</span><span class="sxs-lookup"><span data-stu-id="89efb-182">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="89efb-183">Der Client fordert beim Dienst Aktienkurse an und zeigt die Ergebnisse dann in seinem Konsolenfenster an.</span><span class="sxs-lookup"><span data-stu-id="89efb-183">The client requests stock quotes from the service and then displays the results in its console window.</span></span>
