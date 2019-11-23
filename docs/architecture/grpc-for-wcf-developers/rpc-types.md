---
title: RPC-GrpC-Typen für WCF-Entwickler
description: Eine Überprüfung der von WCF unterstützten Remote Prozedur Aufrufe und ihrer Entsprechungen in GrpC
ms.date: 09/02/2019
ms.openlocfilehash: 64375236da17c0aedbafe1cb441e72a144203358
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967270"
---
# <a name="types-of-rpc"></a><span data-ttu-id="6ffc8-103">RPC-Typen</span><span class="sxs-lookup"><span data-stu-id="6ffc8-103">Types of RPC</span></span>

<span data-ttu-id="6ffc8-104">Als Windows Communication Foundation (WCF)-Entwickler haben Sie wahrscheinlich die folgenden Typen von Remote Prozedur Aufruf (RPC) verwendet:</span><span class="sxs-lookup"><span data-stu-id="6ffc8-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of Remote Procedure Call (RPC):</span></span>

- <span data-ttu-id="6ffc8-105">Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="6ffc8-105">Request/Reply</span></span>
- <span data-ttu-id="6ffc8-106">Gelegene</span><span class="sxs-lookup"><span data-stu-id="6ffc8-106">Duplex:</span></span>
  - <span data-ttu-id="6ffc8-107">Unidirektionaler Duplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="6ffc8-107">One-way duplex with session</span></span>
  - <span data-ttu-id="6ffc8-108">Vollduplex Duplex mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="6ffc8-108">Full duplex with session</span></span>
- <span data-ttu-id="6ffc8-109">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="6ffc8-109">One-way</span></span>

<span data-ttu-id="6ffc8-110">Es ist möglich, diese RPC-Typen auf natürliche Weise vorhandenen GrpC-Konzepten zuzuordnen, und in diesem Kapitel werden die einzelnen Bereiche nacheinander behandelt.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts and this chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="6ffc8-111">Ähnliche Beispiele werden in [Kapitel 5](migrate-wcf-to-grpc.md)ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-111">Similar examples will be explored in much greater depth in [Chapter 5](migrate-wcf-to-grpc.md).</span></span>

| <span data-ttu-id="6ffc8-112">WCF</span><span class="sxs-lookup"><span data-stu-id="6ffc8-112">WCF</span></span> | <span data-ttu-id="6ffc8-113">gRPC</span><span class="sxs-lookup"><span data-stu-id="6ffc8-113">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="6ffc8-114">Reguläre Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="6ffc8-114">Regular request/reply</span></span> | <span data-ttu-id="6ffc8-115">Unär</span><span class="sxs-lookup"><span data-stu-id="6ffc8-115">Unary</span></span> |
| <span data-ttu-id="6ffc8-116">Duplex Dienst mit Sitzung mithilfe einer Client Rückruf Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ffc8-116">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="6ffc8-117">Server Streaming</span><span class="sxs-lookup"><span data-stu-id="6ffc8-117">Server streaming</span></span> |
| <span data-ttu-id="6ffc8-118">Vollduplex Dienst mit Sitzung</span><span class="sxs-lookup"><span data-stu-id="6ffc8-118">Full duplex service with session</span></span> | <span data-ttu-id="6ffc8-119">Bidirektionales Streaming</span><span class="sxs-lookup"><span data-stu-id="6ffc8-119">Bidirectional streaming</span></span> |
| <span data-ttu-id="6ffc8-120">Unidirektionale Vorgänge</span><span class="sxs-lookup"><span data-stu-id="6ffc8-120">One-way operations</span></span> | <span data-ttu-id="6ffc8-121">Client Streaming</span><span class="sxs-lookup"><span data-stu-id="6ffc8-121">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="6ffc8-122">Anforderung/Antwort</span><span class="sxs-lookup"><span data-stu-id="6ffc8-122">Request/reply</span></span>

