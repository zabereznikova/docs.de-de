---
title: RPC-GrpC-Typen für WCF-Entwickler
description: Eine Überprüfung der von WCF unterstützten Remote Prozedur Aufrufe und ihrer Entsprechungen in GrpC
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675154"
---
# <a name="types-of-rpc"></a><span data-ttu-id="139ae-103">RPC-Typen</span><span class="sxs-lookup"><span data-stu-id="139ae-103">Types of RPC</span></span>

<span data-ttu-id="139ae-104">Als Windows Communication Foundation (WCF)-Entwickler haben Sie wahrscheinlich die folgenden Typen von Remote Prozedur Aufruf (RPC) verwendet:</span><span class="sxs-lookup"><span data-stu-id="139ae-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="139ae-105">Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="139ae-105">Request/reply</span></span>
- <span data-ttu-id="139ae-106">Gelegene</span><span class="sxs-lookup"><span data-stu-id="139ae-106">Duplex:</span></span>
  - <span data-ttu-id="139ae-107">Unidirektionaler Duplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="139ae-107">One-way duplex with session</span></span>
  - <span data-ttu-id="139ae-108">Vollduplex Duplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="139ae-108">Full duplex with session</span></span>
- <span data-ttu-id="139ae-109">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="139ae-109">One-way</span></span>

<span data-ttu-id="139ae-110">Es ist möglich, diese RPC-Typen den vorhandenen GrpC-Konzepten relativ natürlich zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="139ae-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="139ae-111">In diesem Kapitel werden die einzelnen Bereiche im einzelnen erläutert.</span><span class="sxs-lookup"><span data-stu-id="139ae-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="139ae-112">In [Kapitel 5](migrate-wcf-to-grpc.md) werden ähnliche Beispiele ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="139ae-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="139ae-113">WCF</span><span class="sxs-lookup"><span data-stu-id="139ae-113">WCF</span></span> | <span data-ttu-id="139ae-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="139ae-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="139ae-115">Reguläre Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="139ae-115">Regular request/reply</span></span> | <span data-ttu-id="139ae-116">Unäroperatoren</span><span class="sxs-lookup"><span data-stu-id="139ae-116">Unary</span></span> |
| <span data-ttu-id="139ae-117">Duplex Dienst mit Sitzung mithilfe einer Client Rückruf Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="139ae-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="139ae-118">Server Streaming</span><span class="sxs-lookup"><span data-stu-id="139ae-118">Server streaming</span></span> |
| <span data-ttu-id="139ae-119">Vollduplex Dienst mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="139ae-119">Full duplex service with session</span></span> | <span data-ttu-id="139ae-120">Bidirektionales Streaming</span><span class="sxs-lookup"><span data-stu-id="139ae-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="139ae-121">Unidirektionale Vorgänge</span><span class="sxs-lookup"><span data-stu-id="139ae-121">One-way operations</span></span> | <span data-ttu-id="139ae-122">Client Streaming</span><span class="sxs-lookup"><span data-stu-id="139ae-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="139ae-123">Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="139ae-123">Request/reply</span></span>

<span data-ttu-id="139ae-124">Verwenden Sie für einfache Anforderung/Antwort-Methoden, die kleine Datenmengen verwenden und zurückgeben, das einfachste GrpC-Muster, den unären RPC.</span><span class="sxs-lookup"><span data-stu-id="139ae-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="139ae-125">Wie Sie sehen können, ähnelt das Implementieren einer Methode des unären Dienst-RPC-dienstanzvorgangs der Implementierung eines WCF-Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="139ae-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="139ae-126">Der Unterschied besteht darin, dass Sie mit GrpC eine Basisklassen Methode außer Kraft setzen, anstatt eine Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="139ae-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="139ae-127">Auf dem Server geben die GrpC-Basis Methoden immer <xref:System.Threading.Tasks.Task%601>zurück, obwohl der Client sowohl Async-als auch Blockierungs Methoden zum Aufrufen des Dienstanbieter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="139ae-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="139ae-128">WCF Duplex, eine Möglichkeit zum Client</span><span class="sxs-lookup"><span data-stu-id="139ae-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="139ae-129">WCF-Anwendungen (mit bestimmten Bindungen) können eine permanente Verbindung zwischen Client und Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="139ae-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="139ae-130">Der Server kann Daten asynchron an den Client senden, bis die Verbindung geschlossen wurde, indem er eine *Rückruf Schnittstelle* verwendet, die in der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="139ae-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="139ae-131">GrpC-Dienste bieten eine ähnliche Funktionalität wie Nachrichtenströme.</span><span class="sxs-lookup"><span data-stu-id="139ae-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="139ae-132">Streams werden in Bezug auf die Implementierung nicht *exakt* den WCF-Duplex Diensten zugeordnet, aber Sie können dieselben Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="139ae-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="139ae-133">GrpC-Streaming</span><span class="sxs-lookup"><span data-stu-id="139ae-133">gRPC streaming</span></span>

<span data-ttu-id="139ae-134">GrpC unterstützt die Erstellung von permanenten Datenströmen vom Client zum Server und vom Server zum Client.</span><span class="sxs-lookup"><span data-stu-id="139ae-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="139ae-135">Beide Arten von Datenströmen können gleichzeitig aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="139ae-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="139ae-136">Diese Fähigkeit wird als bidirektionales Streaming bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="139ae-136">This ability is called bidirectional streaming.</span></span> 

