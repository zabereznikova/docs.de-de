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
# <a name="types-of-rpc"></a>RPC-Typen

Als WCF-Entwickler (Windows Communication Foundation) sind Sie wahrscheinlich daran gewöhnt, sich mit den folgenden Arten von Remoteprozeduraufrufen (Remote Procedure Call, RPC) zu befassen:

- Anfrage/Antwort
- Duplex:
  - Einwegduplex mit Sitzung
  - Vollduplex mit Sitzung
- Unidirektional

Es ist möglich, diese RPC-Typen ziemlich natürlich zu bestehenden gRPC-Konzepten zu zuordnen. In diesem Kapitel werden die einzelnen Bereiche nacheinander behandelt. [In Kapitel 5](migrate-wcf-to-grpc.md) werden ähnliche Beispiele eingehender untersucht.

| WCF | gRPC |
| --- | ---- |
| Regelmäßige Anfrage/Antwort | Unäroperatoren |
| Duplexdienst mit Sitzung über eine Clientrückrufschnittstelle | Server-Streaming |
| Vollduplex-Service mit Sitzung | Bidirektionales Streaming |
| Einweg-Operationen | Client-Streaming |

## <a name="requestreply"></a>Anfrage/Antwort

Verwenden Sie für einfache Anforderungs-/Antwortmethoden, die kleine Datenmengen aufnehmen und zurückgeben, das einfachste gRPC-Muster, das unäre RPC.

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

Wie Sie sehen können, ähnelt die Implementierung einer gRPC-Unary RPC-Dienstmethode der Implementierung eines WCF-Vorgangs. Der Unterschied besteht darin, dass Sie mit gRPC eine Basisklassenmethode überschreiben, anstatt eine Schnittstelle zu implementieren. Auf dem Server geben gRPC-Basismethoden immer zurück, <xref:System.Threading.Tasks.Task%601>obwohl der Client sowohl asynchrone als auch blockierende Methoden zum Aufrufen des Dienstes bereitstellt.

## <a name="wcf-duplex-one-way-to-client"></a>WCF-Duplex, eine Möglichkeit zum Client

WCF-Anwendungen (mit bestimmten Bindungen) können eine dauerhafte Verbindung zwischen Client und Server herstellen. Der Server kann mithilfe einer in der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Eigenschaft angegebenen *Rückrufschnittstelle* asynchron Daten an den Client senden, bis die Verbindung geschlossen wird.

gRPC-Dienste bieten ähnliche Funktionen mit Nachrichtenstreams. Streams werden in Bezug auf die Implementierung nicht *genau* WCF-Duplexdiensten zugeordnet, aber Sie können die gleichen Ergebnisse erzielen.

### <a name="grpc-streaming"></a>gRPC-Streaming

gRPC unterstützt die Erstellung persistenter Streams von Client zu Server und von Server zu Client. Beide Streamtypen können gleichzeitig aktiv sein. Diese Fähigkeit wird als bidirektionales Streaming bezeichnet.

Sie können Streams für beliebige, asynchrone Nachrichten im Laufe der Zeit verwenden. Sie können sie auch zum Übergeben großer Datasets verwenden, die zu groß sind, um eine einzelne Anforderung oder Antwort zu generieren und zu senden.

Das folgende Beispiel zeigt eine Server-Streaming-RPC.

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

Dieser Serverstream kann von einer Clientanwendung aus verwendet werden, wie im folgenden Code gezeigt:

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
> Serverstreaming-RPCs sind nützlich für Dienste im Abonnementstil. Sie sind auch nützlich, um große Datasets zu senden, wenn es ineffizient oder unmöglich wäre, das gesamte Dataset im Arbeitsspeicher zu erstellen. Streaming-Antworten sind jedoch nicht so schnell `repeated` wie das Senden von Feldern in einer einzelnen Nachricht. Streaming sollte in der Regel nicht für kleine Datasets verwendet werden.

### <a name="differences-from-wcf"></a>Unterschiede zu WCF

Ein WCF-Duplexdienst verwendet eine Clientrückrufschnittstelle, die über mehrere Methoden verfügen kann. Ein gRPC-Server-Streaming-Dienst kann nachrichten nur über einen einzelnen Stream senden. Wenn Sie mehrere Methoden benötigen, verwenden Sie einen Nachrichtentyp mit [einem Feld "Einoder" oder eines Felds,](protobuf-any-oneof.md) um verschiedene Nachrichten zu senden, und schreiben Sie Code in den Client, um sie zu verarbeiten.

In WCF wird die [ServiceContract-Klasse](xref:System.ServiceModel.ServiceContractAttribute) mit der Sitzung beibehalten, bis die Verbindung geschlossen wird. Innerhalb der Sitzung können mehrere Methoden aufgerufen werden. In gRPC `Task` sollte die, die die Implementierungsmethode zurückgibt, erst beendet werden, wenn die Verbindung geschlossen wurde.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>WCF-Einweg-Operationen und gRPC-Client-Streaming

WCF bietet einseitige Vorgänge `[OperationContract(IsOneWay = true)]`(mit gekennzeichnet), die eine transportspezifische Bestätigung zurückgeben. gRPC-Dienstmethoden geben immer eine Antwort zurück, auch wenn sie leer ist. Der Client sollte immer auf diese Antwort warten. Für den "Fire-and-forget"-Stil der Nachrichtenübermittlung in gRPC können Sie einen Client-Streamingdienst erstellen.

### <a name="thing_logproto"></a>thing_log.proto

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

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

### <a name="thinglog-client-example"></a>ThingLog-Clientbeispiel

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

Sie können Client-Streaming-RPCs für Fire-and-Forget-Messaging verwenden, wie im vorherigen Beispiel gezeigt. Sie können sie auch zum Senden sehr großer Datasets an den Server verwenden. Die gleiche Warnung bezüglich der Leistung gilt: Für kleinere Datasets verwenden Sie `repeated` Felder in regulären Nachrichten.

## <a name="wcf-full-duplex-services"></a>WCF-Vollduplex-Services

Die WCF-Duplexbindung unterstützt mehrere einseitige Vorgänge sowohl auf der Dienstschnittstelle als auch auf der Clientrückrufschnittstelle. Diese Unterstützung ermöglicht fortlaufende Unterhaltungen zwischen Client und Server. gRPC unterstützt ähnliches bei bidirektionalen Streaming-RPCs, `stream` bei denen beide Parameter mit dem Modifikator markiert sind.

### <a name="chatproto"></a>chat.proto

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

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

Im vorherigen Beispiel können Sie sehen, dass die Implementierungsmethode sowohl einen Anforderungsstream (`IAsyncStreamReader<MessageRequest>`) als auch einen Antwortstream (`IServerStreamWriter<MessageResponse>`) empfängt. Die Methode kann Nachrichten lesen und schreiben, bis die Verbindung geschlossen wird.

### <a name="chatter-client"></a>Chatter-Client

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
>[VorherigeS](wcf-bindings.md)
>[Weiter](metadata.md)
