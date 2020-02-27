---
title: Migrieren von WCF-Duplex Diensten zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie verschiedene Arten von WCF-Duplex Diensten zu GrpC-Streamingdiensten migrieren.
ms.date: 09/02/2019
ms.openlocfilehash: 5737f02044ab9e4064f632164db764541a9c4d31
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628539"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="3f377-103">Migrieren von WCF-Duplexdiensten zu gRPC</span><span class="sxs-lookup"><span data-stu-id="3f377-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="3f377-104">Nachdem Sie sich nun mit den grundlegenden Konzepten vertraut machen, sehen Sie sich in diesem Abschnitt die komplizierteren *Streaming* -GrpC-Dienste an.</span><span class="sxs-lookup"><span data-stu-id="3f377-104">Now that you have a sense of the basic concepts, in this section, you'll look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="3f377-105">Es gibt mehrere Möglichkeiten, Duplex Dienste in Windows Communication Foundation (WCF) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f377-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="3f377-106">Einige Dienste werden vom Client initiiert und dann Daten vom Server gestreamt.</span><span class="sxs-lookup"><span data-stu-id="3f377-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="3f377-107">Andere Vollduplex Dienste können eine fortlaufende bidirektionale Kommunikation beinhalten, wie z. b. das klassische Rechner Beispiel in der WCF-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="3f377-107">Other full-duplex services might involve more ongoing two-way communication, like the classic Calculator example in the WCF documentation.</span></span> <span data-ttu-id="3f377-108">In diesem Kapitel werden zwei mögliche WCF Stock Ticker-Implementierungen verwendet und zu GrpC migriert: eine, die ein Server-Streaming-RPC verwendet, und eine andere, die ein bidirektionales Streaming von RPC verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f377-108">This chapter will take two possible WCF stock ticker implementations and migrate them to gRPC: one that uses a server streaming RPC and another one that uses a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="3f377-109">Server-Streaming-RPC</span><span class="sxs-lookup"><span data-stu-id="3f377-109">Server streaming RPC</span></span>

<span data-ttu-id="3f377-110">In der [Beispiellösung simplestockticker WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), simplestockeupticker, gibt es einen Duplex Dienst, für den der Client die Verbindung mit einer Liste von Aktien Symbolen startet, und der Server verwendet die *Rückruf Schnittstelle* , um Updates zu senden, sobald diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3f377-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, there's a duplex service for which the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="3f377-111">Der Client implementiert diese Schnittstelle, um auf Aufrufe vom Server zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="3f377-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="3f377-112">Die WCF-Lösung</span><span class="sxs-lookup"><span data-stu-id="3f377-112">The WCF solution</span></span>

<span data-ttu-id="3f377-113">Die WCF-Lösung wird als selbstgeh osteter net. TCP-Server in einem .NET Framework 4 implementiert. *x* -Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="3f377-113">The WCF solution is implemented as a self-hosted Net.TCP server in a .NET Framework 4.*x* console application.</span></span>

#### <a name="servicecontract"></a><span data-ttu-id="3f377-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="3f377-114">ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="3f377-115">Der Dienst verfügt über eine einzelne Methode ohne Rückgabetyp, da er die Rückruf Schnittstelle `ISimpleStockTickerCallback` verwendet, um Daten in Echtzeit an den Client zu senden.</span><span class="sxs-lookup"><span data-stu-id="3f377-115">The service has a single method with no return type because it uses the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="3f377-116">Die Rückruf Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f377-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="3f377-117">Sie finden die Implementierungen dieser Schnittstellen in der Lösung zusammen mit fasteten externen Abhängigkeiten, um Testdaten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3f377-117">You can find the implementations of these interfaces in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="3f377-118">GrpC-Streaming</span><span class="sxs-lookup"><span data-stu-id="3f377-118">gRPC streaming</span></span>

