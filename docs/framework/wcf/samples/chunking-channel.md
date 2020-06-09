---
title: Segmentierungskanal
ms.date: 03/30/2017
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
ms.openlocfilehash: 7a5e5292bcb37e83de21458716e34887a0557d91
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585544"
---
# <a name="chunking-channel"></a><span data-ttu-id="0453c-102">Segmentierungskanal</span><span class="sxs-lookup"><span data-stu-id="0453c-102">Chunking Channel</span></span>

<span data-ttu-id="0453c-103">Beim Senden großer Nachrichten mit Windows Communication Foundation (WCF) ist es häufig wünschenswert, die Menge an Arbeitsspeicher einzuschränken, die zum Puffern dieser Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-103">When sending large messages using Windows Communication Foundation (WCF), it is often desirable to limit the amount of memory used to buffer those messages.</span></span> <span data-ttu-id="0453c-104">Eine mögliche Lösung besteht im Streamen des Nachrichtentexts (vorausgesetzt, der größte Teil der Daten befindet sich dort).</span><span class="sxs-lookup"><span data-stu-id="0453c-104">One possible solution is to stream the message body (assuming the bulk of the data is in the body).</span></span> <span data-ttu-id="0453c-105">Einige Protokolle erfordern jedoch die Pufferung der Nachricht als Ganzes.</span><span class="sxs-lookup"><span data-stu-id="0453c-105">However some protocols require buffering of the entire message.</span></span> <span data-ttu-id="0453c-106">Zuverlässiges Messaging und Sicherheit sind zwei solche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0453c-106">Reliable messaging and security are two such examples.</span></span> <span data-ttu-id="0453c-107">Eine weitere mögliche Lösung besteht darin, die große Nachricht in kleinere Nachrichten zu teilen, so genannte Segmente, diese Segmente jeweils einzeln zu senden und dann auf der Empfängerseite die große Nachricht wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0453c-107">Another possible solution is to divide up the large message into smaller messages called chunks, send those chunks one chunk at a time, and reconstitute the large message on the receiving side.</span></span> <span data-ttu-id="0453c-108">Die Anwendung selbst könnte diese Segmentierung und Desegmentierung vornehmen, oder es könnte alternativ ein benutzerdefinierter Kanal dafür verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0453c-108">The application itself could do this chunking and de-chunking or it could use a custom channel to do it.</span></span> <span data-ttu-id="0453c-109">Das Beispiel für den Segmentierungskanal zeigt, wie mit einem benutzerdefinierten Protokollkanal oder Mehrschicht-Kanal das Segmentieren und Desegmentieren beliebig großer Nachrichten vorgenommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0453c-109">The chunking channel sample shows how a custom protocol or layered channel can be used to do chunking and de-chunking of arbitrarily large messages.</span></span>

<span data-ttu-id="0453c-110">Die Segmentierung sollte stets nur dann eingesetzt werden, wenn die gesamte Nachricht, die gesendet werden soll, erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0453c-110">Chunking should always be employed only after the entire message to be sent has been constructed.</span></span> <span data-ttu-id="0453c-111">Ein Segmentierungskanal sollte immer unter einem Sicherheitskanal und einem zuverlässigen Sitzungskanal angeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="0453c-111">A chunking channel should always be layered below a security channel and a reliable session channel.</span></span>

> [!NOTE]
> <span data-ttu-id="0453c-112">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="0453c-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0453c-113">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0453c-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0453c-114">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0453c-114">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="0453c-115">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0453c-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0453c-116">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0453c-116">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`

## <a name="chunking-channel-assumptions-and-limitations"></a><span data-ttu-id="0453c-117">Segmentierungskanal &#160; Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0453c-117">Chunking Channel Assumptions and Limitations</span></span>

### <a name="message-structure"></a><span data-ttu-id="0453c-118">Nachrichtenstruktur</span><span class="sxs-lookup"><span data-stu-id="0453c-118">Message Structure</span></span>

<span data-ttu-id="0453c-119">Der Segmentierungskanal geht bei zu segmentierenden Nachrichten von folgender Nachrichtenstruktur aus:</span><span class="sxs-lookup"><span data-stu-id="0453c-119">The chunking channel assumes the following message structure for messages to be chunked:</span></span>

```xml
<soap:Envelope>
  <!-- headers -->
  <soap:Body>
    <operationElement>
      <paramElement>data to be chunked</paramElement>
    </operationElement>
  </soap:Body>
</soap:Envelope>
```

<span data-ttu-id="0453c-120">Bei Verwendung von ServiceModel erfüllen Vertragsvorgänge mit 1 Eingabeparameter diese Nachrichtenform bei ihrer Eingabenachricht.</span><span class="sxs-lookup"><span data-stu-id="0453c-120">When using the ServiceModel, contract operations that have 1 input parameter comply with this shape of message for their input message.</span></span> <span data-ttu-id="0453c-121">Ebenso erfüllen Vertragsvorgänge mit 1 Ausgabeparameter bzw. Rückgabewert diese Nachrichtenform bei ihrer Ausgabenachricht.</span><span class="sxs-lookup"><span data-stu-id="0453c-121">Similarly, contract operations that have 1 output parameter or return value comply with this shape of message for their output message.</span></span> <span data-ttu-id="0453c-122">Es folgen Beispiele für solche Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="0453c-122">The following are examples of such operations:</span></span>

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    Stream EchoStream(Stream stream);

    [OperationContract]
    Stream DownloadStream();

    [OperationContract(IsOneWay = true)]
    void UploadStream(Stream stream);
}
```

### <a name="sessions"></a><span data-ttu-id="0453c-123">Sitzungen</span><span class="sxs-lookup"><span data-stu-id="0453c-123">Sessions</span></span>