<span data-ttu-id="6ffc8-123">Verwenden Sie für einfache Anforderung/Antwort-Methoden, die kleine Datenmengen verwenden und zurückgeben, das einfachste GrpC-Muster, den unären RPC.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-123">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="6ffc8-124">Wie Sie sehen können, ist das Implementieren einer Methode für die unäre RPC-Methode von GrpC sehr ähnlich wie das Implementieren eines WCF-Vorgangs, mit dem Unterschied, dass Sie mit GrpC eine Basisklassen Methode außer Kraft setzen, anstatt eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ffc8-124">As you can see, implementing a gRPC unary RPC service method is very similar to implementing a WCF operation, except that with gRPC you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="6ffc8-125">Beachten Sie, dass die GrpC-Basis Methoden auf dem Server immer eine <xref:System.Threading.Tasks.Task%601>zurückgeben, obwohl der Client sowohl Async-als auch Blockierungs Methoden zum Aufrufen des Dienstanbieter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-125">Note that on the server, gRPC base methods always return a <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="6ffc8-126">WCF Duplex, unidirektional zum Client</span><span class="sxs-lookup"><span data-stu-id="6ffc8-126">WCF duplex, one-way to client</span></span>

<span data-ttu-id="6ffc8-127">WCF-Anwendungen (mit bestimmten Bindungen) können eine permanente Verbindung zwischen Client und Server herstellen, und der Server kann Daten asynchron an den Client senden, bis die Verbindung geschlossen wird. dabei wird eine *Rückruf Schnittstelle* verwendet, die in der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-127">WCF applications (with certain bindings) can create a persistent connection between client and server, and the server can asynchronously send data to the client until the connection is closed, using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="6ffc8-128">GrpC-Dienste bieten eine ähnliche Funktionalität wie Nachrichtenströme.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-128">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="6ffc8-129">Streams werden im Hinblick auf die Implementierung nicht *exakt* den WCF-Duplex Diensten zugeordnet, aber es können dieselben Ergebnisse erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-129">Streams don't map *exactly* to WCF duplex services in terms of implementation, but the same results can be achieved.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6ffc8-130">GrpC-Streaming</span><span class="sxs-lookup"><span data-stu-id="6ffc8-130">gRPC streaming</span></span>

<span data-ttu-id="6ffc8-131">GrpC unterstützt die Erstellung von permanenten Datenströmen vom Client zum Server und vom Server zum Client.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-131">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="6ffc8-132">Beide Arten von Datenströmen können gleichzeitig aktiv sein. Dies wird als bidirektionales Streaming bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-132">Both types of stream may be active concurrently; this is called bidirectional streaming.</span></span> <span data-ttu-id="6ffc8-133">Streams können im Laufe der Zeit für willkürliche, asynchrone Nachrichten oder für das übergeben großer Datasets verwendet werden, die zu groß sind, um Sie in einer einzelnen Anforderung oder Antwort zu generieren und zu senden.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-133">Streams can be used for arbitrary, asynchronous messaging over time, or for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="6ffc8-134">Das folgende Beispiel zeigt ein Server-Streaming-RPC.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-134">The following example shows a server streaming RPC.</span></span>

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

<span data-ttu-id="6ffc8-135">Dieser Serverdaten Strom kann von einer Client Anwendung verwendet werden, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6ffc8-135">This server stream could be consumed from a client application as shown in the following code:</span></span>

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
> <span data-ttu-id="6ffc8-136">Server Streaming-RPCs sind für Dienste im Abonnement Stil und auch für das Senden sehr großer Datasets nützlich, wenn es ineffizient oder unmöglich wäre, das gesamte Dataset im Arbeitsspeicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-136">Server streaming RPCs are useful for subscription-style services, and also for sending very large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="6ffc8-137">Das Streamen von Antworten ist jedoch nicht so schnell wie das Senden `repeated` Felder in einer einzelnen Nachricht, sodass ein Regel Streaming nicht für kleine Datasets verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-137">However, streaming responses isn't as fast as sending `repeated` fields in a single message, so as a rule streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-to-wcf"></a><span data-ttu-id="6ffc8-138">Unterschiede zu WCF</span><span class="sxs-lookup"><span data-stu-id="6ffc8-138">Differences to WCF</span></span>