<span data-ttu-id="139ae-137">Sie können Datenströme für beliebiges, asynchrones Messaging im Lauf der Zeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="139ae-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="139ae-138">Oder Sie können Sie verwenden, um große Datasets zu übergeben, die zu groß sind, um Sie in einer einzelnen Anforderung oder Antwort zu generieren und zu senden.</span><span class="sxs-lookup"><span data-stu-id="139ae-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="139ae-139">Das folgende Beispiel zeigt ein Server-Streaming-RPC.</span><span class="sxs-lookup"><span data-stu-id="139ae-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="139ae-140">Dieser Serverdaten Strom kann von einer Client Anwendung verwendet werden, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="139ae-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="139ae-141">RPCs mit Server Streaming sind für Dienste im Abonnement Stil nützlich.</span><span class="sxs-lookup"><span data-stu-id="139ae-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="139ae-142">Sie sind auch nützlich, um große Datasets zu senden, wenn es ineffizient oder unmöglich wäre, das gesamte Dataset im Arbeitsspeicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="139ae-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="139ae-143">Das Streamen von Antworten ist jedoch nicht so schnell wie das Senden `repeated` Felder in einer einzelnen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="139ae-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="139ae-144">Als Regel sollte Streaming nicht für kleine Datasets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="139ae-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="139ae-145">Unterschiede zu WCF</span><span class="sxs-lookup"><span data-stu-id="139ae-145">Differences from WCF</span></span>

<span data-ttu-id="139ae-146">Ein WCF-Duplex Dienst verwendet eine Client Rückruf Schnittstelle, die mehrere Methoden aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="139ae-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="139ae-147">Ein GrpC-Server-Streamingdienst kann nur Nachrichten über einen einzigen Stream senden.</span><span class="sxs-lookup"><span data-stu-id="139ae-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="139ae-148">Wenn Sie mehrere Methoden benötigen, verwenden Sie einen Nachrichtentyp mit einem [beliebigen Feld oder einem Feld](protobuf-any-oneof.md) , um verschiedene Nachrichten zu senden, und schreiben Sie Code im Client, um Sie zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="139ae-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="139ae-149">In WCF wird die [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) -Klasse mit der Sitzung aufrechterhalten, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="139ae-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="139ae-150">Innerhalb der Sitzung können mehrere Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="139ae-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="139ae-151">In GrpC sollten die `Task`, die von der Implementierungsmethode zurückgegeben werden, erst beendet werden, wenn die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="139ae-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="139ae-152">Unidirektionale WCF-Vorgänge und GrpC-Client Streaming</span><span class="sxs-lookup"><span data-stu-id="139ae-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="139ae-153">WCF stellt unidirektionale Vorgänge (mit `[OperationContract(IsOneWay = true)]`gekennzeichnet) bereit, die eine Transport spezifische Bestätigung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="139ae-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="139ae-154">GrpC-Dienst Methoden geben immer eine Antwort zurück, auch wenn Sie leer ist.</span><span class="sxs-lookup"><span data-stu-id="139ae-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="139ae-155">Der Client sollte immer auf diese Antwort warten.</span><span class="sxs-lookup"><span data-stu-id="139ae-155">The client should always await that response.</span></span> <span data-ttu-id="139ae-156">Für den Nachrichten Stil "Fire-and-Forget" in GrpC können Sie einen clientstreamingdienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="139ae-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="139ae-157">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="139ae-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="139ae-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="139ae-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="139ae-159">Thinglog-Client Beispiel</span><span class="sxs-lookup"><span data-stu-id="139ae-159">ThingLog client example</span></span>

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

<span data-ttu-id="139ae-160">Sie können Client Streaming-RPCs für das Fire-and-Forget-Messaging verwenden, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="139ae-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="139ae-161">Sie können Sie auch verwenden, um sehr große Datasets an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="139ae-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="139ae-162">Dieselbe Warnung bezüglich der Leistung gilt für kleinere Datasets: Verwenden Sie `repeated` Felder in regulären Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="139ae-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="139ae-163">WCF-Vollduplex Dienste</span><span class="sxs-lookup"><span data-stu-id="139ae-163">WCF full-duplex services</span></span>

<span data-ttu-id="139ae-164">Die WCF-Duplex Bindung unterstützt mehrere unidirektionale Vorgänge sowohl für die Dienst Schnittstelle als auch für die Client Rückruf Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="139ae-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="139ae-165">Diese Unterstützung ermöglicht laufende Konversationen zwischen Client und Server.</span><span class="sxs-lookup"><span data-stu-id="139ae-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="139ae-166">GrpC unterstützt ähnliche Funktionen wie bidirektionale Streaming-RPCs, bei denen beide Parameter mit dem `stream`-Modifizierer markiert sind.</span><span class="sxs-lookup"><span data-stu-id="139ae-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="139ae-167">Chat. proto</span><span class="sxs-lookup"><span data-stu-id="139ae-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="139ae-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="139ae-168">ChatterService.cs</span></span>

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

<span data-ttu-id="139ae-169">Im vorherigen Beispiel können Sie sehen, dass die Implementierungsmethode sowohl einen Anforderungs Datenstrom (`IAsyncStreamReader<MessageRequest>`) als auch einen Antwortstream (`IServerStreamWriter<MessageResponse>`) empfängt.</span><span class="sxs-lookup"><span data-stu-id="139ae-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="139ae-170">Die-Methode kann Nachrichten lesen und schreiben, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="139ae-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="139ae-171">Chatter-Client</span><span class="sxs-lookup"><span data-stu-id="139ae-171">Chatter client</span></span>

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
><span data-ttu-id="139ae-172">[Zurück](wcf-bindings.md)
>[Weiter](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="139ae-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