<span data-ttu-id="0453c-124">Der Segmentierungskanal erfordert, dass Nachrichten genau einmal zugestellt werden, und zwar in geordneter Zustellung von Einzelnachrichten (Segmenten).</span><span class="sxs-lookup"><span data-stu-id="0453c-124">The chunking channel requires messages to be delivered exactly once, in ordered delivery of messages (chunks).</span></span> <span data-ttu-id="0453c-125">Dies bedeutet, dass der zugrunde liegende Kanalstapel sitzungsbasiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="0453c-125">This means the underlying channel stack must be sessionful.</span></span> <span data-ttu-id="0453c-126">Sitzungen können vom Transport bereitgestellt werden (z.&#160;B. TCP-Transport) oder durch einen sitzungsbasierten Protokollkanal (z.&#160;B. ReliableSession-Kanal).</span><span class="sxs-lookup"><span data-stu-id="0453c-126">Sessions can be provided by the transport (for example, TCP transport) or by a sessionful protocol channel (for example, ReliableSession channel).</span></span>

### <a name="asynchronous-send-and-receive"></a><span data-ttu-id="0453c-127">Asynchrones Senden und Empfangen</span><span class="sxs-lookup"><span data-stu-id="0453c-127">Asynchronous Send and Receive</span></span>

<span data-ttu-id="0453c-128">Asynchrone Methoden zum Senden und Empfangen sind in dieser Version des Segmentierungskanalbeispiels nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="0453c-128">Asynchronous send and receive methods are not implemented in this version of the chunking channel sample.</span></span>

## <a name="chunking-protocol"></a><span data-ttu-id="0453c-129">Segmentierungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="0453c-129">Chunking Protocol</span></span>

<span data-ttu-id="0453c-130">Der Segmentierungskanal definiert ein Protokoll, das den Start und das Ende einer Segmentreihe sowie die laufende Nummer jedes Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="0453c-130">The chunking channel defines a protocol that indicates the start and end of a series of chunks as well as the sequence number of each chunk.</span></span> <span data-ttu-id="0453c-131">Die folgenden drei Beispielnachrichten veranschaulichen die Start-, Segmentierungs- und Endnachricht mit Kommentaren, in denen jeweils die wichtigsten Aspekte der einzelnen Elemente beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0453c-131">The following three example messages demonstrate the start, chunk and end messages with comments that describe the key aspects of each.</span></span>

### <a name="start-message"></a><span data-ttu-id="0453c-132">Startnachricht</span><span class="sxs-lookup"><span data-stu-id="0453c-132">Start Message</span></span>

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
<!--Original message action is replaced with a chunking-specific action. -->
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>
<!--
Original message is assigned a unique id that is transmitted
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.
-->
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">
53f183ee-04aa-44a0-b8d3-e45224563109
</MessageId>
<!--
ChunkingStart header signals the start of a chunked message.
-->
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />
<!--
Original message action is transmitted in OriginalAction.
This is required to re-create the original message on the other side.
-->
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">
http://tempuri.org/ITestService/EchoStream
    </OriginalAction>
   <!--
    All original message headers are included here.
   -->
  </s:Header>
  <s:Body>
<!--
Chunking assumes this structure of Body content:
<element>
  <childelement>large data to be chunked<childelement>
</element>
The start message contains just <element> and <childelement> without
the data to be chunked.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

### <a name="chunk-message"></a><span data-ttu-id="0453c-133">Segmentierungsnachricht</span><span class="sxs-lookup"><span data-stu-id="0453c-133">Chunk Message</span></span>

```xml
<s:Envelope
  xmlns:a="http://www.w3.org/2005/08/addressing"
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
   <!--
    All chunking protocol messages have this action.
   -->
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
The sequence number of the chunk.
This number restarts at 1 with each new sequence of chunks.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      1096
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The chunked data is wrapped in a chunk element.
The encoding of this data (and the entire message)
depends on the encoder used. The chunking channel does not mandate an encoding.
-->
    <chunk xmlns="http://samples.microsoft.com/chunking">
kfSr2QcBlkHTvQ==
    </chunk>
  </s:Body>
</s:Envelope>
```

### <a name="end-message"></a><span data-ttu-id="0453c-134">Endnachricht</span><span class="sxs-lookup"><span data-stu-id="0453c-134">End Message</span></span>

```xml
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://samples.microsoft.com/chunkingAction
    </a:Action>
<!--
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.
-->
    <MessageId s:mustUnderstand="1"
               xmlns="http://samples.microsoft.com/chunking">
      53f183ee-04aa-44a0-b8d3-e45224563109
    </MessageId>
<!--
ChunkingEnd header signals the end of a chunk sequence.
-->
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"
                 xmlns="http://samples.microsoft.com/chunking" />
<!--
ChunkingEnd messages have a sequence number.
-->
    <ChunkNumber s:mustUnderstand="1"
                 xmlns="http://samples.microsoft.com/chunking">
      79
    </ChunkNumber>
  </s:Header>
  <s:Body>
<!--
The ChunkingEnd message has the same <element><childelement> structure
as the ChunkingStart message.
-->
    <EchoStream xmlns="http://tempuri.org/">
      <stream />
    </EchoStream>
  </s:Body>
</s:Envelope>
```

## <a name="chunking-channel-architecture"></a><span data-ttu-id="0453c-135">Segmentierungskanalarchitektur</span><span class="sxs-lookup"><span data-stu-id="0453c-135">Chunking Channel Architecture</span></span>

<span data-ttu-id="0453c-136">Der Segmentierungskanal ist ein `IDuplexSessionChannel`, der im Allgemeinen der typischen Kanalarchitektur folgt.</span><span class="sxs-lookup"><span data-stu-id="0453c-136">The chunking channel is an `IDuplexSessionChannel` that, at a high level, follows the typical channel architecture.</span></span> <span data-ttu-id="0453c-137">Es gibt ein `ChunkingBindingElement`, das eine `ChunkingChannelFactory` und einen `ChunkingChannelListener` erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0453c-137">There is a `ChunkingBindingElement` that can build a `ChunkingChannelFactory` and a `ChunkingChannelListener`.</span></span> <span data-ttu-id="0453c-138">`ChunkingChannelFactory` erstellt auf Anforderung Instanzen von `ChunkingChannel`.</span><span class="sxs-lookup"><span data-stu-id="0453c-138">The `ChunkingChannelFactory` creates instances of `ChunkingChannel` when it is asked to.</span></span> <span data-ttu-id="0453c-139">`ChunkingChannelListener` erstellt Instanzen von `ChunkingChannel`, wenn ein neuer innerer Kanal akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-139">The `ChunkingChannelListener` creates instances of `ChunkingChannel` when a new inner channel is accepted.</span></span> <span data-ttu-id="0453c-140">Der `ChunkingChannel` selbst ist für das Senden und Empfangen von Nachrichten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="0453c-140">The `ChunkingChannel` itself is responsible for sending and receiving messages.</span></span>

<span data-ttu-id="0453c-141">Eine Ebene tiefer beruht `ChunkingChannel` für die Implementierung des Segmentierungsprotokolls auf mehreren Komponenten.</span><span class="sxs-lookup"><span data-stu-id="0453c-141">At the next level down, `ChunkingChannel` relies on several components to implement the chunking protocol.</span></span> <span data-ttu-id="0453c-142">Auf der Senderseite verwendet der Kanal einen benutzerdefinierten <xref:System.Xml.XmlDictionaryWriter>, den so genannten `ChunkingWriter`, der die eigentliche Segmentierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="0453c-142">On the send side, the channel uses a custom <xref:System.Xml.XmlDictionaryWriter> called `ChunkingWriter` that does the actual chunking.</span></span> <span data-ttu-id="0453c-143">`ChunkingWriter` verwendet den inneren Kanal direkt zum Senden von Segmenten.</span><span class="sxs-lookup"><span data-stu-id="0453c-143">`ChunkingWriter` uses the inner channel directly to send chunks.</span></span> <span data-ttu-id="0453c-144">Durch die Verwendung eines benutzerdefinierten `XmlDictionaryWriter` können Segmente versendet werden, während der große Text der ursprünglichen Nachricht geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-144">Using a custom `XmlDictionaryWriter` allows us to send out chunks as the large body of the original message is being written.</span></span> <span data-ttu-id="0453c-145">Dies bedeutet, dass nicht die gesamte ursprüngliche Nachricht gepuffert wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-145">This means we do not buffer the entire original message.</span></span>

![Diagramm, das die Architektur des Segmentierungs Kanals anzeigt.](./media/chunking-channel/chunking-channel-send.gif)

<span data-ttu-id="0453c-147">Auf der Empfängerseite ruft `ChunkingChannel` Nachrichten aus dem inneren Kanal ab und gibt sie an einen benutzerdefinierten <xref:System.Xml.XmlDictionaryReader>, den so genannten `ChunkingReader` weiter, der die ursprüngliche Nachricht wieder aus den eingehenden Segmenten zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="0453c-147">On the receive side, `ChunkingChannel` pulls messages from the inner channel and hands them to a custom <xref:System.Xml.XmlDictionaryReader> called `ChunkingReader`, which reconstitutes the original message from the incoming chunks.</span></span> <span data-ttu-id="0453c-148">`ChunkingChannel` bindet diesen `ChunkingReader` in einer benutzerdefinierten `Message`-Implementierung, der so genannten `ChunkingMessage`, ein und gibt diese Nachricht an die darüberliegende Schicht zurück.</span><span class="sxs-lookup"><span data-stu-id="0453c-148">`ChunkingChannel` wraps this `ChunkingReader` in a custom `Message` implementation called `ChunkingMessage` and returns this message to the layer above.</span></span> <span data-ttu-id="0453c-149">Diese Kombination aus `ChunkingReader` und `ChunkingMessage` ermöglicht die Desegmentierung des ursprünglichen Nachrichtentexts, während dieser von der darüberliegenden Schicht gelesen wird. Es ist also nicht erforderlich, den gesamten Text der ursprünglichen Nachricht zu puffern.</span><span class="sxs-lookup"><span data-stu-id="0453c-149">This combination of `ChunkingReader` and `ChunkingMessage` allows us to de-chunk the original message body as it is being read by the layer above instead of having to buffer the entire original message body.</span></span> <span data-ttu-id="0453c-150">`ChunkingReader` enthält eine Warteschlange, in der die eingehenden Segmente bis zu der maximal konfigurierbaren Anzahl gepufferter Segmente gepuffert werden.</span><span class="sxs-lookup"><span data-stu-id="0453c-150">`ChunkingReader` has a queue where it buffers incoming chunks up to a maximum configurable number of buffered chunks.</span></span> <span data-ttu-id="0453c-151">Wenn diese Obergrenze erreicht ist, wartet der Leser, bis Nachrichten durch die darüberliegende Schicht aus der Warteschlange abfließen (d.&#160;h. einfach durch Lesen aus dem ursprünglichen Nachrichtentext) oder bis das maximale Empfangs-Timeout erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="0453c-151">When this maximum limit is reached, the reader waits for messages to be drained from the queue by the layer above (that is, by just reading from the original message body) or until the maximum receive timeout is reached.</span></span>

![Diagramm, das die Architektur des Segmentierungs Kanals anzeigt.](./media/chunking-channel/chunking-channel-receive.gif)

## <a name="chunking-programming-model"></a><span data-ttu-id="0453c-153">Programmierungsmodell für die Segmentierung</span><span class="sxs-lookup"><span data-stu-id="0453c-153">Chunking Programming Model</span></span>

<span data-ttu-id="0453c-154">Dienstentwickler können angeben, welche Nachrichten segmentiert werden sollen, indem sie das Attribut `ChunkingBehavior` auf Vorgänge innerhalb des Vertrags anwenden.</span><span class="sxs-lookup"><span data-stu-id="0453c-154">Service developers can specify which messages are to be chunked by applying the `ChunkingBehavior` attribute to operations within the contract.</span></span> <span data-ttu-id="0453c-155">Das Attribut macht eine `AppliesTo`-Eigenschaft verfügbar, mit der der Entwickler angeben kann, ob sich die Segmentierung auf die Eingabenachricht, die Ausgabenachricht oder auf beides bezieht.</span><span class="sxs-lookup"><span data-stu-id="0453c-155">The attribute exposes an `AppliesTo` property that allows the developer to specify whether chunking applies to the input message, the output message or both.</span></span> <span data-ttu-id="0453c-156">Im folgenden Beispiel wird die Verwendung des `ChunkingBehavior`-Attributs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0453c-156">The following example shows the usage of `ChunkingBehavior` attribute:</span></span>

```csharp
[ServiceContract]
interface ITestService
{
    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.Both)]
    Stream EchoStream(Stream stream);

    [OperationContract]
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]
    Stream DownloadStream();

    [OperationContract(IsOneWay=true)]
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]
    void UploadStream(Stream stream);

}
```

<span data-ttu-id="0453c-157">Aus diesem Programmierungsmodell kompiliert `ChunkingBindingElement` eine Liste von Aktions-URIs, die die zu segmentierenden Nachrichten identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0453c-157">From this programming model, the `ChunkingBindingElement` compiles a list of action URIs that identify messages to be chunked.</span></span> <span data-ttu-id="0453c-158">Die Aktion der einzelnen ausgehenden Nachrichten wird mit dieser Liste verglichen, um zu bestimmen, ob die Nachricht segmentiert oder direkt gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0453c-158">The action of each outgoing message is compared against this list to determine if the message should be chunked or sent directly.</span></span>

## <a name="implementing-the-send-operation"></a><span data-ttu-id="0453c-159">Implementieren des Sendevorgangs</span><span class="sxs-lookup"><span data-stu-id="0453c-159">Implementing the Send Operation</span></span>

<span data-ttu-id="0453c-160">Allgemein gesagt überprüft der Sendevorgang zunächst, ob die ausgehende Nachricht segmentiert werden muss, und falls nicht, sendet sie die Nachricht direkt über den inneren Kanal.</span><span class="sxs-lookup"><span data-stu-id="0453c-160">At a high level, the Send operation first checks whether the outgoing message must be chunked and, if not, sends the message directly using the inner channel.</span></span>

<span data-ttu-id="0453c-161">Wenn die Nachricht segmentiert werden muss, erstellt Send einen neuen `ChunkingWriter` und ruft `WriteBodyContents` in der ausgehenden Nachricht auf, der sie diesen `ChunkingWriter` übergibt.</span><span class="sxs-lookup"><span data-stu-id="0453c-161">If the message must be chunked, Send creates a new `ChunkingWriter` and calls `WriteBodyContents` on the outgoing message passing it this `ChunkingWriter`.</span></span> <span data-ttu-id="0453c-162">Der `ChunkingWriter` nimmt dann die Nachrichtensegmentierung vor (dazu gehört das Kopieren der ursprünglichen Nachrichtenheaders in die Startsegmentnachricht) und sendet Segmente über den inneren Kanal.</span><span class="sxs-lookup"><span data-stu-id="0453c-162">The `ChunkingWriter` then does the message chunking (including copying original message headers to the start chunk message) and sends chunks using the inner channel.</span></span>

<span data-ttu-id="0453c-163">Hier einige Details, die beachtet werden sollten:</span><span class="sxs-lookup"><span data-stu-id="0453c-163">A few details worth noting:</span></span>

- <span data-ttu-id="0453c-164">Send ruft zunächst `ThrowIfDisposedOrNotOpened` auf, um sicherzustellen, dass `CommunicationState` geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0453c-164">Send first calls `ThrowIfDisposedOrNotOpened` to ensure the `CommunicationState` is opened.</span></span>

- <span data-ttu-id="0453c-165">Das Senden wird synchronisiert, sodass für die einzelnen Sitzungen jeweils nicht mehrere Nachrichten gleichzeitig gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0453c-165">Sending is synchronized so that only one message can be sent at a time for each session.</span></span> <span data-ttu-id="0453c-166">Es gibt einen `ManualResetEvent` namens `sendingDone`, der zurückgesetzt wird, wenn eine segmentierte Nachricht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-166">There is a `ManualResetEvent` named `sendingDone` that is reset when a chunked message is being sent.</span></span> <span data-ttu-id="0453c-167">Sobald die Endsegmentnachricht gesendet wurde, ist dieses Ereignis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0453c-167">Once the end chunk message is sent, this event is set.</span></span> <span data-ttu-id="0453c-168">Die Send-Methode wartet, bis dieses Ereignis festgelegt ist, bevor sie versucht, die ausgehende Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="0453c-168">The Send method waits for this event to be set before it tries to send the outgoing message.</span></span>

- <span data-ttu-id="0453c-169">Send sperrt `CommunicationObject.ThisLock`, um Änderungen am synchronisierten Zustand während des Sendens zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0453c-169">Send locks the `CommunicationObject.ThisLock` to prevent synchronized state changes while sending.</span></span> <span data-ttu-id="0453c-170">Weitere Informationen zu <xref:System.ServiceModel.Channels.CommunicationObject>-Zuständen und den Zustandsautomaten finden Sie in der <xref:System.ServiceModel.Channels.CommunicationObject>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="0453c-170">See the <xref:System.ServiceModel.Channels.CommunicationObject> documentation for more information about <xref:System.ServiceModel.Channels.CommunicationObject> states and state machine.</span></span>

- <span data-ttu-id="0453c-171">Der an Send übergebene Timeout dient als Timeout für den gesamten Sendevorgang, der das Senden aller Segmente umfasst.</span><span class="sxs-lookup"><span data-stu-id="0453c-171">The timeout passed to Send is used as the timeout for the entire send operation which includes sending all of the chunks.</span></span>

- <span data-ttu-id="0453c-172">Der benutzerdefinierte <xref:System.Xml.XmlDictionaryWriter>-Entwurf wurde ausgewählt, um zu vermeiden, dass der gesamte Text der ursprünglichen Nachricht gepuffert wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-172">The custom <xref:System.Xml.XmlDictionaryWriter> design was chosen to avoid buffering the entire original message body.</span></span> <span data-ttu-id="0453c-173">Wenn mithilfe von <xref:System.Xml.XmlDictionaryReader> ein `message.GetReaderAtBodyContents` für den Text verwendet würde, würde der gesamte Nachrichtentext gepuffert.</span><span class="sxs-lookup"><span data-stu-id="0453c-173">If we were to get an <xref:System.Xml.XmlDictionaryReader> on the body using `message.GetReaderAtBodyContents` the entire body would be buffered.</span></span> <span data-ttu-id="0453c-174">Stattdessen verfügen wir über ein benutzerdefiniertes <xref:System.Xml.XmlDictionaryWriter> , das an die Übergabe erfolgt `message.WriteBodyContents` .</span><span class="sxs-lookup"><span data-stu-id="0453c-174">Instead, we have a custom  <xref:System.Xml.XmlDictionaryWriter> that is passed to `message.WriteBodyContents`.</span></span> <span data-ttu-id="0453c-175">Wenn die Nachricht WriteBase64 beim Writer aufruft, fasst der Writer Segmente zu Nachrichten zusammen und sendet sie über den inneren Kanal.</span><span class="sxs-lookup"><span data-stu-id="0453c-175">As the message calls WriteBase64 on the writer, the writer packages up chunks into messages and sends them using the inner channel.</span></span> <span data-ttu-id="0453c-176">WriteBase64 blockiert, bis das Segment gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0453c-176">WriteBase64 blocks until the chunk is sent.</span></span>

## <a name="implementing-the-receive-operation"></a><span data-ttu-id="0453c-177">Implementieren des Empfangsvorgangs (Receive)</span><span class="sxs-lookup"><span data-stu-id="0453c-177">Implementing the Receive Operation</span></span>

<span data-ttu-id="0453c-178">Allgemein gesagt stellt der Empfangsvorgang (Receive) zunächst sicher, dass die eingehende Nachricht nicht `null` und dass ihre Aktion `ChunkingAction` lautet.</span><span class="sxs-lookup"><span data-stu-id="0453c-178">At a high level, the Receive operation first checks that the incoming message is not `null` and that its action is the `ChunkingAction`.</span></span> <span data-ttu-id="0453c-179">Wenn sie nicht beide Kriterien erfüllt, wird die Nachricht unverändert von Receive zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0453c-179">If it does not meet both criteria, the message is returned unchanged from Receive.</span></span> <span data-ttu-id="0453c-180">Andernfalls erstellt Receive einen neuen `ChunkingReader` und eine neue `ChunkingMessage`, die ihn umgibt (durch Aufrufen von `GetNewChunkingMessage`).</span><span class="sxs-lookup"><span data-stu-id="0453c-180">Otherwise, Receive creates a new `ChunkingReader` and a new `ChunkingMessage` wrapped around it (by calling `GetNewChunkingMessage`).</span></span> <span data-ttu-id="0453c-181">Vor der Rückgabe dieser neuen `ChunkingMessage` führt Receive mithilfe eines Threadpool-Threads `ReceiveChunkLoop` aus, wodurch wiederum `innerChannel.Receive` in einer Schleife aufgerufen wird und Segmente an `ChunkingReader` übergeben werden, bis die Endsegmentnachricht empfangen oder der Receive-Timeout erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-181">Before returning that new `ChunkingMessage`, Receive uses a threadpool thread to execute `ReceiveChunkLoop`, which calls `innerChannel.Receive` in a loop and hands off chunks to the `ChunkingReader` until the end chunk message is received or the receive timeout is hit.</span></span>

<span data-ttu-id="0453c-182">Hier einige Details, die beachtet werden sollten:</span><span class="sxs-lookup"><span data-stu-id="0453c-182">A few details worth noting:</span></span>

- <span data-ttu-id="0453c-183">Wie Send ruft auch Receive zunächst `ThrowIfDisposedOrNotOepned` auf, um sicherzustellen, dass `CommunicationState` geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0453c-183">Like Send, Receive first calls `ThrowIfDisposedOrNotOepned` to ensure the `CommunicationState` is Opened.</span></span>

- <span data-ttu-id="0453c-184">Auch Receive wird synchronisiert, sodass aus der Sitzung nicht mehrere Nachrichten gleichzeitig empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="0453c-184">Receive is also synchronized so that only one message can be received at a time from the session.</span></span> <span data-ttu-id="0453c-185">Dies ist besonders wichtig, da nach dem Empfang einer Startsegmentnachricht davon ausgegangen wird, dass alle anschließend empfangenen Nachrichten Segmente innerhalb dieser neuen Segmentsequenz sind, bis eine Endsegmentnachricht empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-185">This is especially important because once a start chunk message is received, all subsequent received messages are expected to be chunks within this new chunk sequence until an end chunk message is received.</span></span> <span data-ttu-id="0453c-186">Receive kann so lange keine Nachrichten mithilfe von Pull aus dem inneren Kanal übertragen, bis alle Segmente, die zu der Nachricht gehören, die momentan wieder aus ihren Segmenten zusammengesetzt wird, empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="0453c-186">Receive cannot pull messages from the inner channel until all chunks that belong to the message currently being de-chunked are received.</span></span> <span data-ttu-id="0453c-187">Um dies zu erreichen, verwendet Receive ein `ManualResetEvent` namens `currentMessageCompleted`, das beim Empfang der Endsegmentnachricht festgelegt und beim Empfang einer neuen Startsegmentnachricht zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-187">To accomplish this, Receive uses a `ManualResetEvent` named `currentMessageCompleted`, which is set when the end chunk message is received and reset when a new start chunk message is received.</span></span>

- <span data-ttu-id="0453c-188">Im Gegensatz zu Send verhindert Receive während des Empfangs keine Zustandsübergänge bei synchronisierten Zuständen.</span><span class="sxs-lookup"><span data-stu-id="0453c-188">Unlike Send, Receive does not prevent synchronized state transitions while receiving.</span></span> <span data-ttu-id="0453c-189">So kann beispielsweise Close während des Empfangs aufgerufen werden. Der Vorgang wartet dann, bis der ausstehende Empfang der ursprünglichen Nachricht abgeschlossen bzw. der angegebene Timeoutwert erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="0453c-189">For example, Close can be called while receiving and waits until the pending receive of the original message is completed or the specified timeout value is reached.</span></span>

- <span data-ttu-id="0453c-190">Der an Receive übergebene Timeout dient als Timeout für den gesamten Empfangsvorgang, der den Empfang aller Segmente umfasst.</span><span class="sxs-lookup"><span data-stu-id="0453c-190">The timeout passed to Receive is used as the timeout for the entire receive operation, which includes receiving all of the chunks.</span></span>

- <span data-ttu-id="0453c-191">Wenn die Schicht, die die Nachricht verwendet, den Nachrichtentext langsamer verwendet als Segmentnachrichten eintreffen, puffert `ChunkingReader` die eingehenden Segmente bis zu der von `ChunkingBindingElement.MaxBufferedChunks` angegebenen Obergrenze.</span><span class="sxs-lookup"><span data-stu-id="0453c-191">If the layer that consumes the message is consuming the message body at a rate lower than the rate of incoming chunk messages, the `ChunkingReader` buffers those incoming chunks up to the limit specified by `ChunkingBindingElement.MaxBufferedChunks`.</span></span> <span data-ttu-id="0453c-192">Nachdem dieser Grenzwert erreicht wurde, werden erst dann wieder Segmente mithilfe von Pull aus der unteren Schicht übertragen, wenn entweder ein gepuffertes Segment verwendet oder der Empfangs-Timeout erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="0453c-192">Once that limit is reached, no more chunks are pulled from the lower layer until either a buffered chunk is consumed or the receive timeout is reached.</span></span>

## <a name="communicationobject-overrides"></a><span data-ttu-id="0453c-193">CommunicationObject-Überschreibungen</span><span class="sxs-lookup"><span data-stu-id="0453c-193">CommunicationObject Overrides</span></span>

### <a name="onopen"></a><span data-ttu-id="0453c-194">OnOpen</span><span class="sxs-lookup"><span data-stu-id="0453c-194">OnOpen</span></span>

<span data-ttu-id="0453c-195">`OnOpen` ruft `innerChannel.Open` auf, um den inneren Kanal zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0453c-195">`OnOpen` calls `innerChannel.Open` to open the inner channel.</span></span>

### <a name="onclose"></a><span data-ttu-id="0453c-196">OnClose</span><span class="sxs-lookup"><span data-stu-id="0453c-196">OnClose</span></span>

<span data-ttu-id="0453c-197">`OnClose` legt zuerst `stopReceive` auf `true` fest, um zu signalisieren, dass der ausstehende`ReceiveChunkLoop` beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0453c-197">`OnClose` first sets `stopReceive` to `true` to signal the pending `ReceiveChunkLoop` to stop.</span></span> <span data-ttu-id="0453c-198">Er wartet dann auf das `receiveStopped` <xref:System.Threading.ManualResetEvent> , das festgelegt wird, wenn `ReceiveChunkLoop` beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-198">It then waits for the `receiveStopped` <xref:System.Threading.ManualResetEvent>, which is set when `ReceiveChunkLoop` stops.</span></span> <span data-ttu-id="0453c-199">Angenommen, `ReceiveChunkLoop` wird innerhalb des angegebenen Timeouts beendet, dann ruft `OnClose` mit dem restlichen Timeout `innerChannel.Close` auf.</span><span class="sxs-lookup"><span data-stu-id="0453c-199">Assuming the `ReceiveChunkLoop` stops within the specified timeout, `OnClose` calls `innerChannel.Close` with the remaining timeout.</span></span>

### <a name="onabort"></a><span data-ttu-id="0453c-200">OnAbort</span><span class="sxs-lookup"><span data-stu-id="0453c-200">OnAbort</span></span>

<span data-ttu-id="0453c-201">`OnAbort` ruft `innerChannel.Abort` auf, um den inneren Kanal abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="0453c-201">`OnAbort` calls `innerChannel.Abort` to abort the inner channel.</span></span> <span data-ttu-id="0453c-202">Wenn es einen ausstehenden `ReceiveChunkLoop` gibt, erhält diese eine Ausnahme vom ausstehenden `innerChannel.Receive`-Aufruf.</span><span class="sxs-lookup"><span data-stu-id="0453c-202">If there is a pending `ReceiveChunkLoop` it gets an exception from the pending `innerChannel.Receive` call.</span></span>

### <a name="onfaulted"></a><span data-ttu-id="0453c-203">OnFaulted</span><span class="sxs-lookup"><span data-stu-id="0453c-203">OnFaulted</span></span>

<span data-ttu-id="0453c-204">Der `ChunkingChannel` erfordert kein besonderes Verhalten, wenn der Kanal einen Fehler verursacht hat, sodass `OnFaulted` nicht überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-204">The `ChunkingChannel` does not require special behavior when the channel is faulted so `OnFaulted` is not overridden.</span></span>

## <a name="implementing-channel-factory"></a><span data-ttu-id="0453c-205">Implementieren einer Kanalfactory</span><span class="sxs-lookup"><span data-stu-id="0453c-205">Implementing Channel Factory</span></span>

<span data-ttu-id="0453c-206">Der `ChunkingChannelFactory` ist dafür zuständig, Instanzen von `ChunkingDuplexSessionChannel` zu erstellen und Zustandsübergänge an die innere Kanalfactory weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="0453c-206">The `ChunkingChannelFactory` is responsible for creating instances of `ChunkingDuplexSessionChannel` and for cascading state transitions to the inner channel factory.</span></span>

<span data-ttu-id="0453c-207">`OnCreateChannel` verwendet die innere Kanalfactory zur Erstellung eines inneren `IDuplexSessionChannel`-Kanals.</span><span class="sxs-lookup"><span data-stu-id="0453c-207">`OnCreateChannel` uses the inner channel factory to create an `IDuplexSessionChannel` inner channel.</span></span> <span data-ttu-id="0453c-208">Anschließend erstellt es einen neuen `ChunkingDuplexSessionChannel`, dem sie beim Empfang diesen inneren Kanal sowie die Liste der zu segmentierenden Nachrichtenaktionen und die maximale Anzahl der zu puffernden Segmente übergibt.</span><span class="sxs-lookup"><span data-stu-id="0453c-208">It then creates a new `ChunkingDuplexSessionChannel` passing it this inner channel along with the list of message actions to be chunked and the maximum number of chunks to buffer upon receive.</span></span> <span data-ttu-id="0453c-209">Die Liste der zu segmentierenden Nachrichtenaktionen und die maximale Anzahl der zu puffernden Segmente sind zwei Parameter, die im Konstruktor an `ChunkingChannelFactory` weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0453c-209">The list of message actions to be chunked and the maximum number of chunks to buffer are two parameters passed to `ChunkingChannelFactory` in its constructor.</span></span> <span data-ttu-id="0453c-210">Im Abschnitt über `ChunkingBindingElement` wird beschrieben, woher diese Werte kommen.</span><span class="sxs-lookup"><span data-stu-id="0453c-210">The section on `ChunkingBindingElement` describes where these values come from.</span></span>

<span data-ttu-id="0453c-211">`OnOpen`, `OnClose`, `OnAbort` und ihre asynchronen Entsprechungen rufen die entsprechende Zustandsübergangsmethode in der inneren Kanalfactory auf.</span><span class="sxs-lookup"><span data-stu-id="0453c-211">The `OnOpen`, `OnClose`, `OnAbort` and their asynchronous equivalents call the corresponding state transition method on the inner channel factory.</span></span>

## <a name="implementing-channel-listener"></a><span data-ttu-id="0453c-212">Implementieren eines Kanallisteners</span><span class="sxs-lookup"><span data-stu-id="0453c-212">Implementing Channel Listener</span></span>

<span data-ttu-id="0453c-213">Der `ChunkingChannelListener` ist ein Wrapper um einen inneren Kanallistener.</span><span class="sxs-lookup"><span data-stu-id="0453c-213">The `ChunkingChannelListener` is a wrapper around an inner channel listener.</span></span> <span data-ttu-id="0453c-214">Neben dem Delegieren von Aufrufen an diesen inneren Kanallistener besteht seine Hauptaufgabe darin, neue `ChunkingDuplexSessionChannels` um Kanäle zu legen, die aus dem inneren Kanallistener akzeptiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0453c-214">Its main function, besides delegate calls to that inner channel listener, is to wrap new `ChunkingDuplexSessionChannels` around channels accepted from the inner channel listener.</span></span> <span data-ttu-id="0453c-215">Dies erfolgt in `OnAcceptChannel` und `OnEndAcceptChannel`.</span><span class="sxs-lookup"><span data-stu-id="0453c-215">This is done in `OnAcceptChannel` and `OnEndAcceptChannel`.</span></span> <span data-ttu-id="0453c-216">Dem neu erstellten `ChunkingDuplexSessionChannel` wird der innere Kanal, zusammen mit den anderen, bereits beschriebenen Parametern, übergeben.</span><span class="sxs-lookup"><span data-stu-id="0453c-216">The newly created `ChunkingDuplexSessionChannel` is passed the inner channel along with the other parameters previously described.</span></span>

## <a name="implementing-binding-element-and-binding"></a><span data-ttu-id="0453c-217">Implementieren von Bindungselement und Bindung</span><span class="sxs-lookup"><span data-stu-id="0453c-217">Implementing Binding Element and Binding</span></span>

<span data-ttu-id="0453c-218">`ChunkingBindingElement` ist für das Erstellen der `ChunkingChannelFactory` und des `ChunkingChannelListener` verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="0453c-218">`ChunkingBindingElement` is responsible for creating the `ChunkingChannelFactory` and `ChunkingChannelListener`.</span></span> <span data-ttu-id="0453c-219">Der `ChunkingBindingElement` überprüft, ob T in `CanBuildChannelFactory` \<T> und `CanBuildChannelListener` \<T> vom Typ ist `IDuplexSessionChannel` (der einzige Kanal, der vom Segmentierungs Kanal unterstützt wird) und ob die anderen Bindungs Elemente der Bindung diesen Kanaltyp unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0453c-219">The `ChunkingBindingElement` checks whether T in `CanBuildChannelFactory`\<T> and `CanBuildChannelListener`\<T> is of type `IDuplexSessionChannel` (the only channel supported by the chunking channel) and that the other binding elements in the binding support this channel type.</span></span>

<span data-ttu-id="0453c-220">`BuildChannelFactory`\<T>prüft zunächst, ob der angeforderte Kanaltyp erstellt werden kann, und ruft anschließend eine Liste der zu segmentierenden Nachrichten Aktionen ab.</span><span class="sxs-lookup"><span data-stu-id="0453c-220">`BuildChannelFactory`\<T> first checks that the requested channel type can be built and then gets a list of message actions to be chunked.</span></span> <span data-ttu-id="0453c-221">Weitere Informationen finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0453c-221">For more information, see the following section.</span></span> <span data-ttu-id="0453c-222">Anschließend erstellt es einen neuen `ChunkingChannelFactory`, dem es die innere Kanalfactory (wie aus `context.BuildInnerChannelFactory<IDuplexSessionChannel>` zurückgegeben), die Liste der Nachrichtenaktionen und die maximale Anzahl der beim Empfang zu puffernden Segmente übergibt.</span><span class="sxs-lookup"><span data-stu-id="0453c-222">It then creates a new `ChunkingChannelFactory` passing it the inner channel factory (as returned from `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), the list of message actions, and the maximum number of chunks to buffer.</span></span> <span data-ttu-id="0453c-223">Die maximale Anzahl an Segmenten stammt aus einer Eigenschaft namens `MaxBufferedChunks`, die vom `ChunkingBindingElement` verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-223">The maximum number of chunks comes from a property called `MaxBufferedChunks` exposed by the `ChunkingBindingElement`.</span></span>

<span data-ttu-id="0453c-224">`BuildChannelListener<T>` hat zum Erstellen von `ChunkingChannelListener` und zur Übergabe an den inneren Kanallistener eine ähnliche Implementierung.</span><span class="sxs-lookup"><span data-stu-id="0453c-224">`BuildChannelListener<T>` has a similar implementation for creating `ChunkingChannelListener` and passing it the inner channel listener.</span></span>

<span data-ttu-id="0453c-225">In diesem Beispiel ist eine Beispielbindung namens `TcpChunkingBinding` enthalten.</span><span class="sxs-lookup"><span data-stu-id="0453c-225">There is an example binding included in this sample named `TcpChunkingBinding`.</span></span> <span data-ttu-id="0453c-226">Diese Bindung besteht aus zwei Bindungselementen: `TcpTransportBindingElement` und `ChunkingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="0453c-226">This binding consists of two binding elements: `TcpTransportBindingElement` and `ChunkingBindingElement`.</span></span> <span data-ttu-id="0453c-227">Die Bindung macht nicht nur die Eigenschaft `MaxBufferedChunks` verfügbar, sondern legt auch einige der `TcpTransportBindingElement`-Eigenschaften fest, wie beispielsweise `MaxReceivedMessageSize` (wird auf `ChunkingUtils.ChunkSize` + 100 KB für Header festgelegt).</span><span class="sxs-lookup"><span data-stu-id="0453c-227">In addition to exposing the `MaxBufferedChunks` property, the binding also sets some of the `TcpTransportBindingElement` properties such as `MaxReceivedMessageSize` (sets it to `ChunkingUtils.ChunkSize` + 100KB bytes for headers).</span></span>

<span data-ttu-id="0453c-228">`TcpChunkingBinding` implementiert außerdem `IBindingRuntimePreferences` und gibt den Wert true aus der `ReceiveSynchronously`-Methode zurück, was anzeigt, dass nur die synchronen Receive-Aufrufe implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="0453c-228">`TcpChunkingBinding` also implements `IBindingRuntimePreferences` and returns true from the `ReceiveSynchronously` method indicating that only the synchronous Receive calls are implemented.</span></span>

### <a name="determining-which-messages-to-chunk"></a><span data-ttu-id="0453c-229">Bestimmen der zu segmentierenden Nachrichten</span><span class="sxs-lookup"><span data-stu-id="0453c-229">Determining Which Messages To Chunk</span></span>

<span data-ttu-id="0453c-230">Der Segmentierungskanal segmentiert nur die Nachrichten, die über das `ChunkingBehavior`-Attribut identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="0453c-230">The chunking channel chunks only the messages identified through the `ChunkingBehavior` attribute.</span></span> <span data-ttu-id="0453c-231">Die `ChunkingBehavior`-Klasse implementiert `IOperationBehavior` und wird durch Aufrufen der `AddBindingParameter`-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="0453c-231">The `ChunkingBehavior` class implements `IOperationBehavior` and is implemented by calling the `AddBindingParameter` method.</span></span> <span data-ttu-id="0453c-232">In dieser Methode untersucht `ChunkingBehavior` den Wert dieser `AppliesTo`-Eigenschaft (`InMessage`, `OutMessage` oder beides), um zu bestimmen, welche Nachrichten segmentiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0453c-232">In this method, the `ChunkingBehavior` examines the value of its `AppliesTo` property (`InMessage`, `OutMessage` or both) to determine which messages should be chunked.</span></span> <span data-ttu-id="0453c-233">Anschließend ruft es die Aktion jeder diese Nachrichten ab (aus der Nachrichtenauflistung unter `OperationDescription`) und fügt sie einer Zeichenfolgenauflistung hinzu, die in einer Instanz von `ChunkingBindingParameter` enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0453c-233">It then gets the action of each of those messages (from the Messages collection on `OperationDescription`) and adds it to a string collection contained within an instance of `ChunkingBindingParameter`.</span></span> <span data-ttu-id="0453c-234">Anschließend wird dieser `ChunkingBindingParameter` der angegebenen `BindingParameterCollection` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0453c-234">It then adds this `ChunkingBindingParameter` to the provided `BindingParameterCollection`.</span></span>

<span data-ttu-id="0453c-235">Diese `BindingParameterCollection` wird innerhalb von `BindingContext` an die einzelnen Bindungselemente in der Bindung übergeben, wenn das betreffende Bindungselement die Kanalfactory oder den Kanallistener erstellt.</span><span class="sxs-lookup"><span data-stu-id="0453c-235">This `BindingParameterCollection` is passed inside the `BindingContext` to each binding element in the binding when that binding element builds the channel factory or the channel listener.</span></span> <span data-ttu-id="0453c-236">Die `ChunkingBindingElement` -Implementierung von `BuildChannelFactory<T>` und `BuildChannelListener<T>` ruft diese `ChunkingBindingParameter` aus den `BindingContext’` s ab `BindingParameterCollection` .</span><span class="sxs-lookup"><span data-stu-id="0453c-236">The `ChunkingBindingElement`'s implementation of `BuildChannelFactory<T>` and `BuildChannelListener<T>` pull this `ChunkingBindingParameter` out of the `BindingContext’`s `BindingParameterCollection`.</span></span> <span data-ttu-id="0453c-237">Die Auflistung der in `ChunkingBindingParameter` enthaltenen Aktionen wird anschließend an `ChunkingChannelFactory` oder `ChunkingChannelListener` übergeben, von wo aus sie wiederum an `ChunkingDuplexSessionChannel` übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="0453c-237">The collection of actions contained within the `ChunkingBindingParameter` is then passed to the `ChunkingChannelFactory` or `ChunkingChannelListener`, which in turn passes it to the `ChunkingDuplexSessionChannel`.</span></span>

## <a name="running-the-sample"></a><span data-ttu-id="0453c-238">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="0453c-238">Running the Sample</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0453c-239">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0453c-239">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="0453c-240">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="0453c-240">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="0453c-241">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0453c-241">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="0453c-242">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0453c-242">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="0453c-243">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0453c-243">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

5. <span data-ttu-id="0453c-244">Führen Sie zuerst Service.exe und dann Client.exe aus, und sehen Sie sich die Ausgabe in beiden Konsolenfenstern an.</span><span class="sxs-lookup"><span data-stu-id="0453c-244">Run Service.exe first, then run Client.exe and watch both console windows for output.</span></span>

<span data-ttu-id="0453c-245">Beim Ausführen des Beispiels sollte die Ausgabe wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="0453c-245">When running the sample, the following output is expected.</span></span>

<span data-ttu-id="0453c-246">Client:</span><span class="sxs-lookup"><span data-stu-id="0453c-246">Client:</span></span>

```console
Press enter when service is available

 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```

<span data-ttu-id="0453c-247">Server: </span><span class="sxs-lookup"><span data-stu-id="0453c-247">Server:</span></span>

```console
Service started, press enter to exit
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd
```
