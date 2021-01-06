---
title: Migrieren von WCF-Duplex Diensten zu GrpC-GrpC für WCF-Entwickler
description: Erfahren Sie, wie Sie verschiedene Arten von WCF-Duplex Diensten zu GrpC-Streamingdiensten migrieren.
ms.date: 12/15/2020
ms.openlocfilehash: 4741e5ad5c12fa358853381d4f2c286add14f8f5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938025"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Migrieren von WCF-Duplexdiensten zu gRPC

Nachdem Sie sich nun mit den grundlegenden Konzepten vertraut machen, sehen Sie sich in diesem Abschnitt die komplizierteren *Streaming* -GrpC-Dienste an.

Es gibt mehrere Möglichkeiten, Duplex Dienste in Windows Communication Foundation (WCF) zu verwenden. Einige Dienste werden vom Client initiiert und dann Daten vom Server gestreamt. Andere Vollduplex Dienste können eine fortlaufende bidirektionale Kommunikation beinhalten, wie z. b. das klassische Rechner Beispiel in der WCF-Dokumentation. In diesem Kapitel werden zwei mögliche WCF Stock Ticker-Implementierungen verwendet und zu GrpC migriert: eine, die ein Server-Streaming-RPC verwendet, und eine andere, die ein bidirektionales Streaming von RPC verwendet.

## <a name="server-streaming-rpc"></a>Server-Streaming-RPC

In der [Beispiellösung simplestockticker WCF](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), simplestockeupticker, gibt es einen Duplex Dienst, für den der Client die Verbindung mit einer Liste von Aktien Symbolen startet, und der Server verwendet die *Rückruf Schnittstelle* , um Updates zu senden, sobald diese verfügbar sind. Der Client implementiert diese Schnittstelle, um auf Aufrufe vom Server zu reagieren.

### <a name="the-wcf-solution"></a>Die WCF-Lösung

Die WCF-Lösung wird als selbstgeh osteter net. TCP-Server in einem .NET Framework 4 implementiert. *x* -Konsolenanwendung.

#### <a name="servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Der Dienst verfügt über eine einzelne Methode ohne Rückgabetyp, da er die Rückruf Schnittstelle verwendet `ISimpleStockTickerCallback` , um Daten in Echtzeit an den Client zu senden.

#### <a name="the-callback-interface"></a>Die Rückruf Schnittstelle

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Sie finden die Implementierungen dieser Schnittstellen in der Lösung zusammen mit fasteten externen Abhängigkeiten, um Testdaten bereitzustellen.

### <a name="grpc-streaming"></a>GrpC-Streaming

Der GrpC-Prozess für die Verarbeitung von Echtzeitdaten unterscheidet sich vom WCF-Prozess. Ein Client-zu-Server-Client kann einen permanenten Stream erstellen, der auf eingehende Nachrichten überwacht werden kann. Trotz des Unterschieds können Datenströme eine intuitivere Methode zum Umgang mit diesen Daten sein und sind relevanter in der modernen Programmierung, die LINQ, reaktive Streams, funktionale Programmierung usw. unterstreicht.

Die Dienst Definition benötigt zwei Nachrichten: eine für die Anforderung und eine für den Datenstrom. Der Dienst gibt einen Stream der `StockTickerUpdate` Nachricht mit dem- `stream` Schlüsselwort in der `return` Deklaration zurück. Es wird empfohlen, dass Sie `Timestamp` der Aktualisierung einen hinzufügen, um den genauen Zeitpunkt der Preisänderung anzuzeigen.

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

### <a name="implement-simplestockticker"></a>Implementieren von simplestockticker

Verwenden Sie den Fake `StockPriceSubscriber` aus dem WCF-Projekt, indem Sie die drei Klassen aus der `TraderSys.StockMarket` Klassenbibliothek in eine neue .NET Standard-Klassenbibliothek in der Ziel Projekt Mappe kopieren. Um ASP.net Core die bewährten Methoden besser befolgen zu können, fügen Sie einen Typ hinzu, `Factory` um Instanzen zu erstellen `IStockPriceSubscriberFactory`

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