<span data-ttu-id="6ffc8-139">Ein WCF-Duplex Dienst verwendet eine Client Rückruf Schnittstelle, die mehrere Methoden aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-139">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="6ffc8-140">Ein GrpC Server-Streamingdienst kann nur Nachrichten über einen einzigen Stream senden.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-140">A gRPC server streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="6ffc8-141">Wenn Sie mehrere Methoden benötigen, verwenden Sie einen Nachrichtentyp mit einem [beliebigen Feld oder einem Feld](protobuf-any-oneof.md) , um verschiedene Nachrichten zu senden, und schreiben Sie Code im Client, um Sie zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-141">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="6ffc8-142">In WCF wird die [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) -Klasse mit der Sitzung aufrechterhalten, bis die Verbindung geschlossen wird, und innerhalb der Sitzung können mehrere Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-142">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed, and multiple methods may be called within the session.</span></span> <span data-ttu-id="6ffc8-143">In GrpC sollten die `Task`, die von der Implementierungsmethode zurückgegeben werden, erst abgeschlossen werden, wenn die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-143">In gRPC, the `Task` returned by the implementation method shouldn't complete until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="6ffc8-144">Unidirektionale WCF-Vorgänge und GrpC-Client Streaming</span><span class="sxs-lookup"><span data-stu-id="6ffc8-144">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="6ffc8-145">WCF stellt unidirektionale Vorgänge (mit `[OperationContract(IsOneWay = true)]`gekennzeichnet) bereit, die eine Transport spezifische Bestätigung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-145">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="6ffc8-146">GrpC-Dienst Methoden geben immer eine Antwort zurück, auch wenn Sie leer ist, und der Client sollte immer auf diese Antwort warten.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-146">gRPC service methods always return a response, even if it's empty, and the client should always await that response.</span></span> <span data-ttu-id="6ffc8-147">Für "Fire-and-Forget"-Messaging in GrpC können Sie einen clientstreamingdienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-147">For "fire-and-forget" style messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="6ffc8-148">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="6ffc8-148">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="6ffc8-149">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="6ffc8-149">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="6ffc8-150">Thinglog-Client Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ffc8-150">ThingLog client example</span></span>

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

<span data-ttu-id="6ffc8-151">Auch hier können Client Streaming-RPCs für das Fire-and-Forget-Messaging verwendet werden, wie im vorherigen Beispiel gezeigt, aber auch für das Senden sehr großer Datasets an den Server.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-151">Again, client streaming RPCs can be used for fire-and-forget messaging as shown in the previous example, but also for sending very large datasets to the server.</span></span> <span data-ttu-id="6ffc8-152">Dieselbe Warnung bezüglich der Leistung gilt für kleinere Datasets: Verwenden Sie `repeated` Felder in regulären Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-152">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="6ffc8-153">WCF-Vollduplex Dienste</span><span class="sxs-lookup"><span data-stu-id="6ffc8-153">WCF full duplex services</span></span>

<span data-ttu-id="6ffc8-154">Die WCF-Duplex Bindung unterstützt mehrere unidirektionale Vorgänge sowohl für die Dienst Schnittstelle als auch für die Client Rückruf Schnittstelle, sodass laufende Konversationen zwischen Client und Server möglich sind.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-154">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface, allowing ongoing conversations between client and server.</span></span> <span data-ttu-id="6ffc8-155">GrpC unterstützt ähnliche Funktionen wie bidirektionale Streaming-RPCs, bei denen beide Parameter mit dem `stream`-Modifizierer markiert sind.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-155">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="6ffc8-156">Chat. proto</span><span class="sxs-lookup"><span data-stu-id="6ffc8-156">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="6ffc8-157">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="6ffc8-157">ChatterService.cs</span></span>

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

<span data-ttu-id="6ffc8-158">Im vorherigen Beispiel können Sie sehen, dass die Implementierungsmethode sowohl einen Anforderungs Datenstrom (`IAsyncStreamReader<MessageRequest>`) als auch einen Antwortstream (`IServerStreamWriter<MessageResponse>`) empfängt und Nachrichten lesen und schreiben kann, bis die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-158">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`), and can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="6ffc8-159">Chatter-Client</span><span class="sxs-lookup"><span data-stu-id="6ffc8-159">Chatter client</span></span>

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
><span data-ttu-id="6ffc8-160">[Zurück](wcf-bindings.md)
>[Weiter](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-160">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
