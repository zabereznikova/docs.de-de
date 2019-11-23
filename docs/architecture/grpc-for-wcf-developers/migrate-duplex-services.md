---
title: Migrieren von WCF-Duplex Diensten zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie verschiedene Arten von WCF Duplex Service zu GrpC-Streamingdiensten migrieren.
ms.date: 09/02/2019
ms.openlocfilehash: e2248df20e5c2d8f96055d42ba684749251154bd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971878"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="8f914-103">Migrieren von WCF-Duplexdiensten zu gRPC</span><span class="sxs-lookup"><span data-stu-id="8f914-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="8f914-104">Nun, da die grundlegenden Konzepte vorhanden sind, werden in diesem Abschnitt die komplizierteren *Streaming* -GrpC-Dienste erläutert.</span><span class="sxs-lookup"><span data-stu-id="8f914-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="8f914-105">Es gibt mehrere Möglichkeiten, Duplex Dienste in Windows Communication Foundation (WCF) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f914-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="8f914-106">Einige Dienste werden vom Client initiiert und dann Daten vom Server gestreamt.</span><span class="sxs-lookup"><span data-stu-id="8f914-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="8f914-107">Andere Vollduplex Dienste beinhalten möglicherweise eine fortlaufende bidirektionale Kommunikation wie das klassische "Rechner"-Beispiel aus der WCF-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="8f914-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="8f914-108">In diesem Kapitel werden zwei mögliche WCF-Implementierungen von "Stock Ticker" verwendet und zu GrpC migriert: eine mit einem Server-Streaming-RPC und die andere mit einem bidirektionalen Streaming-RPC.</span><span class="sxs-lookup"><span data-stu-id="8f914-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="8f914-109">Server-Streaming-RPC</span><span class="sxs-lookup"><span data-stu-id="8f914-109">Server streaming RPC</span></span>