#### <a name="register-the-factory"></a>Registrieren der Factory

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Diese Klasse kann jetzt zum Implementieren von GrpC verwendet werden `StockTickerService` .

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

Wie Sie sehen, gibt die-Deklaration in der `.proto` Datei an, dass die Methode einen Nachrichtenstrom zurückgibt `StockTickerUpdate` , es wird jedoch ein zurückgegeben `Task` . Die Erstellung des Datenstroms erfolgt über den generierten Code und die GrpC-Laufzeitbibliotheken, die den `IServerStreamWriter<StockTickerUpdate>` Antwortdaten Strom bereitstellen, der verwendet werden kann.

Anders als bei einem WCF-Duplex Dienst, bei dem die Instanz der Dienstklasse aktiv bleibt, während die Verbindung geöffnet ist, verwendet der GrpC-Dienst die zurückgegebene Aufgabe, um den Dienst aktiv zu halten. Die Aufgabe sollte erst abgeschlossen werden, wenn die Verbindung geschlossen wurde.

Der Dienst kann erkennen, wann die Verbindung vom Client geschlossen wurde, indem der `CancellationToken` aus dem verwendet wird `ServerCallContext` . Eine einfache statische Methode, `AwaitCancellation` , wird verwendet, um eine Aufgabe zu erstellen, die abgeschlossen wird, wenn das Token abgebrochen wird.

In der `Subscribe` -Methode erhalten Sie dann eine `StockPriceSubscriber` und fügen einen Ereignishandler hinzu, der in den Antwortstream schreibt. Warten Sie dann, bis die Verbindung geschlossen wurde, bevor Sie sofort den verwerfen `subscriber` , um zu verhindern, dass Daten in den geschlossenen Stream geschrieben werden.

Die- `WriteUpdateAsync` Methode verfügt über einen- `try` / `catch` Block, um alle Fehler zu behandeln, die auftreten können, wenn eine Nachricht in den Stream geschrieben wird. Diese Überlegungen sind bei persistenten Verbindungen über Netzwerke wichtig, die in jeder Millisekunde unterbrechen werden können, egal ob absichtlich oder aufgrund eines Fehlers an einem Ort.

### <a name="use-stocktickerservice-from-a-client-application"></a>Verwenden von stocktickerservice aus einer Client Anwendung

Führen Sie die gleichen Schritte im vorherigen Abschnitt aus, um eine Share Bare Client Klassenbibliothek aus der Datei zu erstellen `.proto` . Im Beispiel gibt es eine .NET-Konsolenanwendung, die die Verwendung des-Clients veranschaulicht.

#### <a name="example-programcs"></a>Beispiel für „Program.cs“

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

In diesem Fall ist die- `Subscribe` Methode auf dem generierten Client nicht asynchron. Der Stream wird sofort erstellt und verwendet, da seine- `MoveNext` Methode asynchron ist, und wenn er zum ersten Mal aufgerufen wird, wird er erst beendet, wenn die Verbindung aktiv ist.

Der Stream wird an eine asynchrone Methode übermittelt `DisplayAsync` . Die Anwendung wartet dann darauf, dass der Benutzer eine Taste drückt, bricht die Methode ab `DisplayAsync` und wartet, bis die Aufgabe beendet ist, bevor Sie beendet wird.

> [!NOTE]
> In diesem Code wird die neue c# 8 `using` -Deklarations Syntax verwendet, um den Stream und den Kanal zu verwerfen, wenn die `Main` Methode beendet wird. Es handelt sich um eine kleine Änderung, aber eine schöne Änderung, die Einzüge und leere Zeilen reduziert.

#### <a name="consume-the-stream"></a>Verbrauchen des Streams

