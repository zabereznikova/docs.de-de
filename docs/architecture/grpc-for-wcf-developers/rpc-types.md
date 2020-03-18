---
title: Typen von RPC - gRPC für WCF-Entwickler
description: Eine Überprüfung der von WCF unterstützten Arten von Remoteprozeduraufrufen und deren Entsprechungen in gRPC
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401784"
---
# <a name="types-of-rpc"></a><span data-ttu-id="1584c-103">RPC-Typen</span><span class="sxs-lookup"><span data-stu-id="1584c-103">Types of RPC</span></span>

<span data-ttu-id="1584c-104">Als WCF-Entwickler (Windows Communication Foundation) sind Sie wahrscheinlich daran gewöhnt, sich mit den folgenden Arten von Remoteprozeduraufrufen (Remote Procedure Call, RPC) zu befassen:</span><span class="sxs-lookup"><span data-stu-id="1584c-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="1584c-105">Anfrage/Antwort</span><span class="sxs-lookup"><span data-stu-id="1584c-105">Request/reply</span></span>
- <span data-ttu-id="1584c-106">Duplex:</span><span class="sxs-lookup"><span data-stu-id="1584c-106">Duplex:</span></span>
  - <span data-ttu-id="1584c-107">Einwegduplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="1584c-107">One-way duplex with session</span></span>
  - <span data-ttu-id="1584c-108">Vollduplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="1584c-108">Full duplex with session</span></span>
- <span data-ttu-id="1584c-109">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="1584c-109">One-way</span></span>

<span data-ttu-id="1584c-110">Es ist möglich, diese RPC-Typen ziemlich natürlich zu bestehenden gRPC-Konzepten zu zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1584c-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="1584c-111">In diesem Kapitel werden die einzelnen Bereiche nacheinander behandelt.</span><span class="sxs-lookup"><span data-stu-id="1584c-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="1584c-112">[In Kapitel 5](migrate-wcf-to-grpc.md) werden ähnliche Beispiele eingehender untersucht.</span><span class="sxs-lookup"><span data-stu-id="1584c-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="1584c-113">WCF</span><span class="sxs-lookup"><span data-stu-id="1584c-113">WCF</span></span> | <span data-ttu-id="1584c-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="1584c-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="1584c-115">Regelmäßige Anfrage/Antwort</span><span class="sxs-lookup"><span data-stu-id="1584c-115">Regular request/reply</span></span> | <span data-ttu-id="1584c-116">Unäroperatoren</span><span class="sxs-lookup"><span data-stu-id="1584c-116">Unary</span></span> |
| <span data-ttu-id="1584c-117">Duplexdienst mit Sitzung über eine Clientrückrufschnittstelle</span><span class="sxs-lookup"><span data-stu-id="1584c-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="1584c-118">Server-Streaming</span><span class="sxs-lookup"><span data-stu-id="1584c-118">Server streaming</span></span> |
| <span data-ttu-id="1584c-119">Vollduplex-Service mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="1584c-119">Full duplex service with session</span></span> | <span data-ttu-id="1584c-120">Bidirektionales Streaming</span><span class="sxs-lookup"><span data-stu-id="1584c-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="1584c-121">Einweg-Operationen</span><span class="sxs-lookup"><span data-stu-id="1584c-121">One-way operations</span></span> | <span data-ttu-id="1584c-122">Client-Streaming</span><span class="sxs-lookup"><span data-stu-id="1584c-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="1584c-123">Anfrage/Antwort</span><span class="sxs-lookup"><span data-stu-id="1584c-123">Request/reply</span></span>

<span data-ttu-id="1584c-124">Verwenden Sie für einfache Anforderungs-/Antwortmethoden, die kleine Datenmengen aufnehmen und zurückgeben, das einfachste gRPC-Muster, das unäre RPC.</span><span class="sxs-lookup"><span data-stu-id="1584c-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="1584c-125">Wie Sie sehen können, ähnelt die Implementierung einer gRPC-Unary RPC-Dienstmethode der Implementierung eines WCF-Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="1584c-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="1584c-126">Der Unterschied besteht darin, dass Sie mit gRPC eine Basisklassenmethode überschreiben, anstatt eine Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1584c-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="1584c-127">Auf dem Server geben gRPC-Basismethoden immer zurück, <xref:System.Threading.Tasks.Task%601>obwohl der Client sowohl asynchrone als auch blockierende Methoden zum Aufrufen des Dienstes bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1584c-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="1584c-128">WCF-Duplex, eine Möglichkeit zum Client</span><span class="sxs-lookup"><span data-stu-id="1584c-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="1584c-129">WCF-Anwendungen (mit bestimmten Bindungen) können eine dauerhafte Verbindung zwischen Client und Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="1584c-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="1584c-130">Der Server kann mithilfe einer in der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Eigenschaft angegebenen *Rückrufschnittstelle* asynchron Daten an den Client senden, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="1584c-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="1584c-131">gRPC-Dienste bieten ähnliche Funktionen mit Nachrichtenstreams.</span><span class="sxs-lookup"><span data-stu-id="1584c-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="1584c-132">Streams werden in Bezug auf die Implementierung nicht *genau* WCF-Duplexdiensten zugeordnet, aber Sie können die gleichen Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="1584c-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="1584c-133">gRPC-Streaming</span><span class="sxs-lookup"><span data-stu-id="1584c-133">gRPC streaming</span></span>