<span data-ttu-id="8f914-110">In der [Beispiellösung simplestockticker WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *simplestockenttick,* gibt es einen Duplex Dienst, bei dem der Client die Verbindung mit einer Liste von Aktien Symbolen startet und der Server die *Rückruf Schnittstelle* verwendet, um Updates zu senden, sobald diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8f914-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="8f914-111">Der Client implementiert diese Schnittstelle, um auf Aufrufe vom Server zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="8f914-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="8f914-112">Die WCF-Lösung</span><span class="sxs-lookup"><span data-stu-id="8f914-112">The WCF solution</span></span>

<span data-ttu-id="8f914-113">Die WCF-Lösung wird als selbstgeh osteter NetTcp-Server in einer .NET Framework 4. x-Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="8f914-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="8f914-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="8f914-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="8f914-115">Der Dienst verfügt über eine einzelne Methode ohne Rückgabetyp, da er die Rückruf `ISimpleStockTickerCallback` Schnittstelle verwendet, um Daten in Echtzeit an den Client zu senden.</span><span class="sxs-lookup"><span data-stu-id="8f914-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="8f914-116">Die Rückruf Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f914-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="8f914-117">Die Implementierungen dieser Schnittstellen finden Sie in der Lösung zusammen mit fatierten externen Abhängigkeiten, um Testdaten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8f914-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="8f914-118">GrpC-Streaming</span><span class="sxs-lookup"><span data-stu-id="8f914-118">gRPC streaming</span></span>

<span data-ttu-id="8f914-119">Die GrpC-Methode für die Verarbeitung von Echtzeitdaten unterscheidet sich.</span><span class="sxs-lookup"><span data-stu-id="8f914-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="8f914-120">Ein Client-zu-Server-Client kann einen permanenten Stream erstellen, der auf asynchrone eingehende Nachrichten überwacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f914-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="8f914-121">Trotz des Unterschieds können Datenströme eine intuitivere Methode zum Umgang mit diesen Daten sein und sind relevanter in der modernen Programmierung mit dem Schwerpunkt auf LINQ, reaktivem Datenströmen, funktionaler Programmierung usw.</span><span class="sxs-lookup"><span data-stu-id="8f914-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="8f914-122">Die Dienst Definition benötigt zwei Nachrichten: eine für die Anforderung und eine für den Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="8f914-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="8f914-123">Der Dienst gibt einen Datenstrom der `StockTickerUpdate` Nachricht zurück, wobei das `stream`-Schlüsselwort in der `return` Deklaration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="8f914-124">Es wird empfohlen, dass Sie dem Update eine `Timestamp` hinzufügen, um die genaue Zeit anzuzeigen, zu der sich der Preis geändert hat.</span><span class="sxs-lookup"><span data-stu-id="8f914-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="8f914-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="8f914-125">simple_stock_ticker.proto</span></span>

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

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="8f914-126">Implementieren von simplestockticker</span><span class="sxs-lookup"><span data-stu-id="8f914-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="8f914-127">Verwenden Sie die gefälschten `StockPriceSubscriber` aus dem WCF-Projekt, indem Sie die drei Klassen aus der `TraderSys.StockMarket`-Klassenbibliothek in eine neue .NET Standard-Klassenbibliothek in der Ziel Projekt Mappe kopieren.</span><span class="sxs-lookup"><span data-stu-id="8f914-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="8f914-128">Um die bewährten Methoden besser befolgen zu können, fügen Sie einen `Factory` Typ hinzu, um Instanzen des IT-Diensts zu erstellen und die `IStockPriceSubscriberFactory` ASP.net Core mit den Abhängigkeits Injection-Diensten</span><span class="sxs-lookup"><span data-stu-id="8f914-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="8f914-129">Die Factory-Implementierung</span><span class="sxs-lookup"><span data-stu-id="8f914-129">The factory implementation</span></span>

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

#### <a name="registering-the-factory"></a><span data-ttu-id="8f914-130">Registrieren der Factory</span><span class="sxs-lookup"><span data-stu-id="8f914-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="8f914-131">Nun kann diese Klasse verwendet werden, um den GrpC Stock Ticker-Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8f914-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="8f914-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="8f914-132">StockTickerService.cs</span></span>

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
            // Handle any errors due to broken connection etc.
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

<span data-ttu-id="8f914-133">Wie Sie sehen können, gibt die Deklaration in der `.proto` Datei an, dass die Methode einen Stream von `StockTickerUpdate` Meldungen zurückgibt, tatsächlich wird eine Vanille `Task`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f914-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="8f914-134">Die Erstellung des Datenstroms erfolgt über den generierten Code und die GrpC-Laufzeitbibliotheken, die den `IServerStreamWriter<StockTickerUpdate>` Antwortstream bereitstellen, der verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f914-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="8f914-135">Anders als bei einem WCF-Duplex Dienst, bei dem die Instanz der Dienstklasse aktiv bleibt, während die Verbindung geöffnet ist, verwendet der GrpC-Dienst die zurückgegebene Aufgabe, um den Dienst aktiv zu halten.</span><span class="sxs-lookup"><span data-stu-id="8f914-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="8f914-136">Die Aufgabe sollte erst abgeschlossen werden, wenn die Verbindung geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8f914-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="8f914-137">Der Dienst kann erkennen, wann die Verbindung vom Client geschlossen wurde, indem die `CancellationToken` des `ServerCallContext`verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="8f914-138">Eine einfache statische Methode, `AwaitCancellation`, wird verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, wenn das Token abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="8f914-139">Erhalten Sie in der `Subscribe`-Methode eine `StockPriceSubscriber`, und fügen Sie einen Ereignishandler hinzu, der in den Antwortstream schreibt.</span><span class="sxs-lookup"><span data-stu-id="8f914-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="8f914-140">Warten Sie dann, bis die Verbindung geschlossen wurde, bevor Sie die `subscriber` sofort verwerfen, um zu verhindern, dass Daten in den geschlossenen Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8f914-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="8f914-141">Die `WriteUpdateAsync`-Methode verfügt über einen `try`/`catch` Block, um alle Fehler zu behandeln, die beim Schreiben einer Nachricht in den Datenstrom auftreten können.</span><span class="sxs-lookup"><span data-stu-id="8f914-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="8f914-142">Dies ist ein wichtiger Aspekt bei persistenten Verbindungen über Netzwerke, die in jeder Millisekunde beschädigt werden können, unabhängig davon, ob dies absichtlich oder aufgrund eines Fehlers irgendwo auftritt.</span><span class="sxs-lookup"><span data-stu-id="8f914-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="8f914-143">Verwenden von stocktickerservice aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="8f914-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="8f914-144">Führen Sie die gleichen Schritte im vorherigen Abschnitt aus, um eine Share able-Client Klassenbibliothek aus der `.proto`-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f914-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="8f914-145">Im Beispiel gibt es eine .net Core 3,0-Konsolenanwendung, die die Verwendung des-Clients veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8f914-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="8f914-146">Beispiel Program.cs</span><span class="sxs-lookup"><span data-stu-id="8f914-146">Example Program.cs</span></span>

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

<span data-ttu-id="8f914-147">In diesem Fall ist die `Subscribe`-Methode auf dem generierten Client nicht asynchron.</span><span class="sxs-lookup"><span data-stu-id="8f914-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="8f914-148">Der Stream wird sofort erstellt und verwendet, da seine `MoveNext`-Methode asynchron ist und das erste Mal aufgerufen wird, bis die Verbindung aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="8f914-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="8f914-149">Der Stream wird an eine Async-`DisplayAsync` Methode übermittelt. die Anwendung wartet dann darauf, dass der Benutzer eine Taste drückt, bricht die `DisplayAsync` Methode ab und wartet, bis die Aufgabe beendet ist, bevor Sie beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="8f914-150">In diesem Code wird die neue C# 8-Syntax "using-Deklaration" verwendet, um den Stream und den Kanal zu verwerfen, wenn die `Main`-Methode beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="8f914-151">Es handelt sich um eine kleine Änderung, aber eine schöne Änderung, die Einzüge und leere Zeilen reduziert.</span><span class="sxs-lookup"><span data-stu-id="8f914-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="8f914-152">Verbrauchen des Streams</span><span class="sxs-lookup"><span data-stu-id="8f914-152">Consume the stream</span></span>

<span data-ttu-id="8f914-153">WCF verwendete Rückruf Schnittstellen, damit der Server Methoden direkt auf dem Client aufruft.</span><span class="sxs-lookup"><span data-stu-id="8f914-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="8f914-154">GrpC-Streams funktionieren anders.</span><span class="sxs-lookup"><span data-stu-id="8f914-154">gRPC streams work differently.</span></span> <span data-ttu-id="8f914-155">Der Client durchläuft den zurückgegebenen Stream und verarbeitet Nachrichten, so als ob Sie von einer lokalen Methode zurückgegeben wurden, die eine `IEnumerable`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8f914-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="8f914-156">Der `IAsyncStreamReader<T>` Type funktioniert ähnlich wie ein `IEnumerator<T>`: Es gibt eine `MoveNext` Methode, die "true" zurückgibt, wenn mehr Daten vorhanden sind, und eine `Current` Eigenschaft, die den aktuellen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8f914-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="8f914-157">Der einzige Unterschied besteht darin, dass die `MoveNext`-Methode eine `Task<bool>` anstelle eines `bool`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8f914-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="8f914-158">Die `ReadAllAsync`-Erweiterungsmethode umschließt den Stream in C# einem Standard-8-`IAsyncEnumerable`, der mit der neuen `await foreach`-Syntax verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f914-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

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
> <span data-ttu-id="8f914-159">Der Abschnitt zu [Client Bibliotheken](client-libraries.md#iobservable) am Ende dieses Kapitels erläutert, wie eine Erweiterungsmethode und Klassen hinzugefügt werden, um `IAsyncStreamReader<T>` in einer `IObservable<T>` für Entwickler zu umschließen, die reaktive Programmier Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f914-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="8f914-160">Beachten Sie auch hier, dass Sie Ausnahmen hier aufgrund der Möglichkeit eines Netzwerk Fehlers und des <xref:System.OperationCanceledException>, das unweigerlich ausgelöst wird, wenn der Code einen <xref:System.Threading.CancellationToken> verwendet, um die Schleife zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="8f914-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="8f914-161">Der `RpcException`-Typ enthält viele nützliche Informationen zu GrpC-Laufzeitfehlern, einschließlich der `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="8f914-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="8f914-162">Weitere Informationen finden Sie unter [ *Fehlerbehandlung* in Kapitel 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="8f914-162">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="8f914-163">Bidirektionales Streaming</span><span class="sxs-lookup"><span data-stu-id="8f914-163">Bidirectional streaming</span></span>

<span data-ttu-id="8f914-164">Ein WCF-Vollduplex Dienst ermöglicht asynchrones Echt Zeit Messaging in beide Richtungen.</span><span class="sxs-lookup"><span data-stu-id="8f914-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="8f914-165">Im Server Streaming-Beispiel startet der Client eine Anforderung und empfängt dann einen Datenstrom von Updates.</span><span class="sxs-lookup"><span data-stu-id="8f914-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="8f914-166">Eine bessere Version dieses Dienstanbieter ermöglicht dem Client das Hinzufügen und Entfernen von Beständen aus der Liste, ohne ein neues Abonnement zu erstellen und zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f914-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="8f914-167">Diese Funktionalität wurde in der Beispiel Projekt Mappe [fullstockticker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)implementiert.</span><span class="sxs-lookup"><span data-stu-id="8f914-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="8f914-168">Die `IFullStockTickerService`-Schnittstelle stellt drei Methoden bereit:</span><span class="sxs-lookup"><span data-stu-id="8f914-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="8f914-169">`Subscribe` startet die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8f914-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="8f914-170">`AddSymbol` fügt ein zu überwachendes Aktiensymbol hinzu.</span><span class="sxs-lookup"><span data-stu-id="8f914-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="8f914-171">`RemoveSymbol` entfernt ein Symbol aus der überwachten Liste.</span><span class="sxs-lookup"><span data-stu-id="8f914-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

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

<span data-ttu-id="8f914-172">Die Rückruf Schnittstelle bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="8f914-172">The callback interface remains the same.</span></span>

<span data-ttu-id="8f914-173">Das Implementieren dieses Musters in GrpC ist weniger unkompliziert, da jetzt zwei Datenströme mit Nachrichten vorhanden sind, die an den Server übermittelt werden: einen vom Client zum Server und einen anderen von Server zu Client.</span><span class="sxs-lookup"><span data-stu-id="8f914-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="8f914-174">Es ist nicht möglich, mehrere Methoden zu verwenden, um den hinzu Füge-und Entfernungs Vorgang zu implementieren, aber mehrere Nachrichten Typen können in einem einzelnen Stream weitergegeben werden. dabei wird entweder der `Any` Type oder das `oneof`-Schlüsselwort verwendet, das in [Kapitel 3](protobuf-any-oneof.md)abgedeckt wurde.</span><span class="sxs-lookup"><span data-stu-id="8f914-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="8f914-175">Für einen Fall, in dem ein bestimmter Satz von Typen zulässig ist, ist `oneof` eine bessere Möglichkeit.</span><span class="sxs-lookup"><span data-stu-id="8f914-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="8f914-176">Verwenden Sie eine `ActionMessage`, die entweder eine `AddSymbolRequest` oder eine `RemoveSymbolRequest`enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="8f914-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

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

<span data-ttu-id="8f914-177">Deklarieren Sie einen bidirektionalen Streamingdienst, der einen Stream von `ActionMessage`-Nachrichten annimmt.</span><span class="sxs-lookup"><span data-stu-id="8f914-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="8f914-178">Die Implementierung für diesen Dienst ähnelt dem vorherigen Beispiel, mit dem Unterschied, dass der erste Parameter der `Subscribe`-Methode jetzt ein `IAsyncStreamReader<ActionMessage>`ist, der zum Verarbeiten der `Add` und `Remove` Anforderungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8f914-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

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
        // Handle any errors due to broken connection etc.
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

<span data-ttu-id="8f914-179">Die `ActionMessage` Klasse, die von GrpC für uns generiert wurde, gewährleistet, dass nur eine der `Add`-und `Remove` Eigenschaften festgelegt werden kann. das Auffinden der nicht `null` ist eine gültige Methode, um zu ermitteln, welcher Nachrichtentyp verwendet wird, aber es gibt eine bessere Methode.</span><span class="sxs-lookup"><span data-stu-id="8f914-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="8f914-180">Die Codegenerierung hat auch eine `enum ActionOneOfCase` in der `ActionMessage`-Klasse erstellt, die wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="8f914-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="8f914-181">Die-Eigenschaft `ActionCase` für das `ActionMessage`-Objekt kann mit einer `switch`-Anweisung verwendet werden, um zu bestimmen, welches Feld festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8f914-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

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
> <span data-ttu-id="8f914-182">Die `switch`-Anweisung verfügt über einen `default` Fall, der eine Warnung protokolliert, wenn ein unbekannter `ActionOneOfCase` Wert gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="8f914-183">Dies kann hilfreich sein, um anzugeben, dass ein Client eine spätere Version der `.proto` Datei verwendet, die weitere Aktionen hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="8f914-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="8f914-184">Dies ist ein Grund, warum die Verwendung eines `switch` besser ist als das Testen für `null` auf bekannten Feldern.</span><span class="sxs-lookup"><span data-stu-id="8f914-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="8f914-185">Verwenden von fullstocktickerservice aus einer Client Anwendung</span><span class="sxs-lookup"><span data-stu-id="8f914-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="8f914-186">Es gibt eine einfache .net Core 3,0 WPF-Anwendung, um die Verwendung dieses komplexeren Clients zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="8f914-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="8f914-187">Die vollständige Anwendung finden Sie [auf GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="8f914-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="8f914-188">Der-Client wird in der `MainWindowViewModel`-Klasse verwendet, die eine Instanz des `FullStockTicker.FullStockTickerClient` Typs aus der Abhängigkeitsinjektion abruft.</span><span class="sxs-lookup"><span data-stu-id="8f914-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

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

<span data-ttu-id="8f914-189">Das von der `client.Subscribe()`-Methode zurückgegebene Objekt ist nun eine Instanz des GrpC-Bibliotheks Typs `AsyncDuplexStreamingCall<TRequest, TResponse>`, die eine `RequestStream` zum Senden von Anforderungen an den Server und eine `ResponseStream` zur Behandlung von Antworten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8f914-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="8f914-190">Der Anforderungs Datenstrom wird in einigen WPF-`ICommand` Methoden zum Hinzufügen und Entfernen von Symbolen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f914-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="8f914-191">Legen Sie für jeden Vorgang das relevante Feld für ein `ActionMessage` Objekt fest:</span><span class="sxs-lookup"><span data-stu-id="8f914-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

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
> <span data-ttu-id="8f914-192">Wenn Sie den Wert eines `oneof` Felds für eine Nachricht festlegen, werden automatisch alle Felder gelöscht, die zuvor festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="8f914-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="8f914-193">Der Datenstrom von Antworten wird in einer `async`-Methode behandelt, und die zurückgegebene `Task` muss verworfen werden, wenn das Fenster geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="8f914-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

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

### <a name="client-clean-up"></a><span data-ttu-id="8f914-194">Client Bereinigung</span><span class="sxs-lookup"><span data-stu-id="8f914-194">Client clean-up</span></span>

<span data-ttu-id="8f914-195">Wenn das Fenster geschlossen wird und das `MainWindowViewModel` verworfen wird (aus dem `Closed`-Ereignis von `MainWindow`), wird empfohlen, dass Sie das `AsyncDuplexStreamingCall` Objekt ordnungsgemäß verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8f914-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="8f914-196">Insbesondere sollte die `CompleteAsync`-Methode des `RequestStream` aufgerufen werden, um den Stream auf dem Server ordnungsgemäß zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8f914-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="8f914-197">Das folgende Beispiel zeigt die `DisposeAsync`-Methode aus dem Sample View-Model:</span><span class="sxs-lookup"><span data-stu-id="8f914-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public ValueTask DisposeAsync()
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

<span data-ttu-id="8f914-198">Durch das Schließen von Anforderungs Datenströmen kann der Server seine eigenen Ressourcen rechtzeitig verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8f914-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="8f914-199">Dadurch wird die Effizienz und Skalierbarkeit von Diensten verbessert und Ausnahmen verhindert.</span><span class="sxs-lookup"><span data-stu-id="8f914-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8f914-200">[Zurück](migrate-request-reply.md)
>[Weiter](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="8f914-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