<span data-ttu-id="3f377-119">Der GrpC-Prozess für die Verarbeitung von Echtzeitdaten unterscheidet sich vom WCF-Prozess.</span><span class="sxs-lookup"><span data-stu-id="3f377-119">The gRPC process for handling real-time data is different from the WCF process.</span></span> <span data-ttu-id="3f377-120">Ein Client-zu-Server-Client kann einen permanenten Stream erstellen, der auf eingehende Nachrichten überwacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f377-120">A call from client to server can create a persistent stream, which can be monitored for messages that arrive asynchronously.</span></span> <span data-ttu-id="3f377-121">Trotz des Unterschieds können Datenströme eine intuitivere Methode zum Umgang mit diesen Daten sein und sind relevanter in der modernen Programmierung, die LINQ, reaktive Streams, funktionale Programmierung usw. unterstreicht.</span><span class="sxs-lookup"><span data-stu-id="3f377-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming, which emphasizes LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="3f377-122">Die Dienst Definition benötigt zwei Nachrichten: eine für die Anforderung und eine für den Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="3f377-122">The service definition needs two messages: one for the request and one for the stream.</span></span> <span data-ttu-id="3f377-123">Der Dienst gibt einen Datenstrom der `StockTickerUpdate` Nachricht mit dem Schlüsselwort `stream` in seiner `return` Deklaration zurück.</span><span class="sxs-lookup"><span data-stu-id="3f377-123">The service returns a stream of the `StockTickerUpdate` message with the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="3f377-124">Es wird empfohlen, dem Update eine `Timestamp` hinzuzufügen, um den genauen Zeitpunkt der Preisänderung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3f377-124">We recommend that you add a `Timestamp` to the update to show the exact time of the price change.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="3f377-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="3f377-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-simplestockticker"></a><span data-ttu-id="3f377-126">Implementieren von simplestockticker</span><span class="sxs-lookup"><span data-stu-id="3f377-126">Implement SimpleStockTicker</span></span>

<span data-ttu-id="3f377-127">Verwenden Sie die gefälschten `StockPriceSubscriber` aus dem WCF-Projekt, indem Sie die drei Klassen aus der `TraderSys.StockMarket`-Klassenbibliothek in eine neue .NET Standard-Klassenbibliothek in der Ziel Projekt Mappe kopieren.</span><span class="sxs-lookup"><span data-stu-id="3f377-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="3f377-128">Um die bewährten Methoden besser befolgen zu können, fügen Sie einen `Factory`-Typ hinzu, um Instanzen des IT-Diensts zu erstellen, und registrieren Sie die `IStockPriceSubscriberFactory` mit den ASP.net Core Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="3f377-128">To better follow best practices, add a `Factory` type to create instances of it, and register the `IStockPriceSubscriberFactory` with the ASP.NET Core dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="3f377-129">Die Factory-Implementierung</span><span class="sxs-lookup"><span data-stu-id="3f377-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="register-the-factory"></a><span data-ttu-id="3f377-130">Registrieren der Factory</span><span class="sxs-lookup"><span data-stu-id="3f377-130">Register the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="3f377-131">Diese Klasse kann jetzt zum Implementieren der GrpC-`StockTickerService`verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f377-131">This class can now be used to implement the gRPC `StockTickerService`.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="3f377-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="3f377-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors caused by broken connection, etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="3f377-133">Wie Sie sehen, gibt die-Deklaration in der `.proto`-Datei an, dass die-Methode einen Stream mit `StockTickerUpdate` Meldungen zurückgibt, gibt aber tatsächlich eine `Task`zurück.</span><span class="sxs-lookup"><span data-stu-id="3f377-133">As you can see, although the declaration in the `.proto` file says the method returns a stream of `StockTickerUpdate` messages, it actually returns a `Task`.</span></span> <span data-ttu-id="3f377-134">Die Erstellung des Datenstroms erfolgt über den generierten Code und die GrpC-Laufzeitbibliotheken, die den `IServerStreamWriter<StockTickerUpdate>` Antwortstream bereitstellen, der verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f377-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="3f377-135">Anders als bei einem WCF-Duplex Dienst, bei dem die Instanz der Dienstklasse aktiv bleibt, während die Verbindung geöffnet ist, verwendet der GrpC-Dienst die zurückgegebene Aufgabe, um den Dienst aktiv zu halten.</span><span class="sxs-lookup"><span data-stu-id="3f377-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned task to keep the service alive.</span></span> <span data-ttu-id="3f377-136">Die Aufgabe sollte erst abgeschlossen werden, wenn die Verbindung geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3f377-136">The task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="3f377-137">Der Dienst kann erkennen, wann die Verbindung vom Client geschlossen wurde, indem die `CancellationToken` des `ServerCallContext`verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="3f377-138">Eine einfache statische Methode, `AwaitCancellation`, wird verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, wenn das Token abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-138">A simple static method, `AwaitCancellation`, is used to create a task that completes when the token is canceled.</span></span>

