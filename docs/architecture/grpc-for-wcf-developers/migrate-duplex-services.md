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
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Migrieren von WCF-Duplexdiensten zu gRPC

Nun, da die grundlegenden Konzepte vorhanden sind, werden in diesem Abschnitt die komplizierteren *Streaming* -GrpC-Dienste erläutert.

Es gibt mehrere Möglichkeiten, Duplex Dienste in Windows Communication Foundation (WCF) zu verwenden. Einige Dienste werden vom Client initiiert und dann Daten vom Server gestreamt. Andere Vollduplex Dienste beinhalten möglicherweise eine fortlaufende bidirektionale Kommunikation wie das klassische "Rechner"-Beispiel aus der WCF-Dokumentation. In diesem Kapitel werden zwei mögliche WCF-Implementierungen von "Stock Ticker" verwendet und zu GrpC migriert: eine mit einem Server-Streaming-RPC und die andere mit einem bidirektionalen Streaming-RPC.

## <a name="server-streaming-rpc"></a>Server-Streaming-RPC

In der [Beispiellösung simplestockticker WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *simplestockenttick,* gibt es einen Duplex Dienst, bei dem der Client die Verbindung mit einer Liste von Aktien Symbolen startet und der Server die *Rückruf Schnittstelle* verwendet, um Updates zu senden, sobald diese verfügbar sind. Der Client implementiert diese Schnittstelle, um auf Aufrufe vom Server zu reagieren.

### <a name="the-wcf-solution"></a>Die WCF-Lösung

Die WCF-Lösung wird als selbstgeh osteter NetTcp-Server in einer .NET Framework 4. x-Konsolenanwendung implementiert.

#### <a name="the-servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Der Dienst verfügt über eine einzelne Methode ohne Rückgabetyp, da er die Rückruf `ISimpleStockTickerCallback` Schnittstelle verwendet, um Daten in Echtzeit an den Client zu senden.

#### <a name="the-callback-interface"></a>Die Rückruf Schnittstelle

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Die Implementierungen dieser Schnittstellen finden Sie in der Lösung zusammen mit fatierten externen Abhängigkeiten, um Testdaten bereitzustellen.

### <a name="grpc-streaming"></a>GrpC-Streaming

Die GrpC-Methode für die Verarbeitung von Echtzeitdaten unterscheidet sich. Ein Client-zu-Server-Client kann einen permanenten Stream erstellen, der auf asynchrone eingehende Nachrichten überwacht werden kann. Trotz des Unterschieds können Datenströme eine intuitivere Methode zum Umgang mit diesen Daten sein und sind relevanter in der modernen Programmierung mit dem Schwerpunkt auf LINQ, reaktivem Datenströmen, funktionaler Programmierung usw.

Die Dienst Definition benötigt zwei Nachrichten: eine für die Anforderung und eine für den Datenstrom. Der Dienst gibt einen Datenstrom der `StockTickerUpdate` Nachricht zurück, wobei das `stream`-Schlüsselwort in der `return` Deklaration verwendet wird. Es wird empfohlen, dass Sie dem Update eine `Timestamp` hinzufügen, um die genaue Zeit anzuzeigen, zu der sich der Preis geändert hat.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker. proto

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

### <a name="implement-the-simplestockticker"></a>Implementieren von simplestockticker

Verwenden Sie die gefälschten `StockPriceSubscriber` aus dem WCF-Projekt, indem Sie die drei Klassen aus der `TraderSys.StockMarket`-Klassenbibliothek in eine neue .NET Standard-Klassenbibliothek in der Ziel Projekt Mappe kopieren. Um die bewährten Methoden besser befolgen zu können, fügen Sie einen `Factory` Typ hinzu, um Instanzen des IT-Diensts zu erstellen und die `IStockPriceSubscriberFactory` ASP.net Core mit den Abhängigkeits Injection-Diensten

#### <a name="the-factory-implementation"></a>Die Factory-Implementierung

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

#### <a name="registering-the-factory"></a>Registrieren der Factory

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Nun kann diese Klasse verwendet werden, um den GrpC Stock Ticker-Dienst zu implementieren.

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

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

Wie Sie sehen können, gibt die Deklaration in der `.proto` Datei an, dass die Methode einen Stream von `StockTickerUpdate` Meldungen zurückgibt, tatsächlich wird eine Vanille `Task`zurückgegeben. Die Erstellung des Datenstroms erfolgt über den generierten Code und die GrpC-Laufzeitbibliotheken, die den `IServerStreamWriter<StockTickerUpdate>` Antwortstream bereitstellen, der verwendet werden kann.

Anders als bei einem WCF-Duplex Dienst, bei dem die Instanz der Dienstklasse aktiv bleibt, während die Verbindung geöffnet ist, verwendet der GrpC-Dienst die zurückgegebene Aufgabe, um den Dienst aktiv zu halten. Die Aufgabe sollte erst abgeschlossen werden, wenn die Verbindung geschlossen wurde.

Der Dienst kann erkennen, wann die Verbindung vom Client geschlossen wurde, indem die `CancellationToken` des `ServerCallContext`verwendet wird. Eine einfache statische Methode, `AwaitCancellation`, wird verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, wenn das Token abgebrochen wird.

Erhalten Sie in der `Subscribe`-Methode eine `StockPriceSubscriber`, und fügen Sie einen Ereignishandler hinzu, der in den Antwortstream schreibt. Warten Sie dann, bis die Verbindung geschlossen wurde, bevor Sie die `subscriber` sofort verwerfen, um zu verhindern, dass Daten in den geschlossenen Stream geschrieben werden.

Die `WriteUpdateAsync`-Methode verfügt über einen `try`/`catch` Block, um alle Fehler zu behandeln, die beim Schreiben einer Nachricht in den Datenstrom auftreten können. Dies ist ein wichtiger Aspekt bei persistenten Verbindungen über Netzwerke, die in jeder Millisekunde beschädigt werden können, unabhängig davon, ob dies absichtlich oder aufgrund eines Fehlers irgendwo auftritt.

### <a name="using-the-stocktickerservice-from-a-client-application"></a>Verwenden von stocktickerservice aus einer Client Anwendung

Führen Sie die gleichen Schritte im vorherigen Abschnitt aus, um eine Share able-Client Klassenbibliothek aus der `.proto`-Datei zu erstellen. Im Beispiel gibt es eine .net Core 3,0-Konsolenanwendung, die die Verwendung des-Clients veranschaulicht.

#### <a name="example-programcs"></a>Beispiel Program.cs

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

In diesem Fall ist die `Subscribe`-Methode auf dem generierten Client nicht asynchron. Der Stream wird sofort erstellt und verwendet, da seine `MoveNext`-Methode asynchron ist und das erste Mal aufgerufen wird, bis die Verbindung aktiv ist.

Der Stream wird an eine Async-`DisplayAsync` Methode übermittelt. die Anwendung wartet dann darauf, dass der Benutzer eine Taste drückt, bricht die `DisplayAsync` Methode ab und wartet, bis die Aufgabe beendet ist, bevor Sie beendet wird.

> [!NOTE]
> In diesem Code wird die neue C# 8-Syntax "using-Deklaration" verwendet, um den Stream und den Kanal zu verwerfen, wenn die `Main`-Methode beendet wird. Es handelt sich um eine kleine Änderung, aber eine schöne Änderung, die Einzüge und leere Zeilen reduziert.

#### <a name="consume-the-stream"></a>Verbrauchen des Streams

WCF verwendete Rückruf Schnittstellen, damit der Server Methoden direkt auf dem Client aufruft. GrpC-Streams funktionieren anders. Der Client durchläuft den zurückgegebenen Stream und verarbeitet Nachrichten, so als ob Sie von einer lokalen Methode zurückgegeben wurden, die eine `IEnumerable`zurückgibt.

Der `IAsyncStreamReader<T>` Type funktioniert ähnlich wie ein `IEnumerator<T>`: Es gibt eine `MoveNext` Methode, die "true" zurückgibt, wenn mehr Daten vorhanden sind, und eine `Current` Eigenschaft, die den aktuellen Wert zurückgibt. Der einzige Unterschied besteht darin, dass die `MoveNext`-Methode eine `Task<bool>` anstelle eines `bool`zurückgibt. Die `ReadAllAsync`-Erweiterungsmethode umschließt den Stream in C# einem Standard-8-`IAsyncEnumerable`, der mit der neuen `await foreach`-Syntax verwendet werden kann.

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
> Der Abschnitt zu [Client Bibliotheken](client-libraries.md#iobservable) am Ende dieses Kapitels erläutert, wie eine Erweiterungsmethode und Klassen hinzugefügt werden, um `IAsyncStreamReader<T>` in einer `IObservable<T>` für Entwickler zu umschließen, die reaktive Programmier Muster verwenden.

Beachten Sie auch hier, dass Sie Ausnahmen hier aufgrund der Möglichkeit eines Netzwerk Fehlers und des <xref:System.OperationCanceledException>, das unweigerlich ausgelöst wird, wenn der Code einen <xref:System.Threading.CancellationToken> verwendet, um die Schleife zu unterbrechen. Der `RpcException`-Typ enthält viele nützliche Informationen zu GrpC-Laufzeitfehlern, einschließlich der `StatusCode`. Weitere Informationen finden Sie unter [ *Fehlerbehandlung* in Kapitel 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Bidirektionales Streaming

Ein WCF-Vollduplex Dienst ermöglicht asynchrones Echt Zeit Messaging in beide Richtungen. Im Server Streaming-Beispiel startet der Client eine Anforderung und empfängt dann einen Datenstrom von Updates. Eine bessere Version dieses Dienstanbieter ermöglicht dem Client das Hinzufügen und Entfernen von Beständen aus der Liste, ohne ein neues Abonnement zu erstellen und zu erstellen. Diese Funktionalität wurde in der Beispiel Projekt Mappe [fullstockticker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)implementiert.

Die `IFullStockTickerService`-Schnittstelle stellt drei Methoden bereit:

- `Subscribe` startet die Verbindung.
- `AddSymbol` fügt ein zu überwachendes Aktiensymbol hinzu.
- `RemoveSymbol` entfernt ein Symbol aus der überwachten Liste.

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

Die Rückruf Schnittstelle bleibt unverändert.

Das Implementieren dieses Musters in GrpC ist weniger unkompliziert, da jetzt zwei Datenströme mit Nachrichten vorhanden sind, die an den Server übermittelt werden: einen vom Client zum Server und einen anderen von Server zu Client. Es ist nicht möglich, mehrere Methoden zu verwenden, um den hinzu Füge-und Entfernungs Vorgang zu implementieren, aber mehrere Nachrichten Typen können in einem einzelnen Stream weitergegeben werden. dabei wird entweder der `Any` Type oder das `oneof`-Schlüsselwort verwendet, das in [Kapitel 3](protobuf-any-oneof.md)abgedeckt wurde.

Für einen Fall, in dem ein bestimmter Satz von Typen zulässig ist, ist `oneof` eine bessere Möglichkeit. Verwenden Sie eine `ActionMessage`, die entweder eine `AddSymbolRequest` oder eine `RemoveSymbolRequest`enthalten kann.

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

Deklarieren Sie einen bidirektionalen Streamingdienst, der einen Stream von `ActionMessage`-Nachrichten annimmt.

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

Die Implementierung für diesen Dienst ähnelt dem vorherigen Beispiel, mit dem Unterschied, dass der erste Parameter der `Subscribe`-Methode jetzt ein `IAsyncStreamReader<ActionMessage>`ist, der zum Verarbeiten der `Add` und `Remove` Anforderungen verwendet werden kann.

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

Die `ActionMessage` Klasse, die von GrpC für uns generiert wurde, gewährleistet, dass nur eine der `Add`-und `Remove` Eigenschaften festgelegt werden kann. das Auffinden der nicht `null` ist eine gültige Methode, um zu ermitteln, welcher Nachrichtentyp verwendet wird, aber es gibt eine bessere Methode. Die Codegenerierung hat auch eine `enum ActionOneOfCase` in der `ActionMessage`-Klasse erstellt, die wie folgt aussieht:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

Die-Eigenschaft `ActionCase` für das `ActionMessage`-Objekt kann mit einer `switch`-Anweisung verwendet werden, um zu bestimmen, welches Feld festgelegt ist.

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
> Die `switch`-Anweisung verfügt über einen `default` Fall, der eine Warnung protokolliert, wenn ein unbekannter `ActionOneOfCase` Wert gefunden wird. Dies kann hilfreich sein, um anzugeben, dass ein Client eine spätere Version der `.proto` Datei verwendet, die weitere Aktionen hinzugefügt hat. Dies ist ein Grund, warum die Verwendung eines `switch` besser ist als das Testen für `null` auf bekannten Feldern.

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a>Verwenden von fullstocktickerservice aus einer Client Anwendung

Es gibt eine einfache .net Core 3,0 WPF-Anwendung, um die Verwendung dieses komplexeren Clients zu veranschaulichen. Die vollständige Anwendung finden Sie [auf GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Der-Client wird in der `MainWindowViewModel`-Klasse verwendet, die eine Instanz des `FullStockTicker.FullStockTickerClient` Typs aus der Abhängigkeitsinjektion abruft.

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

Das von der `client.Subscribe()`-Methode zurückgegebene Objekt ist nun eine Instanz des GrpC-Bibliotheks Typs `AsyncDuplexStreamingCall<TRequest, TResponse>`, die eine `RequestStream` zum Senden von Anforderungen an den Server und eine `ResponseStream` zur Behandlung von Antworten bereitstellt.

Der Anforderungs Datenstrom wird in einigen WPF-`ICommand` Methoden zum Hinzufügen und Entfernen von Symbolen verwendet. Legen Sie für jeden Vorgang das relevante Feld für ein `ActionMessage` Objekt fest:

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
> Wenn Sie den Wert eines `oneof` Felds für eine Nachricht festlegen, werden automatisch alle Felder gelöscht, die zuvor festgelegt wurden.

Der Datenstrom von Antworten wird in einer `async`-Methode behandelt, und die zurückgegebene `Task` muss verworfen werden, wenn das Fenster geschlossen wird.

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

### <a name="client-clean-up"></a>Client Bereinigung

Wenn das Fenster geschlossen wird und das `MainWindowViewModel` verworfen wird (aus dem `Closed`-Ereignis von `MainWindow`), wird empfohlen, dass Sie das `AsyncDuplexStreamingCall` Objekt ordnungsgemäß verwerfen. Insbesondere sollte die `CompleteAsync`-Methode des `RequestStream` aufgerufen werden, um den Stream auf dem Server ordnungsgemäß zu schließen. Das folgende Beispiel zeigt die `DisposeAsync`-Methode aus dem Sample View-Model:

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

Durch das Schließen von Anforderungs Datenströmen kann der Server seine eigenen Ressourcen rechtzeitig verwerfen. Dadurch wird die Effizienz und Skalierbarkeit von Diensten verbessert und Ausnahmen verhindert.

>[!div class="step-by-step"]
>[Zurück](migrate-request-reply.md)
>[Weiter](streaming-versus-repeated.md)
