---
title: 'Transport: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: 4ae4bf22f452035d10ecba6bcf93bf580ab7f5f8
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422161"
---
# <a name="transport-udp"></a><span data-ttu-id="c2018-102">Transport: UDP</span><span class="sxs-lookup"><span data-stu-id="c2018-102">Transport: UDP</span></span>
<span data-ttu-id="c2018-103">Beispiel für den UDP-Transport veranschaulicht, wie UDP-Unicast und -Multicast als einen benutzerdefinierten Windows Communication Foundation (WCF)-Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-103">The UDP Transport sample demonstrates how to implement UDP unicast and multicast as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="c2018-104">Im Beispiel wird die empfohlene Vorgehensweise zum Erstellen eines benutzerdefinierten Transports in WCF anhand des kanalframeworks und WCF-best Practices beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2018-104">The sample describes the recommended procedure for creating a custom transport in WCF, by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="c2018-105">Die Schritte zum Erstellen eines benutzerdefinierten Transports lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2018-105">The steps to create a custom transport are as follows:</span></span>  
  
1. <span data-ttu-id="c2018-106">Entscheiden Sie, welche des Kanals [Nachrichtenaustauschmuster](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel oder IReplyChannel) Ihre ChannelFactory und vom ChannelListener unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c2018-106">Decide which of the channel [Message Exchange Patterns](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel, or IReplyChannel) your ChannelFactory and ChannelListener will support.</span></span> <span data-ttu-id="c2018-107">Dann entscheiden Sie sich, ob Sie die sitzungsbasierten Variationen dieser Schnittstellen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2018-107">Then decide whether you will support the sessionful variations of these interfaces.</span></span>  
  
2. <span data-ttu-id="c2018-108">Erstellen Sie eine Kanalfactory und einen Kanallistener, die Ihr Nachrichtenaustauschmuster unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2018-108">Create a channel factory and listener that support your Message Exchange Pattern.</span></span>  
  