<span data-ttu-id="3f377-139">Erhalten Sie in der `Subscribe`-Methode eine `StockPriceSubscriber`, und fügen Sie einen Ereignishandler hinzu, der in den Antwortstream schreibt.</span><span class="sxs-lookup"><span data-stu-id="3f377-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="3f377-140">Warten Sie dann, bis die Verbindung geschlossen wurde, bevor Sie die `subscriber` sofort verwerfen, um zu verhindern, dass Daten in den geschlossenen Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3f377-140">Then wait for the connection to be closed before immediately disposing the `subscriber` to prevent it from trying to write data to the closed stream.</span></span>

<span data-ttu-id="3f377-141">Die `WriteUpdateAsync`-Methode verfügt über einen `try`/`catch` Block, um alle Fehler zu behandeln, die auftreten können, wenn eine Nachricht in den Stream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when a message is written to the stream.</span></span> <span data-ttu-id="3f377-142">Diese Überlegungen sind bei persistenten Verbindungen über Netzwerke wichtig, die in jeder Millisekunde unterbrechen werden können, egal ob absichtlich oder aufgrund eines Fehlers an einem Ort.</span><span class="sxs-lookup"><span data-stu-id="3f377-142">This consideration is important in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="use-stocktickerservice-from-a-client-application"></a><span data-ttu-id="3f377-143">Verwenden von stocktickerservice aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="3f377-143">Use StockTickerService from a client application</span></span>

<span data-ttu-id="3f377-144">Führen Sie die gleichen Schritte im vorherigen Abschnitt aus, um eine Share able-Client Klassenbibliothek aus der `.proto`-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f377-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="3f377-145">Im Beispiel gibt es eine .net Core 3,0-Konsolenanwendung, die die Verwendung des-Clients veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3f377-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="3f377-146">Beispiel für „Program.cs“</span><span class="sxs-lookup"><span data-stu-id="3f377-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="3f377-147">In diesem Fall ist die `Subscribe`-Methode auf dem generierten Client nicht asynchron.</span><span class="sxs-lookup"><span data-stu-id="3f377-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="3f377-148">Der Stream wird sofort erstellt und verwendet, da seine `MoveNext`-Methode asynchron ist, und wenn er zum ersten Mal aufgerufen wird, wird er erst beendet, wenn die Verbindung aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="3f377-148">The stream is created and usable right away because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="3f377-149">Der Stream wird an eine asynchrone `DisplayAsync` Methode übermittelt.</span><span class="sxs-lookup"><span data-stu-id="3f377-149">The stream is passed to an asynchronous `DisplayAsync` method.</span></span> <span data-ttu-id="3f377-150">Die Anwendung wartet dann darauf, dass der Benutzer eine Taste drückt, und bricht dann die `DisplayAsync` Methode ab und wartet, bis die Aufgabe beendet ist, bevor Sie beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-150">The application then waits for the user to press a key, and then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="3f377-151">In diesem Code wird die C# neue 8 `using` Deklarations Syntax verwendet, um den Stream und den Kanal zu verwerfen, wenn die `Main`-Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-151">This code uses the new C# 8 `using` declaration syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="3f377-152">Es handelt sich um eine kleine Änderung, aber eine schöne Änderung, die Einzüge und leere Zeilen reduziert.</span><span class="sxs-lookup"><span data-stu-id="3f377-152">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="3f377-153">Verbrauchen des Streams</span><span class="sxs-lookup"><span data-stu-id="3f377-153">Consume the stream</span></span>