<span data-ttu-id="1584c-134">gRPC unterstützt die Erstellung persistenter Streams von Client zu Server und von Server zu Client.</span><span class="sxs-lookup"><span data-stu-id="1584c-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="1584c-135">Beide Streamtypen können gleichzeitig aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="1584c-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="1584c-136">Diese Fähigkeit wird als bidirektionales Streaming bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1584c-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="1584c-137">Sie können Streams für beliebige, asynchrone Nachrichten im Laufe der Zeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="1584c-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="1584c-138">Sie können sie auch zum Übergeben großer Datasets verwenden, die zu groß sind, um eine einzelne Anforderung oder Antwort zu generieren und zu senden.</span><span class="sxs-lookup"><span data-stu-id="1584c-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="1584c-139">Das folgende Beispiel zeigt eine Server-Streaming-RPC.</span><span class="sxs-lookup"><span data-stu-id="1584c-139">The following example shows a server-streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="1584c-140">Dieser Serverstream kann von einer Clientanwendung aus verwendet werden, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1584c-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="1584c-141">Serverstreaming-RPCs sind nützlich für Dienste im Abonnementstil.</span><span class="sxs-lookup"><span data-stu-id="1584c-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="1584c-142">Sie sind auch nützlich, um große Datasets zu senden, wenn es ineffizient oder unmöglich wäre, das gesamte Dataset im Arbeitsspeicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1584c-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="1584c-143">Streaming-Antworten sind jedoch nicht so schnell `repeated` wie das Senden von Feldern in einer einzelnen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1584c-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="1584c-144">Streaming sollte in der Regel nicht für kleine Datasets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1584c-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="1584c-145">Unterschiede zu WCF</span><span class="sxs-lookup"><span data-stu-id="1584c-145">Differences from WCF</span></span>

<span data-ttu-id="1584c-146">Ein WCF-Duplexdienst verwendet eine Clientrückrufschnittstelle, die über mehrere Methoden verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="1584c-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="1584c-147">Ein gRPC-Server-Streaming-Dienst kann nachrichten nur über einen einzelnen Stream senden.</span><span class="sxs-lookup"><span data-stu-id="1584c-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="1584c-148">Wenn Sie mehrere Methoden benötigen, verwenden Sie einen Nachrichtentyp mit [einem Feld "Einoder" oder eines Felds,](protobuf-any-oneof.md) um verschiedene Nachrichten zu senden, und schreiben Sie Code in den Client, um sie zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1584c-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="1584c-149">In WCF wird die [ServiceContract-Klasse](xref:System.ServiceModel.ServiceContractAttribute) mit der Sitzung beibehalten, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="1584c-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="1584c-150">Innerhalb der Sitzung können mehrere Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1584c-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="1584c-151">In gRPC `Task` sollte die, die die Implementierungsmethode zurückgibt, erst beendet werden, wenn die Verbindung geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1584c-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="1584c-152">WCF-Einweg-Operationen und gRPC-Client-Streaming</span><span class="sxs-lookup"><span data-stu-id="1584c-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="1584c-153">WCF bietet einseitige Vorgänge `[OperationContract(IsOneWay = true)]`(mit gekennzeichnet), die eine transportspezifische Bestätigung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1584c-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="1584c-154">gRPC-Dienstmethoden geben immer eine Antwort zurück, auch wenn sie leer ist.</span><span class="sxs-lookup"><span data-stu-id="1584c-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="1584c-155">Der Client sollte immer auf diese Antwort warten.</span><span class="sxs-lookup"><span data-stu-id="1584c-155">The client should always await that response.</span></span> <span data-ttu-id="1584c-156">Für den "Fire-and-forget"-Stil der Nachrichtenübermittlung in gRPC können Sie einen Client-Streamingdienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="1584c-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="1584c-157">thing_log.proto</span><span class="sxs-lookup"><span data-stu-id="1584c-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="1584c-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="1584c-158">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="1584c-159">ThingLog-Clientbeispiel</span><span class="sxs-lookup"><span data-stu-id="1584c-159">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="1584c-160">Sie können Client-Streaming-RPCs für Fire-and-Forget-Messaging verwenden, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1584c-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="1584c-161">Sie können sie auch zum Senden sehr großer Datasets an den Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="1584c-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="1584c-162">Die gleiche Warnung bezüglich der Leistung gilt: Für kleinere Datasets verwenden Sie `repeated` Felder in regulären Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="1584c-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="1584c-163">WCF-Vollduplex-Services</span><span class="sxs-lookup"><span data-stu-id="1584c-163">WCF full-duplex services</span></span>

<span data-ttu-id="1584c-164">Die WCF-Duplexbindung unterstützt mehrere einseitige Vorgänge sowohl auf der Dienstschnittstelle als auch auf der Clientrückrufschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1584c-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="1584c-165">Diese Unterstützung ermöglicht fortlaufende Unterhaltungen zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="1584c-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="1584c-166">gRPC unterstützt ähnliches bei bidirektionalen Streaming-RPCs, `stream` bei denen beide Parameter mit dem Modifikator markiert sind.</span><span class="sxs-lookup"><span data-stu-id="1584c-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="1584c-167">chat.proto</span><span class="sxs-lookup"><span data-stu-id="1584c-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="1584c-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="1584c-168">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="1584c-169">Im vorherigen Beispiel können Sie sehen, dass die Implementierungsmethode sowohl einen Anforderungsstream (`IAsyncStreamReader<MessageRequest>`) als auch einen Antwortstream (`IServerStreamWriter<MessageResponse>`) empfängt.</span><span class="sxs-lookup"><span data-stu-id="1584c-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="1584c-170">Die Methode kann Nachrichten lesen und schreiben, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="1584c-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="1584c-171">Chatter-Client</span><span class="sxs-lookup"><span data-stu-id="1584c-171">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="1584c-172">[VorherigeS](wcf-bindings.md)
>[Weiter](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="1584c-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