3. <span data-ttu-id="c2018-109">Stellen Sie sicher, dass alle netzwerkspezifischen Ausnahmen zu der entsprechenden abgeleiteten Klasse von <xref:System.ServiceModel.CommunicationException> normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
4. <span data-ttu-id="c2018-110">Hinzufügen einer [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element, das den benutzerdefinierten Transport einem Kanalstapel hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="c2018-110">Add a [\<binding>](../../../../docs/framework/misc/binding.md) element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="c2018-111">Weitere Informationen finden Sie unter [Hinzufügen eines Bindungselements](#AddingABindingElement).</span><span class="sxs-lookup"><span data-stu-id="c2018-111">For more information, see [Adding a Binding Element](#AddingABindingElement).</span></span>  
  
5. <span data-ttu-id="c2018-112">Fügen Sie einen Bindungselementerweiterungs-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c2018-112">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
6. <span data-ttu-id="c2018-113">Fügen Sie Metadatenerweiterungen hinzu, um anderen Endpunkten Funktionen mitzuteilen.</span><span class="sxs-lookup"><span data-stu-id="c2018-113">Add metadata extensions to communicate capabilities to other endpoints.</span></span>  
  
7. <span data-ttu-id="c2018-114">Fügen Sie eine Bindung hinzu, die einen Stapel mit Bindungselementen entsprechend einem genau definierten Profil vorkonfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c2018-114">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="c2018-115">Weitere Informationen finden Sie unter [Hinzufügen einer Standardbindung](#AddingAStandardBinding).</span><span class="sxs-lookup"><span data-stu-id="c2018-115">For more information, see [Adding a Standard Binding](#AddingAStandardBinding).</span></span>  
  
8. <span data-ttu-id="c2018-116">Fügen Sie einen Bindungsabschnitt und ein Bindungskonfigurationselement hinzu, um die Bindung für das Konfigurationssystem verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c2018-116">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="c2018-117">Weitere Informationen finden Sie unter [Hinzufügen von Konfigurationsunterstützung](#AddingConfigurationSupport).</span><span class="sxs-lookup"><span data-stu-id="c2018-117">For more information, see [Adding Configuration Support](#AddingConfigurationSupport).</span></span>  
  
<a name="MessageExchangePatterns"></a>   
## <a name="message-exchange-patterns"></a><span data-ttu-id="c2018-118">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="c2018-118">Message Exchange Patterns</span></span>  
 <span data-ttu-id="c2018-119">Der erste Schritt beim Schreiben eines benutzerdefinierten Transports besteht darin zu entscheiden, welche Nachrichtenaustauschmuster für den Transport erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c2018-119">The first step in writing a custom transport is to decide which Message Exchange Patterns (MEPs) are required for the transport.</span></span> <span data-ttu-id="c2018-120">Es stehen drei Nachrichtenaustauschmuster zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="c2018-120">There are three MEPs to choose from:</span></span>  
  
- <span data-ttu-id="c2018-121">Datagramm (IInputChannel/IOutputChannel)</span><span class="sxs-lookup"><span data-stu-id="c2018-121">Datagram (IInputChannel/IOutputChannel)</span></span>  
  
     <span data-ttu-id="c2018-122">Bei Verwendung eines Datagramm-Nachrichtenaustauschmusters sendet ein Client eine Nachricht mit einem "fire and forget"-Austausch.</span><span class="sxs-lookup"><span data-stu-id="c2018-122">When using a datagram MEP, a client sends a message using a "fire and forget" exchange.</span></span> <span data-ttu-id="c2018-123">Ein "fire and forget"-Austausch erfordert eine Out-of-Band-Bestätigung für die erfolgreiche Zustellung.</span><span class="sxs-lookup"><span data-stu-id="c2018-123">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="c2018-124">Die Nachricht könnte unterwegs verloren gehen und den Dienst nicht erreichen.</span><span class="sxs-lookup"><span data-stu-id="c2018-124">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="c2018-125">Wenn der Sendevorgang auf der Clientseite erfolgreich abgeschlossen wird, stellt dies keine Garantie dar, dass der Remoteendpunkt die Nachricht erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="c2018-125">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="c2018-126">Das Datagramm ist ein wesentlicher Baustein für den Nachrichtenaustausch, da Sie eigene Protokolle damit erstellen können, einschließlich zuverlässiger Protokolle und sicherer Protokolle.</span><span class="sxs-lookup"><span data-stu-id="c2018-126">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="c2018-127">Clientdatagrammkanäle implementieren die <xref:System.ServiceModel.Channels.IOutputChannel>-Schnittstelle, und Dienstdatagrammkanäle implementieren die <xref:System.ServiceModel.Channels.IInputChannel>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2018-127">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
- <span data-ttu-id="c2018-128">Anforderung-Antwort (IRequestChannel/IReplyChannel)</span><span class="sxs-lookup"><span data-stu-id="c2018-128">Request-Response (IRequestChannel/IReplyChannel)</span></span>  
  
     <span data-ttu-id="c2018-129">In diesem Nachrichtenaustauschmuster wird eine Nachricht gesendet, und eine Antwort wird empfangen.</span><span class="sxs-lookup"><span data-stu-id="c2018-129">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="c2018-130">Das Muster besteht aus Anforderungs-Antwort-Paaren.</span><span class="sxs-lookup"><span data-stu-id="c2018-130">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="c2018-131">Beispiele für Anforderungs-Antwort-Aufrufe sind Remoteprozeduraufrufe (RPC) und Browser-GET-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c2018-131">Examples of request-response calls are remote procedure calls (RPC) and browser GETs.</span></span> <span data-ttu-id="c2018-132">Dieses Muster wird auch als Halbduplex bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c2018-132">This pattern is also known as Half-Duplex.</span></span> <span data-ttu-id="c2018-133">In diesem Nachrichtenaustauschmuster implementieren Clientkanäle <xref:System.ServiceModel.Channels.IRequestChannel>, und Dienstkanäle implementieren <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="c2018-133">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
- <span data-ttu-id="c2018-134">Duplex (IDuplexChannel)</span><span class="sxs-lookup"><span data-stu-id="c2018-134">Duplex (IDuplexChannel)</span></span>  
  
     <span data-ttu-id="c2018-135">Das Duplex-Nachrichtenaustauschmuster ermöglicht, dass eine willkürliche Anzahl von Nachrichten von einem Client gesendet und in beliebiger Reihenfolge empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-135">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="c2018-136">Das Duplex-Nachrichtenaustauschmuster ist mit einem Telefongespräch vergleichbar, bei dem jedes gesprochene Wort einer Nachricht entspricht.</span><span class="sxs-lookup"><span data-stu-id="c2018-136">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="c2018-137">Da beide Teilnehmer in diesem Nachrichtenaustauschmuster senden und empfangen können, ist die vom Client und von den Dienstkanälen implementierte Schnittstelle <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="c2018-137">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="c2018-138">Jedes dieser Nachrichtenaustauschmuster kann außerdem Sitzungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2018-138">Each of these MEPs can also support sessions.</span></span> <span data-ttu-id="c2018-139">Die neue Funktion von sitzungsfähigen Kanälen besteht darin, dass alle in einem Kanal gesendeten und empfangenen Nachrichten korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-139">The added functionality provided by a session-aware channel is that it correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="c2018-140">Das Anforderungs-Antwort-Muster ist eine eigenständige, aus zwei Nachrichten bestehende Sitzung, da die Anforderung und die Antwort korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-140">The Request-Response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="c2018-141">Demgegenüber impliziert das Anforderungs-Antwort-Muster, das Sitzungen unterstützt, dass alle Anforderungs-/Antwort-Paare in diesem Kanal miteinander korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-141">In contrast, the Request-Response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="c2018-142">Dadurch ergeben sich sechs Nachrichtenaustauschmuster zur Auswahl: Datagramm, Anforderung-Antwort, Duplex, Datagramm mit Sitzungen, Anforderung-Antwort mit Sitzungen und Duplex mit Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="c2018-142">This gives you a total of six MEPs—Datagram, Request-Response, Duplex, Datagram with sessions, Request-Response with sessions, and Duplex with sessions—to choose from.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2018-143">Für den UDP-Transport wird nur das Nachrichtenaustauschmuster Datagramm unterstützt, da UDP grundsätzlich ein "fire and forget"-Protokoll ist.</span><span class="sxs-lookup"><span data-stu-id="c2018-143">For the UDP transport, the only MEP that is supported is Datagram, because UDP is inherently a "fire and forget" protocol.</span></span>  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a><span data-ttu-id="c2018-144">Der ICommunicationObject- und der WCF-Objektlebenszyklus</span><span class="sxs-lookup"><span data-stu-id="c2018-144">The ICommunicationObject and the WCF object lifecycle</span></span>  
 <span data-ttu-id="c2018-145">WCF bietet einen allgemeinen Zustandsautomaten, der verwendet wird, zum Verwalten des legenszyklus von Objekten wie <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, und <xref:System.ServiceModel.Channels.IChannelListener> , die für die Kommunikation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-145">WCF has a common state machine that is used for managing the lifecycle of objects like <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, and <xref:System.ServiceModel.Channels.IChannelListener> that are used for communication.</span></span> <span data-ttu-id="c2018-146">Es gibt fünf Zustände, in denen diese Kommunikationsobjekte vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="c2018-146">There are five states in which these communication objects can exist.</span></span> <span data-ttu-id="c2018-147">Die Zustände werden durch die <xref:System.ServiceModel.CommunicationState>-Enumeration dargestellt und lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2018-147">These states are represented by the <xref:System.ServiceModel.CommunicationState> enumeration, and are as follows:</span></span>  
  
- <span data-ttu-id="c2018-148">Erstellt: Dies ist der Zustand einer <xref:System.ServiceModel.ICommunicationObject> Wenn es zuerst instanziiert.</span><span class="sxs-lookup"><span data-stu-id="c2018-148">Created: This is the state of a <xref:System.ServiceModel.ICommunicationObject> when it is first instantiated.</span></span> <span data-ttu-id="c2018-149">In diesem Zustand tritt keine Eingabe/Ausgabe (E/A) auf.</span><span class="sxs-lookup"><span data-stu-id="c2018-149">No input/output (I/O) occurs in this state.</span></span>  
  
- <span data-ttu-id="c2018-150">Opening: Objekt geht zu diesem Zustand über, wenn <xref:System.ServiceModel.ICommunicationObject.Open%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-150">Opening: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="c2018-151">An diesem Punkt werden Eigenschaften unveränderlich gemacht, und Eingabe/Ausgabe kann beginnen.</span><span class="sxs-lookup"><span data-stu-id="c2018-151">At this point properties are made immutable, and input/output can begin.</span></span> <span data-ttu-id="c2018-152">Dieser Übergang ist nur vom Created-Zustand aus gültig.</span><span class="sxs-lookup"><span data-stu-id="c2018-152">This transition is valid only from the Created state.</span></span>  
  
- <span data-ttu-id="c2018-153">Geöffnet: Objekt geht zu diesem Zustand, wenn der Öffnungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c2018-153">Opened: Objects transition to this state when the open process completes.</span></span> <span data-ttu-id="c2018-154">Dieser Übergang ist nur vom Opening-Zustand aus gültig.</span><span class="sxs-lookup"><span data-stu-id="c2018-154">This transition is valid only from the Opening state.</span></span> <span data-ttu-id="c2018-155">An diesem Punkt ist das Objekt für die Übertragung voll verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c2018-155">At this point, the object is fully usable for transfer.</span></span>  
  
- <span data-ttu-id="c2018-156">Schließen: Objekt geht zu diesem Zustand über, wenn <xref:System.ServiceModel.ICommunicationObject.Close%2A> für ein ordnungsgemäßes Herunterfahren aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-156">Closing: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called for a graceful shutdown.</span></span> <span data-ttu-id="c2018-157">Dieser Übergang ist nur vom Opened-Zustand aus gültig.</span><span class="sxs-lookup"><span data-stu-id="c2018-157">This transition is valid only from the Opened state.</span></span>  
  
- <span data-ttu-id="c2018-158">Geschlossen: Im Closed werden Zustandsobjekte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-158">Closed: In the Closed state objects are no longer usable.</span></span> <span data-ttu-id="c2018-159">Im Allgemeinen steht der größte Teil der Konfiguration noch zur Ansicht bereit, es kann aber keine Kommunikation auftreten.</span><span class="sxs-lookup"><span data-stu-id="c2018-159">In general, most configuration is still accessible for inspection, but no communication can occur.</span></span> <span data-ttu-id="c2018-160">Dieser Zustand ist mit "Verworfen" vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="c2018-160">This state is equivalent to being disposed.</span></span>  
  
- <span data-ttu-id="c2018-161">Fehler: In den Faulted-Zustand sind die Objekte zugegriffen werden kann, um die Überprüfung jedoch nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-161">Faulted: In the Faulted state, objects are accessible to inspection but no longer usable.</span></span> <span data-ttu-id="c2018-162">Wenn ein nicht behebbarer Fehler auftritt, geht das Objekt in diesen Zustand über.</span><span class="sxs-lookup"><span data-stu-id="c2018-162">When a non-recoverable error occurs, the object transitions into this state.</span></span> <span data-ttu-id="c2018-163">Der einzige gültige Übergang von diesem Status wird in der `Closed` Zustand.</span><span class="sxs-lookup"><span data-stu-id="c2018-163">The only valid transition from this state is into the `Closed` state.</span></span>  
  
 <span data-ttu-id="c2018-164">Es gibt Ereignisse, die für jeden Zustandsübergang ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-164">There are events that fire for each state transition.</span></span> <span data-ttu-id="c2018-165">Die <xref:System.ServiceModel.ICommunicationObject.Abort%2A>-Methode kann jederzeit aufgerufen werden und sorgt dafür, dass das Objekt sofort vom aktuellen Zustand in den Closed-Zustand übergeht.</span><span class="sxs-lookup"><span data-stu-id="c2018-165">The <xref:System.ServiceModel.ICommunicationObject.Abort%2A> method can be called at any time, and causes the object to transition immediately from its current state into the Closed state.</span></span> <span data-ttu-id="c2018-166">Beim Aufrufen von <xref:System.ServiceModel.ICommunicationObject.Abort%2A> wird nicht abgeschlossene Arbeit beendet.</span><span class="sxs-lookup"><span data-stu-id="c2018-166">Calling <xref:System.ServiceModel.ICommunicationObject.Abort%2A> terminates any unfinished work.</span></span>  
  
<a name="ChannelAndChannelListener"></a>   
## <a name="channel-factory-and-channel-listener"></a><span data-ttu-id="c2018-167">Kanalfactory und Kanallistener</span><span class="sxs-lookup"><span data-stu-id="c2018-167">Channel Factory and Channel Listener</span></span>  
 <span data-ttu-id="c2018-168">Der nächste Schritt beim Schreiben eines benutzerdefinierten Transports besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle und von <xref:System.ServiceModel.Channels.IChannelListener> für Dienstkanäle.</span><span class="sxs-lookup"><span data-stu-id="c2018-168">The next step in writing a custom transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span> <span data-ttu-id="c2018-169">Die Kanalebene verwendet ein Factorymuster zum Erstellen von Kanälen.</span><span class="sxs-lookup"><span data-stu-id="c2018-169">The channel layer uses a factory pattern for constructing channels.</span></span> <span data-ttu-id="c2018-170">WCF stellt basisklassenhilfen für diesen Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="c2018-170">WCF provides base class helpers for this process.</span></span>  
  
- <span data-ttu-id="c2018-171">Die <xref:System.ServiceModel.Channels.CommunicationObject>-Klasse implementiert <xref:System.ServiceModel.ICommunicationObject> und setzt den zuvor in Schritt 2 beschriebenen Zustandsautomaten durch.</span><span class="sxs-lookup"><span data-stu-id="c2018-171">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine previously described in Step 2.</span></span> 

- <span data-ttu-id="c2018-172">Die <xref:System.ServiceModel.Channels.ChannelManagerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.CommunicationObject> und bietet eine einheitliche Basisklasse für <xref:System.ServiceModel.Channels.ChannelFactoryBase> und <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span><span class="sxs-lookup"><span data-stu-id="c2018-172">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="c2018-173">Die <xref:System.ServiceModel.Channels.ChannelManagerBase>-Klasse funktioniert in Verbindung mit <xref:System.ServiceModel.Channels.ChannelBase>. Dies ist eine Basisklasse, die <xref:System.ServiceModel.Channels.IChannel> implementiert.</span><span class="sxs-lookup"><span data-stu-id="c2018-173">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
- <span data-ttu-id="c2018-174">Die <xref:System.ServiceModel.Channels.ChannelFactoryBase> -Klasse implementiert <xref:System.ServiceModel.Channels.ChannelManagerBase> und <xref:System.ServiceModel.Channels.IChannelFactory> und konsolidiert die `CreateChannel` -Überladungen in einer `OnCreateChannel` abstrakte Methode.</span><span class="sxs-lookup"><span data-stu-id="c2018-174">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
- <span data-ttu-id="c2018-175">Die <xref:System.ServiceModel.Channels.ChannelListenerBase> -Klasse implementiert <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="c2018-175">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="c2018-176">Die Klasse wird für grundlegende Zustandsverwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2018-176">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="c2018-177">In diesem Beispiel ist die Factoryimplementierung in "UdpChannelFactory.cs" enthalten, und die Listenerimplementierung ist in "UdpChannelListener.cs" enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2018-177">In this sample, the factory implementation is contained in UdpChannelFactory.cs and the listener implementation is contained in UdpChannelListener.cs.</span></span> <span data-ttu-id="c2018-178">Die <xref:System.ServiceModel.Channels.IChannel>-Implementierungen sind in "UdpOutputChannel.cs" und "UdpInputChannel.cs" enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2018-178">The <xref:System.ServiceModel.Channels.IChannel> implementations are in UdpOutputChannel.cs and UdpInputChannel.cs.</span></span>  
  
### <a name="the-udp-channel-factory"></a><span data-ttu-id="c2018-179">Die UDP-Kanalfactory</span><span class="sxs-lookup"><span data-stu-id="c2018-179">The UDP Channel Factory</span></span>  
 <span data-ttu-id="c2018-180">Die `UdpChannelFactory` wird von <xref:System.ServiceModel.Channels.ChannelFactoryBase> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c2018-180">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="c2018-181">Das Beispiel überschreibt <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A>, um Zugriff auf die Nachrichtenversion des Nachrichtenencoders zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="c2018-181">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="c2018-182">Das Beispiel überschreibt auch <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, um beim Übergang des Zustandsautomaten die Instanz von <xref:System.ServiceModel.Channels.BufferManager> zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c2018-182">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> so that we can tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="c2018-183">Der UDP-Ausgabekanal</span><span class="sxs-lookup"><span data-stu-id="c2018-183">The UDP Output Channel</span></span>  
 <span data-ttu-id="c2018-184">Der `UdpOutputChannel` implementiert <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="c2018-184">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="c2018-185">Der Konstruktor überprüft die Argumente und erstellt ein Ziel-<xref:System.Net.EndPoint>-Objekt, das auf der übergebenen <xref:System.ServiceModel.EndpointAddress> basiert.</span><span class="sxs-lookup"><span data-stu-id="c2018-185">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 <span data-ttu-id="c2018-186">Der Kanal kann ordnungsgemäß oder nicht ordnungsgemäß geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-186">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="c2018-187">Bei ordnungsgemäßer Schließung wird der Socket geschlossen, und die `OnClose`-Methode der Basisklasse wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c2018-187">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="c2018-188">Wenn dadurch eine Ausnahme ausgelöst wird, ruft die Infrastruktur `Abort` auf, um sicherzustellen, dass der Kanal bereinigt wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-188">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp
this.socket.Close(0);  
```  
  
 <span data-ttu-id="c2018-189">Implementieren Sie anschließend `Send()` und `BeginSend()` / `EndSend()`.</span><span class="sxs-lookup"><span data-stu-id="c2018-189">We then implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="c2018-190">Dieser Vorgang ist in zwei Hauptabschnitte unterteilt.</span><span class="sxs-lookup"><span data-stu-id="c2018-190">This breaks down into two main sections.</span></span> <span data-ttu-id="c2018-191">Serialisieren Sie zuerst die Nachricht in ein Bytearray:</span><span class="sxs-lookup"><span data-stu-id="c2018-191">First we serialize the message into a byte array.</span></span>  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="c2018-192">Senden Sie anschließend die resultierenden Daten:</span><span class="sxs-lookup"><span data-stu-id="c2018-192">Then we send the resulting data on the wire.</span></span>  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a><span data-ttu-id="c2018-193">Der UdpChannelListener</span><span class="sxs-lookup"><span data-stu-id="c2018-193">The UdpChannelListener</span></span>  
 <span data-ttu-id="c2018-194">Die `UdpChannelListener` abgeleitet, dass das Beispiel implementiert die <xref:System.ServiceModel.Channels.ChannelListenerBase> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c2018-194">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="c2018-195">Er verwendet einen einzelnen UDP-Socket, um Datagramme zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="c2018-195">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="c2018-196">Die `OnOpen`-Methode empfängt Daten mit dem UDP-Socket in einer asynchronen Schleife.</span><span class="sxs-lookup"><span data-stu-id="c2018-196">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="c2018-197">Die Daten werden dann mit dem Nachrichtencodierungsframework in Nachrichten konvertiert:</span><span class="sxs-lookup"><span data-stu-id="c2018-197">The data are then converted into messages using the Message Encoding Framework.</span></span>  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 <span data-ttu-id="c2018-198">Da derselbe Datagrammkanal Nachrichten darstellt, die aus einer Reihe von Quellen eintreffen, ist der `UdpChannelListener` ein Singletonlistener.</span><span class="sxs-lookup"><span data-stu-id="c2018-198">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="c2018-199">Es gibt höchstens einen aktiven <xref:System.ServiceModel.Channels.IChannel> diesem Listener gleichzeitig zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c2018-199">There is, at most, one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="c2018-200">In diesem Beispiel wird nur dann ein weiterer generiert, wenn ein Kanal, der mit der `AcceptChannel`-Methode zurückgegeben wird, anschließend freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-200">The sample generates another one only if a channel that is returned by the `AcceptChannel` method is subsequently disposed.</span></span> <span data-ttu-id="c2018-201">Wenn eine Nachricht empfangen wird, wird sie in diesem Singletonkanal in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="c2018-201">When a message is received, it is enqueued into this singleton channel.</span></span>  
  
#### <a name="udpinputchannel"></a><span data-ttu-id="c2018-202">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="c2018-202">UdpInputChannel</span></span>  
 <span data-ttu-id="c2018-203">Die `UdpInputChannel` -Klasse implementiert `IInputChannel`.</span><span class="sxs-lookup"><span data-stu-id="c2018-203">The `UdpInputChannel` class implements `IInputChannel`.</span></span> <span data-ttu-id="c2018-204">Sie besteht aus einer Warteschlange mit eingehenden Nachrichten, die vom `UdpChannelListener`-Socket gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-204">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="c2018-205">Diese Nachrichten werden mit der `IInputChannel.Receive`-Methode aus der Warteschlange entfernt.</span><span class="sxs-lookup"><span data-stu-id="c2018-205">These messages are dequeued by the `IInputChannel.Receive` method.</span></span>  
  
<a name="AddingABindingElement"></a>   
## <a name="adding-a-binding-element"></a><span data-ttu-id="c2018-206">Hinzufügen eines Bindungselements</span><span class="sxs-lookup"><span data-stu-id="c2018-206">Adding a Binding Element</span></span>  
 <span data-ttu-id="c2018-207">Nachdem nun die Factorys und Kanäle erstellt sind, müssen sie der ServiceModel-Laufzeit über eine Bindung verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-207">Now that the factories and channels are built, we must expose them to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="c2018-208">Eine Bindung ist eine Auflistung von Bindungselementen, die den mit einer Dienstadresse verknüpften Kommunikationsstapel darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2018-208">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="c2018-209">Jedes Element im Stapel wird durch dargestellt eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="c2018-209">Each element in the stack is represented by a [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span>  
  
 <span data-ttu-id="c2018-210">Im Beispiel ist das Bindungselement `UdpTransportBindingElement`, das von <xref:System.ServiceModel.Channels.TransportBindingElement> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-210">In the sample, the binding element is `UdpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="c2018-211">Es überschreibt die folgenden Methoden zum Erstellen der der Bindung zugeordneten Factorys.</span><span class="sxs-lookup"><span data-stu-id="c2018-211">It overrides the following methods to build the factories associated with our binding.</span></span>  
  
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
  
 <span data-ttu-id="c2018-212">Es enthält auch Member zum Klonen des `BindingElement` und Zurückgeben unseres Schemas (soap.udp).</span><span class="sxs-lookup"><span data-stu-id="c2018-212">It also contains members for cloning the `BindingElement` and returning our scheme (soap.udp).</span></span>  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a><span data-ttu-id="c2018-213">Hinzufügen von Metadatenunterstützung für ein Transportbindungselement</span><span class="sxs-lookup"><span data-stu-id="c2018-213">Adding Metadata Support for a Transport Binding Element</span></span>  
 <span data-ttu-id="c2018-214">Um den Transport in ein Metadatensystem zu integrieren, muss dieser sowohl den Import als auch den Export von Richtlinien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2018-214">To integrate our transport into the metadata system, we must support both the import and export of policy.</span></span> <span data-ttu-id="c2018-215">Dadurch können Clients für die Bindung zu generieren die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c2018-215">This allows us to generate clients of our binding through the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="c2018-216">Hinzufügen von WSDL-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c2018-216">Adding WSDL Support</span></span>  
 <span data-ttu-id="c2018-217">Das Transportbindungselement in einer Bindung ist für den Export und Import von Adressierungsinformationen in/zu Metadaten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="c2018-217">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="c2018-218">Bei der Nutzung einer SOAP-Bindung sollte das Transportbindungselement ebenfalls einen korrekten Transport-URI in die Metadaten exportieren.</span><span class="sxs-lookup"><span data-stu-id="c2018-218">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="c2018-219">WSDL-Export</span><span class="sxs-lookup"><span data-stu-id="c2018-219">WSDL Export</span></span>  
 <span data-ttu-id="c2018-220">Um Adressierungsinformationen zu exportieren, implementiert das `UdpTransportBindingElement` die `IWsdlExportExtension`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2018-220">To export addressing information the `UdpTransportBindingElement` implements the `IWsdlExportExtension` interface.</span></span> <span data-ttu-id="c2018-221">Die `ExportEndpoint`-Methode fügt dem WSDL-Port die richtigen Adressierungsinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2018-221">The `ExportEndpoint` method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="c2018-222">Die `UdpTransportBindingElement`-Implementierung der `ExportEndpoint`-Methode exportiert ebenfalls einen Transport-URI, wenn der Endpunkt eine SOAP-Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2018-222">The `UdpTransportBindingElement` implementation of the `ExportEndpoint` method also exports a transport URI when the endpoint uses a SOAP binding.</span></span>  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="c2018-223">WSDL-Import</span><span class="sxs-lookup"><span data-stu-id="c2018-223">WSDL Import</span></span>  
 <span data-ttu-id="c2018-224">Um das WSDL-Importsystem auf die Handhabung des Imports von Adressen zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für "Svcutil.exe" hinzu (wie in der Datei "Svcutil.exe.config" gezeigt):</span><span class="sxs-lookup"><span data-stu-id="c2018-224">To extend the WSDL import system to handle importing the addresses, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
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
  
 <span data-ttu-id="c2018-225">Bei der Ausführung von "Svcutil.exe" gibt es zwei Optionen, um "Svcutil.exe" dazu zu bewegen, die WSDL-Importerweiterungen zu laden:</span><span class="sxs-lookup"><span data-stu-id="c2018-225">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="c2018-226">Verweisen Sie Svcutil.exe Konfigurationsdatei mithilfe der/svcutilconfig:\<Datei >.</span><span class="sxs-lookup"><span data-stu-id="c2018-226">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="c2018-227">Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2018-227">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="c2018-228">Der `UdpBindingElementImporter`-Typ implementiert die `IWsdlImportExtension`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2018-228">The `UdpBindingElementImporter` type implements the `IWsdlImportExtension` interface.</span></span> <span data-ttu-id="c2018-229">Die `ImportEndpoint`-Methode importiert die Adresse vom WSDL-Port.</span><span class="sxs-lookup"><span data-stu-id="c2018-229">The `ImportEndpoint` method imports the address from the WSDL port.</span></span>  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="c2018-230">Hinzufügen von Richtlinienunterstützung</span><span class="sxs-lookup"><span data-stu-id="c2018-230">Adding Policy Support</span></span>  
 <span data-ttu-id="c2018-231">Das benutzerdefinierte Bindungselement kann Richtlinienassertionen in die WSDL-Bindung für einen Dienstendpunkt exportieren, um die Funktionen dieses Bindungselements auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="c2018-231">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="c2018-232">Richtlinienexport</span><span class="sxs-lookup"><span data-stu-id="c2018-232">Policy Export</span></span>  
 <span data-ttu-id="c2018-233">Die `UdpTransportBindingElement` -Typ implementiert `IPolicyExportExtension` zum Hinzufügen der Unterstützung für das Exportieren der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c2018-233">The `UdpTransportBindingElement` type implements `IPolicyExportExtension` to add support for exporting policy.</span></span> <span data-ttu-id="c2018-234">Als Ergebnis schließt `System.ServiceModel.MetadataExporter``UdpTransportBindingElement` in die Generierung der Richtlinie für eine Bindung ein, die dieses enthält.</span><span class="sxs-lookup"><span data-stu-id="c2018-234">As a result, `System.ServiceModel.MetadataExporter` includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="c2018-235">Fügen Sie in `IPolicyExportExtension.ExportPolicy` eine Assertion für UDP und eine weitere Assertion ein, wenn Sie sich im Multicastmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="c2018-235">In `IPolicyExportExtension.ExportPolicy`, we add an assertion for UDP and another assertion if we are in multicast mode.</span></span> <span data-ttu-id="c2018-236">Grund hierfür ist, dass der Multicastmodus Einfluss auf die Art und Weise hat, in der der Kommunikationsstapel erstellt wird, weshalb eine Koordinierung zwischen beiden Seiten stattfinden muss.</span><span class="sxs-lookup"><span data-stu-id="c2018-236">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix, 
        UdpPolicyStrings.MulticastAssertion, 
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="c2018-237">Da benutzerdefinierte Transportbindungselemente für die Handhabung der Adressierung verantwortlich sind, muss die `IPolicyExportExtension`-Implementierung auf dem `UdpTransportBindingElement` auch den Export der geeigneten WS-Adressierungsrichtlinienassertionen handhaben, um die Version der verwendeten WS-Adressierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2018-237">Because custom transport binding elements are responsible for handling addressing, the `IPolicyExportExtension` implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="c2018-238">Richtlinienimport</span><span class="sxs-lookup"><span data-stu-id="c2018-238">Policy Import</span></span>  
 <span data-ttu-id="c2018-239">Um das Richtlinienimportsystem zu erweitern, fügen Sie die folgende Konfiguration zur Konfigurationsdatei für "Svcutil.exe" hinzu (wie in der Datei "Svcutil.exe.config" gezeigt):</span><span class="sxs-lookup"><span data-stu-id="c2018-239">To extend the Policy Import system, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
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
  
 <span data-ttu-id="c2018-240">Dann implementieren Sie `IPolicyImporterExtension` aus der registrierten Klasse (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="c2018-240">Then we implement `IPolicyImporterExtension` from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="c2018-241">Prüfen Sie in `ImportPolicy()` die Assertionen im entsprechenden Namespace, verarbeiten Sie sie für die Generierung des Transports, und prüfen Sie, ob Multicast vorliegt.</span><span class="sxs-lookup"><span data-stu-id="c2018-241">In `ImportPolicy()`, we look through the assertions in our namespace, and process the ones for generating the transport and check whether it is multicast.</span></span> <span data-ttu-id="c2018-242">Entfernen Sie darüber hinaus die gehandhabten Assertionen aus der Liste der Bindungsassertionen.</span><span class="sxs-lookup"><span data-stu-id="c2018-242">We also must remove the assertions we handle from the list of binding assertions.</span></span> <span data-ttu-id="c2018-243">Erneut stehen bei der Ausführung von "Svcutil.exe" zwei Optionen für die Integration zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c2018-243">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="c2018-244">Verweisen Sie Svcutil.exe Konfigurationsdatei mithilfe der/svcutilconfig:\<Datei >.</span><span class="sxs-lookup"><span data-stu-id="c2018-244">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="c2018-245">Fügen Sie den Konfigurationsabschnitt zu Svcutil.exe.config im gleichen Verzeichnis wie Svcutil.exe hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2018-245">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
<a name="AddingAStandardBinding"></a>   
## <a name="adding-a-standard-binding"></a><span data-ttu-id="c2018-246">Hinzufügen einer Standardbindung</span><span class="sxs-lookup"><span data-stu-id="c2018-246">Adding a Standard Binding</span></span>  
 <span data-ttu-id="c2018-247">Das Bindungselement kann auf die beiden folgenden Arten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c2018-247">Our binding element can be used in the following two ways:</span></span>  
  
- <span data-ttu-id="c2018-248">Durch eine benutzerdefinierte Bindung: Eine benutzerdefinierte Bindung ermöglicht den Benutzer, eigene Bindungen basierend auf einer beliebigen Gruppe von Bindungselementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2018-248">Through a custom binding: A custom binding allows the user to create their own binding based on an arbitrary set of binding elements.</span></span>  
  
- <span data-ttu-id="c2018-249">Über eine vom System bereitgestellte Bindung, die das Bindungselement enthält.</span><span class="sxs-lookup"><span data-stu-id="c2018-249">By using a system-provided binding that includes our binding element.</span></span> <span data-ttu-id="c2018-250">WCF bietet mehrere vom System definierte Bindungen, z. B. `BasicHttpBinding`, `NetTcpBinding`, und `WsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="c2018-250">WCF provides a number of these system-defined bindings, such as `BasicHttpBinding`, `NetTcpBinding`, and `WsHttpBinding`.</span></span> <span data-ttu-id="c2018-251">Jede dieser Bindungen wird einem genau definierten Profil zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c2018-251">Each of these bindings is associated with a well-defined profile.</span></span>  
  
 <span data-ttu-id="c2018-252">Das Beispiel implementiert eine Profilbindung in `SampleProfileUdpBinding`, die von <xref:System.ServiceModel.Channels.Binding> abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="c2018-252">The sample implements profile binding in `SampleProfileUdpBinding`, which derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="c2018-253">`SampleProfileUdpBinding` enthält bis zu vier Bindungselemente: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` und `ReliableSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="c2018-253">The `SampleProfileUdpBinding` contains up to four binding elements within it: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement`, and `ReliableSessionBindingElement`.</span></span>  
  
```csharp
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
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="c2018-254">Hinzufügen eines benutzerdefinierten Standardbindungsimportprogramms</span><span class="sxs-lookup"><span data-stu-id="c2018-254">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="c2018-255">„Svcutil.exe“ und der `WsdlImporter`-Typ erkennen und importieren vom System definierte Bindungen standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="c2018-255">Svcutil.exe and the `WsdlImporter` type, by default, recognizes and imports system-defined bindings.</span></span> <span data-ttu-id="c2018-256">Andernfalls wird die Bindung als `CustomBinding`-Instanz importiert.</span><span class="sxs-lookup"><span data-stu-id="c2018-256">Otherwise, the binding gets imported as a `CustomBinding` instance.</span></span> <span data-ttu-id="c2018-257">Zur Aktivierung des Imports der `WsdlImporter` für „Svcutil.exe“ und den `SampleProfileUdpBinding`, fungiert der `UdpBindingElementImporter` auch als benutzerdefiniertes Importprogramm für Standardbindungen.</span><span class="sxs-lookup"><span data-stu-id="c2018-257">To enable Svcutil.exe and the `WsdlImporter` to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="c2018-258">Ein benutzerdefiniertes Standardbindungsimportprogramm implementiert die `ImportEndpoint`-Methode auf der `IWsdlImportExtension`-Schnittstelle, um zu prüfen, ob die aus den Metadaten importierte `CustomBinding`-Instanz von einer spezifischen Standardbindung hätte generiert werden können.</span><span class="sxs-lookup"><span data-stu-id="c2018-258">A custom standard binding importer implements the `ImportEndpoint` method on the `IWsdlImportExtension` interface to examine the `CustomBinding` instance imported from metadata to see whether it could have been generated by a specific standard binding.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="c2018-259">Allgemein beinhaltet die Implementierung eines benutzerdefinierten Importprogramms für Standardbindungen die Überprüfung der Eigenschaften der importierten Bindungen, um zu bestätigen, dass sich nur Eigenschaften geändert haben, die von der Standardbindung hätten festgelegt werden können, und es sich bei allen anderen Eigenschaften um die Standardwerte handelt.</span><span class="sxs-lookup"><span data-stu-id="c2018-259">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="c2018-260">Eine grundlegende Strategie für die Implementierung eines Importprogramms für Standardbindungen ist die Erstellung einer Standardbindung, die Weitergabe der Eigenschaften von den Bindungselementen an die von der Standardbindung unterstützte Standardbindungsinstanz und der Vergleich der Bindungselemente der Standardbindung mit den importierten Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="c2018-260">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>  
  
<a name="AddingConfigurationSupport"></a>   
## <a name="adding-configuration-support"></a><span data-ttu-id="c2018-261">Hinzufügen von Konfigurationsunterstützung</span><span class="sxs-lookup"><span data-stu-id="c2018-261">Adding Configuration Support</span></span>  
 <span data-ttu-id="c2018-262">Um unseren Transport durch Konfiguration verfügbar zu machen, müssen Sie zwei Konfigurationsabschnitte implementieren.</span><span class="sxs-lookup"><span data-stu-id="c2018-262">To expose our transport through configuration, we must implement two configuration sections.</span></span> <span data-ttu-id="c2018-263">Der erste ist ein `BindingElementExtensionElement` für `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="c2018-263">The first is a `BindingElementExtensionElement` for `UdpTransportBindingElement`.</span></span> <span data-ttu-id="c2018-264">Auf diese Weise können `CustomBinding`-Implementierungen auf das im Beispiel erstellte Bindungselement verweisen.</span><span class="sxs-lookup"><span data-stu-id="c2018-264">This is so that `CustomBinding` implementations can reference our binding element.</span></span> <span data-ttu-id="c2018-265">Der zweite ist eine `Configuration` für `SampleProfileUdpBinding`.</span><span class="sxs-lookup"><span data-stu-id="c2018-265">The second is a `Configuration` for our `SampleProfileUdpBinding`.</span></span>  
  
### <a name="binding-element-extension-element"></a><span data-ttu-id="c2018-266">Element für Bindungselementerweiterungen</span><span class="sxs-lookup"><span data-stu-id="c2018-266">Binding Element Extension Element</span></span>  
 <span data-ttu-id="c2018-267">Der Abschnitt `UdpTransportElement` ist ein `BindingElementExtensionElement`, das die `UdpTransportBindingElement` für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c2018-267">The section `UdpTransportElement` is a `BindingElementExtensionElement` that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="c2018-268">Mit wenigen grundlegenden Überschreibungen definiert das Beispiel den Konfigurationsabschnittsnamen, den Typ des Bindungselements und wie das Bindungselement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-268">With a few basic overrides, we define our configuration section name, the type of our binding element and how to create our binding element.</span></span> <span data-ttu-id="c2018-269">Benutzer können dann wie im folgenden Code den Erweiterungsabschnitt in einer Konfigurationsdatei registrieren.</span><span class="sxs-lookup"><span data-stu-id="c2018-269">We can then register our extension section in a configuration file as shown in the following code.</span></span>  
  
```xml
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
  
 <span data-ttu-id="c2018-270">Auf die Erweiterung kann von benutzerdefinierten Bindungen verwiesen werden, um UDP als Transport zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c2018-270">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml
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
  
### <a name="binding-section"></a><span data-ttu-id="c2018-271">Bindungsabschnitt</span><span class="sxs-lookup"><span data-stu-id="c2018-271">Binding Section</span></span>  
 <span data-ttu-id="c2018-272">Der Abschnitt `SampleProfileUdpBindingCollectionElement` ist ein `StandardBindingCollectionElement`, das die `SampleProfileUdpBinding` für das Konfigurationssystem verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c2018-272">The section `SampleProfileUdpBindingCollectionElement` is a `StandardBindingCollectionElement` that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="c2018-273">Dem `SampleProfileUdpBindingConfigurationElement`, das sich von `StandardBindingElement` herleitet, wird der Großteil der Implementierung übertragen.</span><span class="sxs-lookup"><span data-stu-id="c2018-273">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from `StandardBindingElement`.</span></span> <span data-ttu-id="c2018-274">Die `SampleProfileUdpBindingConfigurationElement` verfügt über Eigenschaften, die die Eigenschaften auf entsprechen `SampleProfileUdpBinding`, und Funktionen für die Zuordnung der `ConfigurationElement` Bindung.</span><span class="sxs-lookup"><span data-stu-id="c2018-274">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="c2018-275">Schließlich wird die `OnApplyConfiguration`-Methode in der `SampleProfileUdpBinding` überschrieben. Dies wird im folgenden Beispielcode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c2018-275">Finally, override the `OnApplyConfiguration` method in our `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="c2018-276">Um diesen Handler mit dem Konfigurationssystem zu registrieren, fügen Sie der relevanten Konfigurationsdatei den folgenden Abschnitt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2018-276">To register this handler with the configuration system, we add the following section to the relevant configuration file.</span></span>  
  
```xml
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
  
 <span data-ttu-id="c2018-277">Darauf kann dann vom serviceModel-Konfigurationsabschnitt verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c2018-277">It can then be referenced from the serviceModel configuration section.</span></span>  
  
```xml
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
  
## <a name="the-udp-test-service-and-client"></a><span data-ttu-id="c2018-278">Der UDP-Testdienst und der Client</span><span class="sxs-lookup"><span data-stu-id="c2018-278">The UDP Test Service and Client</span></span>  
 <span data-ttu-id="c2018-279">Testcode für die Verwendung dieses Beispieltransports ist in den UdpTestService- und UdpTestClient-Verzeichnissen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2018-279">Test code for using this sample transport is available in the UdpTestService and UdpTestClient directories.</span></span> <span data-ttu-id="c2018-280">Der Dienstcode besteht aus zwei Tests: Ein Test richtet die Bindungen und Endpunkte über den Code ein und der andere über die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c2018-280">The service code consists of two tests—one test sets up bindings and endpoints from code and the other does it through configuration.</span></span> <span data-ttu-id="c2018-281">Beide Tests verwenden zwei Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="c2018-281">Both tests use two endpoints.</span></span> <span data-ttu-id="c2018-282">Ein Endpunkt verwendet die `SampleUdpProfileBinding` mit [ \<ReliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) festgelegt `true`.</span><span class="sxs-lookup"><span data-stu-id="c2018-282">One endpoint uses the `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `true`.</span></span> <span data-ttu-id="c2018-283">Der andere Endpunkt verwendet eine benutzerdefinierte Bindung mit `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="c2018-283">The other endpoint uses a custom binding with `UdpTransportBindingElement`.</span></span> <span data-ttu-id="c2018-284">Dies ist äquivalent zur Verwendung `SampleUdpProfileBinding` mit [ \<ReliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) festgelegt `false`.</span><span class="sxs-lookup"><span data-stu-id="c2018-284">This is equivalent to using `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `false`.</span></span> <span data-ttu-id="c2018-285">Beide Tests erstellen einen Dienst, fügen einen Endpunkt für jede Bindung hinzu, öffnen den Dienst und warten anschließend darauf, dass der Benutzer die EINGABETASTE drückt, bevor der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2018-285">Both tests create a service, add an endpoint for each binding, open the service and then wait for the user to hit ENTER before closing the service.</span></span>  
  
 <span data-ttu-id="c2018-286">Wenn Sie die Testanwendung für den Dienst starten, sollte folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c2018-286">When you start the service test application you should see the following output.</span></span>  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 <span data-ttu-id="c2018-287">Sie können dann die Testclientanwendung für die veröffentlichten Endpunkte ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2018-287">You can then run the test client application against the published endpoints.</span></span> <span data-ttu-id="c2018-288">Die Clienttestanwendung erstellt für jeden Endpunkt einen Client und sendet fünf Nachrichten an jeden Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="c2018-288">The client test application creates a client for each endpoint and sends five messages to each endpoint.</span></span> <span data-ttu-id="c2018-289">Im Folgenden finden Sie die Ausgabe auf dem Client:</span><span class="sxs-lookup"><span data-stu-id="c2018-289">The following output is on the client.</span></span>  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 <span data-ttu-id="c2018-290">Im Folgenden finden Sie die vollständige Ausgabe auf dem Dienst:</span><span class="sxs-lookup"><span data-stu-id="c2018-290">The following is the full output on the service.</span></span>  
  
```console
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
  
 <span data-ttu-id="c2018-291">Um die Clientanwendung für Endpunkte auszuführen, die mithilfe einer Konfiguration veröffentlicht wurden, drücken Sie die EINGABETASTE im Dienst, und führen Sie den Testclient erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c2018-291">To run the client application against endpoints published using configuration, hit ENTER on the service and then run the test client again.</span></span> <span data-ttu-id="c2018-292">Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:</span><span class="sxs-lookup"><span data-stu-id="c2018-292">You should see the following output on the service.</span></span>  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 <span data-ttu-id="c2018-293">Durch das erneute Ausführen des Clients werden die gleichen Ergebnisse erzielt wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="c2018-293">Running the client again yields the same as the preceding results.</span></span>  
  
 <span data-ttu-id="c2018-294">Um den Clientcode und die Konfiguration mithilfe von "Svcutil.exe" neu zu generieren, starten Sie die Dienstanwendung, und führen Sie dann "Svcutil.exe" wie folgt aus dem Stammverzeichnis des Beispiels aus:</span><span class="sxs-lookup"><span data-stu-id="c2018-294">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe from the root directory of the sample.</span></span>  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 <span data-ttu-id="c2018-295">Beachten Sie, dass "Svcutil.exe" nicht die Bindungserweiterungskonfiguration für `SampleProfileUdpBinding` generiert. Sie müssen diese daher manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2018-295">Note that Svcutil.exe does not generate the binding extension configuration for the `SampleProfileUdpBinding`, so you must add it manually.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>      
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c2018-296">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c2018-296">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c2018-297">Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c2018-297">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="c2018-298">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c2018-298">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c2018-299">Informationen finden Sie im vorhergehenden Abschnitt "Der UDP-Testdienst und der Client".</span><span class="sxs-lookup"><span data-stu-id="c2018-299">Refer to the preceding "The UDP Test Service and Client" section.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c2018-300">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c2018-300">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c2018-301">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c2018-301">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c2018-302">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c2018-302">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c2018-303">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c2018-303">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