<span data-ttu-id="3f377-154">WCF verwendet Rückruf Schnittstellen, damit der Server Methoden direkt auf dem Client aufruft.</span><span class="sxs-lookup"><span data-stu-id="3f377-154">WCF uses callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="3f377-155">GrpC-Streams funktionieren anders.</span><span class="sxs-lookup"><span data-stu-id="3f377-155">gRPC streams work differently.</span></span> <span data-ttu-id="3f377-156">Der Client durchläuft den zurückgegebenen Stream und verarbeitet Nachrichten, so als ob Sie von einer lokalen Methode zurückgegeben wurden, die eine `IEnumerable`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f377-156">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="3f377-157">Der `IAsyncStreamReader<T>` Typ funktioniert ähnlich wie ein `IEnumerator<T>`.</span><span class="sxs-lookup"><span data-stu-id="3f377-157">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`.</span></span> <span data-ttu-id="3f377-158">Es gibt eine `MoveNext` Methode, die true zurückgibt, solange mehr Daten vorhanden sind, und eine `Current`-Eigenschaft, die den aktuellen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f377-158">There's a `MoveNext` method that returns true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="3f377-159">Der einzige Unterschied besteht darin, dass die `MoveNext`-Methode eine `Task<bool>` anstelle eines `bool`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f377-159">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="3f377-160">Die `ReadAllAsync`-Erweiterungsmethode umschließt den Stream in C# einem Standard-8-`IAsyncEnumerable`, der mit der neuen `await foreach`-Syntax verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f377-160">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="3f377-161">Für Entwickler, die reaktive Programmier Muster verwenden, zeigt der Abschnitt zu [Client Bibliotheken](client-libraries.md#iobservable) am Ende dieses Kapitels, wie eine Erweiterungsmethode und Klassen hinzugefügt werden, um `IAsyncStreamReader<T>` in einem `IObservable<T>`zu umschließen.</span><span class="sxs-lookup"><span data-stu-id="3f377-161">For developers using reactive programming patterns, the section on [client libraries](client-libraries.md#iobservable) at the end of this chapter shows how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>`.</span></span>