WCF verwendet Rückruf Schnittstellen, damit der Server Methoden direkt auf dem Client aufruft. GrpC-Streams funktionieren anders. Der Client durchläuft den zurückgegebenen Stream und verarbeitet Nachrichten, so als ob Sie von einer lokalen Methode zurückgegeben wurden, die zurückgibt `IEnumerable` .

Der- `IAsyncStreamReader<T>` Typ funktioniert ähnlich wie `IEnumerator<T>` . Es gibt eine `MoveNext` Methode, die true zurückgibt, wenn mehr Daten vorhanden sind, und eine- `Current` Eigenschaft, die den aktuellen Wert zurückgibt. Der einzige Unterschied besteht darin, dass die `MoveNext` Methode `Task<bool>` anstelle von nur einen zurückgibt `bool` . Die `ReadAllAsync` Erweiterungsmethode umschließt den Stream in einem standardmäßigen c# 8 `IAsyncEnumerable` , der mit der neuen Syntax verwendet werden kann `await foreach` .

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
> Für Entwickler, die reaktive Programmier Muster verwenden, zeigt der Abschnitt zu [Client Bibliotheken](client-libraries.md#iobservable) am Ende dieses Kapitels, wie eine Erweiterungsmethode und Klassen hinzugefügt werden, die in einem umschlossen werden `IAsyncStreamReader<T>` `IObservable<T>` .

Achten Sie auch hier darauf, dass Sie Ausnahmen hier aufgrund der Möglichkeit eines Netzwerk Fehlers und aufgrund der auslösen, die ausgelöst wird, da <xref:System.OperationCanceledException> der Code einen verwendet <xref:System.Threading.CancellationToken> , um die Schleife zu unterbrechen. Der- `RpcException` Typ verfügt über viele nützliche Informationen zu GrpC-Laufzeitfehlern, einschließlich der `StatusCode` . Weitere Informationen finden Sie unter [ *Fehlerbehandlung* in Kapitel 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Bidirektionales Streaming

Ein WCF-Vollduplex Dienst ermöglicht asynchrones Echt Zeit Messaging in beide Richtungen. Im Server Streaming-Beispiel startet der Client eine Anforderung und empfängt dann einen Datenstrom von Updates. Eine bessere Version dieses Dienstanbieter ermöglicht dem Client das Hinzufügen und Entfernen von Beständen aus der Liste, ohne ein neues Abonnement zu erstellen und zu erstellen. Diese Funktionalität wurde in der Beispiel Projekt Mappe [fullstockticker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)implementiert.

Die- `IFullStockTickerService` Schnittstelle stellt drei Methoden bereit:

- `Subscribe` startet die Verbindung.
- `AddSymbol` Fügt ein zu überwachendes Aktiensymbol hinzu.
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

Die Implementierung dieses Musters in GrpC ist weniger unkompliziert, da jetzt zwei Datenströme mit Nachrichten vorhanden sind, die übermittelt werden: eine vom Client zum Server und eine andere von Server zu Client. Es ist nicht möglich, mehrere Methoden zu verwenden, um die Add-und Remove-Vorgänge zu implementieren. Sie können jedoch mehr als einen Typ von Nachrichten in einem einzigen Stream übergeben, indem Sie entweder den- `Any` Typ oder das- `oneof` Schlüsselwort verwenden, die in [Kapitel 3](protobuf-any-oneof.md)behandelt wurden.

In einem Fall, in dem es einen bestimmten Satz von Typen gibt, der akzeptabel ist, `oneof` ist eine bessere Methode. Verwenden Sie `ActionMessage` , das entweder einen `AddSymbolRequest` oder einen enthalten kann `RemoveSymbolRequest` :

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

Deklarieren Sie einen bidirektionalen Streamingdienst, der einen `ActionMessage` Nachrichten Nachrichtenstrom annimmt:

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

Die Implementierung für diesen Dienst ähnelt der des vorherigen Beispiels, mit dem Unterschied, dass der erste Parameter der `Subscribe` -Methode jetzt ein ist `IAsyncStreamReader<ActionMessage>` , der verwendet werden kann, um die `Add` Anforderungen und zu verarbeiten `Remove` :

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

Die `ActionMessage` Klasse, die von GrpC generiert wurde, stellt sicher, dass nur eine der `Add` -und- `Remove` Eigenschaften festgelegt werden kann. Das Auffinden, welche `null` Art von Nachricht verwendet wird, ist nicht gültig, aber es gibt eine bessere Möglichkeit. Die Codegenerierung hat auch einen `enum ActionOneOfCase` in der- `ActionMessage` Klasse erstellt, der wie folgt aussieht:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

Die-Eigenschaft des- `ActionCase` `ActionMessage` Objekts kann mit einer- `switch` Anweisung verwendet werden, um zu bestimmen, welches Feld festgelegt ist:

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
> Die- `switch` Anweisung verfügt über einen `default` Fall, in dem eine Warnung protokolliert wird, wenn ein unbekannter Wert gefunden wird `ActionOneOfCase` . Dies kann hilfreich sein, um anzugeben, dass ein Client eine spätere Version der `.proto` Datei verwendet, die weitere Aktionen hinzugefügt hat. Dies ist ein Grund, warum die Verwendung eines `switch` besser ist als das Testen für `null` bekannte Felder.

### <a name="use-fullstocktickerservice-from-a-client-application"></a>Verwenden von fullstocktickerservice aus einer Client Anwendung

Es gibt eine einfache .net WPF-Anwendung, die die Verwendung dieses komplexeren Clients veranschaulicht. Sie finden die vollständige Anwendung auf [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Der-Client wird in der- `MainWindowViewModel` Klasse verwendet, die eine Instanz des `FullStockTicker.FullStockTickerClient` Typs aus der Abhängigkeitsinjektion abruft:

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

Das von der-Methode zurückgegebene-Objekt `client.Subscribe()` ist nun eine Instanz des GrpC `AsyncDuplexStreamingCall<TRequest, TResponse>` -Bibliotheks Typs, die ein `RequestStream` zum Senden von Anforderungen an den Server und ein `ResponseStream` zum Verarbeiten von Antworten bereitstellt.

Der Anforderungs Datenstrom wird aus einigen WPF `ICommand` -Methoden zum Hinzufügen und Entfernen von Symbolen verwendet. Legen Sie für jeden Vorgang das relevante Feld für ein `ActionMessage` Objekt fest:

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
> Wenn Sie `oneof` den Wert eines Felds für eine Meldung festlegen, werden automatisch alle Felder gelöscht, die zuvor festgelegt wurden.

Der Stream der Antworten wird in einer- `async` Methode behandelt. Der `Task` zurückgegebene Wert wird aufbewahrt, wenn das Fenster geschlossen wird:

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

### <a name="client-cleanup"></a>Client Bereinigung

Wenn das Fenster geschlossen wird und das verworfen `MainWindowViewModel` wird (aus dem- `Closed` Ereignis von `MainWindow` ), empfiehlt es sich, das- `AsyncDuplexStreamingCall` Objekt ordnungsgemäß zu verwerfen. Insbesondere sollte die- `CompleteAsync` Methode für den `RequestStream` aufgerufen werden, um den Stream auf dem Server ordnungsgemäß zu schließen. Dieses Beispiel zeigt die `DisposeAsync` -Methode aus dem Sample View-Model:

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

Das Schließen von Anforderungs Datenströmen ermöglicht es dem Server, seine eigenen Ressourcen rechtzeitig freizugeben. Dadurch wird die Effizienz und Skalierbarkeit von Diensten verbessert und Ausnahmen verhindert.

>[!div class="step-by-step"]
>[Zurück](migrate-request-reply.md)
>[Weiter](streaming-versus-repeated.md)
