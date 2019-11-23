---
title: 'Erstellen von GrpC-Client Bibliotheken: GrpC für WCF-Entwickler'
description: Erörterung von freigegebenen Client Bibliotheken/-Paketen für GrpC-Dienste
ms.date: 09/02/2019
ms.openlocfilehash: 2135fe8b24a2311a31cb2bed191d290b1112bc66
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967878"
---
# <a name="create-grpc-client-libraries"></a>Erstellen von GrpC-Client Bibliotheken

Es ist nicht erforderlich, Client Bibliotheken für eine GrpC-Anwendung zu verteilen. Sie können eine freigegebene Bibliothek von `.proto` Dateien in Ihrer Organisation erstellen, und andere Teams können diese Dateien verwenden, um Client Code in ihren eigenen Projekten zu generieren. Wenn Sie jedoch über ein privates nuget-Repository verfügen und viele andere Teams .net Core verwenden, kann das Erstellen und Veröffentlichen von Client-nuget-Paketen als Teil Ihres Dienst Projekts eine gute Möglichkeit zum Freigeben und herauf Stufen Ihres Dienstanbieter sein.

Ein Vorteil der Verteilung einer Client Bibliothek besteht darin, dass Sie die generierten GrpC-und protobuf-Klassen mit nützlichen Methoden und Eigenschaften verbessern können. Im Client Code, wie auf dem Server, werden alle Klassen als `partial` deklariert, sodass Sie Sie erweitern können, ohne den generierten Code zu bearbeiten. Dies bedeutet, dass es einfach ist, Konstruktoren, Methoden, berechnete Eigenschaften und vieles mehr zu den grundlegenden Typen hinzuzufügen.

> [!CAUTION]
> Sie sollten **keinen** benutzerdefinierten Code verwenden, um wesentliche Funktionen bereitzustellen, da dies bedeutet, dass die Funktionalität auf .NET-Teams beschränkt wäre, die die freigegebene Bibliothek verwenden, und nicht an Teams, die andere Sprachen oder Plattformen wie Python oder Java verwenden.

In einer Umgebung mit mehreren Plattformen, in der unterschiedliche Teams häufig andere Programmiersprachen und Frameworks verwenden, oder wenn die API Extern zugänglich ist, müssen Sie einfach `.proto` Dateien freigeben, damit Entwickler ihre eigenen Clients generieren können. so können Sie sicherstellen, dass so viele Teams wie möglich auf Ihren GrpC-Dienst zugreifen können.

## <a name="useful-extensions"></a>Nützliche Erweiterungen

Für den Umgang mit Objekten von Objekten gibt es zwei häufig verwendete Schnittstellen in .net: <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IObservable%601>. Ab .net Core 3,0 und C# 8,0 gibt es eine <xref:System.Collections.Generic.IAsyncEnumerable%601>-Schnittstelle für die asynchrone Verarbeitung von Streams und eine `await foreach` Syntax für die Verwendung der-Schnittstelle. Dieser Abschnitt enthält wiederverwendbaren Code zum Anwenden dieser Schnittstellen auf GrpC-Streams.

Mit den .net Core-GrpC-Client Bibliotheken gibt es eine `ReadAllAsync` Erweiterungsmethode für `IAsyncStreamReader<T>`, die eine `IAsyncEnumerable<T>`erstellt. Für Entwickler, die reaktive Programmierung verwenden, könnte eine äquivalente Erweiterungsmethode zum Erstellen eines `IObservable<T>` wie folgt aussehen.

### <a name="iobservable"></a>IObservable

Die `IObservable<T>`-Schnittstelle ist die "reaktive" Umkehrung von `IEnumerable<T>`. Anstatt Elemente aus einem Stream abzurufen, ermöglicht der reaktive Ansatz dem Stream das Übertragen von Push-Elementen an einen Abonnenten. Dies ist sehr ähnlich wie bei GrpC-Streams, und es ist einfach, eine `IObservable<T>` um eine `IAsyncStreamReader<T>`zu umschließen.

Dieser Code ist länger als der `IAsyncEnumerable<T>`-Code C# , da nicht über integrierte Unterstützung für die Arbeit mit Observables verfügt. Daher muss die Implementierungs Klasse manuell erstellt werden. Dabei handelt es sich jedoch um eine generische Klasse, sodass eine einzelne Implementierung über alle Typen hinweg funktioniert.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> Diese Observable-Implementierung ermöglicht nur das einmalige Aufrufen der `Subscribe` Methode, da mehrere Abonnenten, die versuchen, aus dem Stream zu lesen, zu Chaos führen würden. Es gibt Operatoren, wie z. b. `Replay` in [System. reaktives. Linq](https://www.nuget.org/packages/System.Reactive.Linq) , die die Pufferung und wiederholbare Freigabe von Observables ermöglichen, die mit dieser Implementierung verwendet werden kann.

Die `GrpcStreamSubscription` Klasse behandelt die Enumeration des `IAsyncStreamReader`.

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

Dies ist nun eine einfache Erweiterungsmethode, mit der das Observable-Objekt aus dem StreamReader erstellt werden kann.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>Zusammenfassung

Die `IAsyncEnumerable`-und `IObservable` Modelle sind sowohl gut unterstützte als auch gut dokumentierte Möglichkeiten, mit asynchronen Datenströmen in .net umzugehen. GrpC-Streams sind für beide Paradigmen gut Zuordnungen und bieten eine enge Integration mit dem modernen .net Core-Framework und reaktiven/asynchronen Programmier Stilen.

>[!div class="step-by-step"]
>[Zurück](streaming-versus-repeated.md)
>[Weiter](security.md)