<span data-ttu-id="3f377-162">Achten Sie auch hier darauf, dass Sie aufgrund der Möglichkeit eines Netzwerk Fehlers und aufgrund der <xref:System.OperationCanceledException>, die unweigerlich ausgelöst werden, wenn der Code eine <xref:System.Threading.CancellationToken> verwendet, um die Schleife zu unterbrechen, Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="3f377-162">Again, be sure to catch exceptions here because of the possibility of network failure, and because of the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="3f377-163">Der `RpcException`-Typ enthält viele nützliche Informationen zu GrpC-Laufzeitfehlern, einschließlich der `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="3f377-163">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="3f377-164">Weitere Informationen finden Sie unter [ *Fehlerbehandlung* in Kapitel 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="3f377-164">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="3f377-165">Bidirektionales Streaming</span><span class="sxs-lookup"><span data-stu-id="3f377-165">Bidirectional streaming</span></span>

<span data-ttu-id="3f377-166">Ein WCF-Vollduplex Dienst ermöglicht asynchrones Echt Zeit Messaging in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="3f377-166">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="3f377-167">Im Server Streaming-Beispiel startet der Client eine Anforderung und empfängt dann einen Datenstrom von Updates.</span><span class="sxs-lookup"><span data-stu-id="3f377-167">In the server streaming example, the client starts a request and then receives a stream of updates.</span></span> <span data-ttu-id="3f377-168">Eine bessere Version dieses Dienstanbieter ermöglicht dem Client das Hinzufügen und Entfernen von Beständen aus der Liste, ohne ein neues Abonnement zu erstellen und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f377-168">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="3f377-169">Diese Funktionalität wurde in der Beispiel Projekt Mappe [fullstockticker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)implementiert.</span><span class="sxs-lookup"><span data-stu-id="3f377-169">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="3f377-170">Die `IFullStockTickerService`-Schnittstelle stellt drei Methoden bereit:</span><span class="sxs-lookup"><span data-stu-id="3f377-170">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="3f377-171">`Subscribe` startet die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3f377-171">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="3f377-172">`AddSymbol` fügt ein zu überwachendes Aktiensymbol hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f377-172">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="3f377-173">`RemoveSymbol` entfernt ein Symbol aus der überwachten Liste.</span><span class="sxs-lookup"><span data-stu-id="3f377-173">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="3f377-174">Die Rückruf Schnittstelle bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="3f377-174">The callback interface remains the same.</span></span>

<span data-ttu-id="3f377-175">Die Implementierung dieses Musters in GrpC ist weniger unkompliziert, da jetzt zwei Datenströme mit Nachrichten vorhanden sind, die übermittelt werden: eine vom Client zum Server und eine andere von Server zu Client.</span><span class="sxs-lookup"><span data-stu-id="3f377-175">Implementing this pattern in gRPC is less straightforward because there are now two streams of data with messages being passed: one from client to server and another from server to client.</span></span> <span data-ttu-id="3f377-176">Es ist nicht möglich, mehrere Methoden zu verwenden, um die Add-und Remove-Vorgänge zu implementieren. Sie können jedoch mehr als einen Typ von Nachrichten in einem einzigen Stream übergeben, indem Sie entweder den `Any` Typ oder das `oneof`-Schlüsselwort verwenden, das in [Kapitel 3](protobuf-any-oneof.md)behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="3f377-176">It isn't possible to use multiple methods to implement the add and remove operations, but you can pass more than one type of message on a single stream by using either the `Any` type or the `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="3f377-177">In einem Fall, in dem ein bestimmter Satz von Typen zulässig ist, ist `oneof` eine bessere Möglichkeit.</span><span class="sxs-lookup"><span data-stu-id="3f377-177">In a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="3f377-178">Verwenden Sie eine `ActionMessage`, die entweder eine `AddSymbolRequest` oder eine `RemoveSymbolRequest`enthalten kann:</span><span class="sxs-lookup"><span data-stu-id="3f377-178">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`:</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="3f377-179">Deklarieren Sie einen bidirektionalen Streamingdienst, der einen Stream von `ActionMessage` Meldungen annimmt:</span><span class="sxs-lookup"><span data-stu-id="3f377-179">Declare a bidirectional streaming service that takes a stream of `ActionMessage` messages:</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="3f377-180">Die Implementierung für diesen Dienst ähnelt der des vorherigen Beispiels, mit dem Unterschied, dass der erste Parameter der `Subscribe`-Methode jetzt ein `IAsyncStreamReader<ActionMessage>`ist, der zum Verarbeiten der `Add` und `Remove` Anforderungen verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="3f377-180">The implementation for this service is similar to that of the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests:</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors caused by broken connection, etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="3f377-181">Die `ActionMessage` Klasse, die von GrpC generiert wurde, stellt sicher, dass nur eine der `Add`-und `Remove`-Eigenschaften festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f377-181">The `ActionMessage` class that gRPC has generated guarantees that only one of the `Add` and `Remove` properties can be set.</span></span> <span data-ttu-id="3f377-182">Das Auffinden, welches nicht `null` ist, ist eine gültige Methode, um zu bestimmen, welcher Nachrichtentyp verwendet wird. es gibt jedoch eine bessere Möglichkeit.</span><span class="sxs-lookup"><span data-stu-id="3f377-182">Finding which one isn't `null` is a valid way to determine which type of message is used, but there's a better way.</span></span> <span data-ttu-id="3f377-183">Die Codegenerierung hat auch eine `enum ActionOneOfCase` in der `ActionMessage`-Klasse erstellt, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="3f377-183">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="3f377-184">Die-Eigenschaft `ActionCase` für das `ActionMessage`-Objekt kann mit einer `switch`-Anweisung verwendet werden, um zu bestimmen, welches Feld festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="3f377-184">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set:</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="3f377-185">Die `switch`-Anweisung verfügt über einen `default` Fall, der eine Warnung protokolliert, wenn ein unbekannter `ActionOneOfCase` Wert gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3f377-185">The `switch` statement has a `default` case that logs a warning if it encounters an unknown `ActionOneOfCase` value.</span></span> <span data-ttu-id="3f377-186">Dies kann hilfreich sein, um anzugeben, dass ein Client eine spätere Version der `.proto` Datei verwendet, die weitere Aktionen hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="3f377-186">This could be useful to indicate that a client is using a later version of the `.proto` file that has added more actions.</span></span> <span data-ttu-id="3f377-187">Dies ist ein Grund, warum die Verwendung eines `switch` besser ist als das Testen für `null` auf bekannten Feldern.</span><span class="sxs-lookup"><span data-stu-id="3f377-187">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="3f377-188">Verwenden von fullstocktickerservice aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="3f377-188">Use FullStockTickerService from a client application</span></span>

<span data-ttu-id="3f377-189">Es gibt eine einfache .net Core 3,0 WPF-Anwendung, die die Verwendung dieses komplexeren Clients veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3f377-189">There's a simple .NET Core 3.0 WPF application that demonstrates the use of this more complex client.</span></span> <span data-ttu-id="3f377-190">Sie finden die vollständige Anwendung auf [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="3f377-190">You can find the full application on [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="3f377-191">Der-Client wird in der `MainWindowViewModel`-Klasse verwendet, die eine Instanz des `FullStockTicker.FullStockTickerClient` Typs aus der Abhängigkeitsinjektion abruft:</span><span class="sxs-lookup"><span data-stu-id="3f377-191">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection:</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="3f377-192">Das von der `client.Subscribe()`-Methode zurückgegebene Objekt ist nun eine Instanz des GrpC-Bibliotheks Typs `AsyncDuplexStreamingCall<TRequest, TResponse>`, die eine `RequestStream` zum Senden von Anforderungen an den Server und eine `ResponseStream` zur Behandlung von Antworten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3f377-192">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="3f377-193">Der Anforderungs Datenstrom wird in einigen WPF-`ICommand` Methoden zum Hinzufügen und Entfernen von Symbolen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3f377-193">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="3f377-194">Legen Sie für jeden Vorgang das relevante Feld für ein `ActionMessage` Objekt fest:</span><span class="sxs-lookup"><span data-stu-id="3f377-194">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="3f377-195">Wenn Sie den Wert eines `oneof` Felds für eine Nachricht festlegen, werden automatisch alle Felder gelöscht, die zuvor festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="3f377-195">Setting a `oneof` field's value on a message automatically clears any fields that have been set previously.</span></span>

<span data-ttu-id="3f377-196">Der Stream der Antworten wird in einer `async` Methode behandelt.</span><span class="sxs-lookup"><span data-stu-id="3f377-196">The stream of responses is handled in an `async` method.</span></span> <span data-ttu-id="3f377-197">Der zurückgegebene `Task` wird aufbewahrt, wenn das Fenster geschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="3f377-197">The `Task` it returns is held to be disposed when the window is closed:</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-cleanup"></a><span data-ttu-id="3f377-198">Client Bereinigung</span><span class="sxs-lookup"><span data-stu-id="3f377-198">Client cleanup</span></span>

<span data-ttu-id="3f377-199">Wenn das Fenster geschlossen wird und das `MainWindowViewModel` verworfen wird (aus dem `Closed`-Ereignis von `MainWindow`), empfiehlt es sich, das `AsyncDuplexStreamingCall` Objekt ordnungsgemäß zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="3f377-199">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), we recommend that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="3f377-200">Insbesondere sollte die `CompleteAsync`-Methode des `RequestStream` aufgerufen werden, um den Stream auf dem Server ordnungsgemäß zu schließen.</span><span class="sxs-lookup"><span data-stu-id="3f377-200">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="3f377-201">Dieses Beispiel zeigt die `DisposeAsync`-Methode aus dem Sample View-Model:</span><span class="sxs-lookup"><span data-stu-id="3f377-201">This example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="3f377-202">Das Schließen von Anforderungs Datenströmen ermöglicht es dem Server, seine eigenen Ressourcen rechtzeitig freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3f377-202">Closing request streams enables the server to dispose of its own resources in a timely way.</span></span> <span data-ttu-id="3f377-203">Dadurch wird die Effizienz und Skalierbarkeit von Diensten verbessert und Ausnahmen verhindert.</span><span class="sxs-lookup"><span data-stu-id="3f377-203">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3f377-204">[Zurück](migrate-request-reply.md)
>[Weiter](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="3f377-204">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
