---
title: 'Erstellen von GrpC-Client Bibliotheken: GrpC für WCF-Entwickler'
description: Erörterung von freigegebenen Client Bibliotheken/-Paketen für GrpC-Dienste
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675170"
---
# <a name="create-grpc-client-libraries"></a>Erstellen von GrpC-Client Bibliotheken

Es ist nicht erforderlich, Client Bibliotheken für eine GrpC-Anwendung zu verteilen. Sie können eine freigegebene Bibliothek von `.proto` Dateien in Ihrer Organisation erstellen, und andere Teams können diese Dateien verwenden, um Client Code in ihren eigenen Projekten zu generieren. Wenn Sie jedoch über ein privates nuget-Repository verfügen und viele andere Teams .net Core verwenden, können Sie Client-nuget-Pakete im Rahmen Ihres Dienst Projekts erstellen und veröffentlichen. Dies kann eine gute Möglichkeit zum Freigeben und herauf Stufen Ihres Dienstanbieter sein.

Ein Vorteil der Verteilung einer Client Bibliothek besteht darin, dass Sie die generierten GrpC-und protobuf-Klassen mit nützlichen Methoden und Eigenschaften verbessern können. Im Client Code, wie auf dem Server, werden alle Klassen als `partial`deklariert, sodass Sie Sie erweitern können, ohne den generierten Code zu bearbeiten. Dies bedeutet, dass es einfach ist, den Grundtypen Konstruktoren, Methoden und berechnete Eigenschaften hinzuzufügen.

> [!CAUTION]
> Sie sollten keinen benutzerdefinierten Code verwenden, um wesentliche Funktionen bereitzustellen. Sie möchten diese wesentlichen Funktionen nicht auf .NET-Teams beschränken, die die freigegebene Bibliothek verwenden, und Sie nicht für Teams bereitstellen, die andere Sprachen oder Plattformen wie Python oder Java verwenden.

Stellen Sie sicher, dass so viele Teams wie möglich auf Ihren GrpC-Dienst zugreifen können. Die beste Möglichkeit hierfür ist die Freigabe von `.proto` Dateien, damit Entwickler ihre eigenen Clients generieren können. Dies gilt insbesondere in einer Umgebung mit mehreren Plattformen, in der unterschiedliche Teams häufig verschiedene Programmiersprachen und-Frameworks verwenden, oder wenn die API Extern zugänglich ist.

## <a name="useful-extensions"></a>Nützliche Erweiterungen

Für den Umgang mit Objekten von Objekten gibt es zwei häufig verwendete Schnittstellen in .net: <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IObservable%601>. Ab .net Core 3,0 und C# 8,0 gibt es eine <xref:System.Collections.Generic.IAsyncEnumerable%601>-Schnittstelle für die asynchrone Verarbeitung von Streams und eine `await foreach` Syntax für die Verwendung der-Schnittstelle. Dieser Abschnitt enthält wiederverwendbaren Code zum Anwenden dieser Schnittstellen auf GrpC-Streams.

Mit den .net Core-GrpC-Client Bibliotheken gibt es eine `ReadAllAsync` Erweiterungsmethode für `IAsyncStreamReader<T>`, die eine `IAsyncEnumerable<T>`-Schnittstelle erstellt. Für Entwickler, die reaktive Programmierung verwenden, könnte eine äquivalente Erweiterungsmethode zum Erstellen einer `IObservable<T>`-Schnittstelle wie im folgenden Abschnitt aussehen.

### <a name="iobservable"></a>IObservable

Die `IObservable<T>`-Schnittstelle ist die "reaktive" Umkehrung von `IEnumerable<T>`. Anstatt Elemente aus einem Stream abzurufen, ermöglicht der reaktive Ansatz dem Stream das Übertragen von Push-Elementen an einen Abonnenten. Dies ist sehr ähnlich wie bei GrpC-Streams, und es ist einfach, eine `IObservable<T>`-Schnittstelle um eine `IAsyncStreamReader<T>` Schnittstelle zu umschließen.

Dieser Code ist länger als der `IAsyncEnumerable<T>`-Code, C# da nicht über eine integrierte Unterstützung für die Arbeit mit Observables verfügt. Sie müssen die Implementierungs Klasse manuell erstellen. Dabei handelt es sich jedoch um eine generische Klasse, sodass eine einzelne Implementierung über alle Typen hinweg funktioniert.

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
> Diese Observable-Implementierung ermöglicht, dass die `Subscribe`-Methode nur einmal aufgerufen werden kann, da mehrere Abonnenten, die versuchen, aus dem Stream zu lesen, zu Chaos führen würden. Es gibt Operatoren, wie z. b [. `Replay` in System. reaktivem. Linq](https://www.nuget.org/packages/System.Reactive.Linq), die die Pufferung und wiederholbare Freigabe von Observables ermöglichen, die mit dieser Implementierung verwendet werden kann.

Die `GrpcStreamSubscription` Klasse behandelt die Enumeration des `IAsyncStreamReader`:

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

Die `IAsyncEnumerable`-und `IObservable` Modelle sind sowohl gut unterstützte als auch gut dokumentierte Möglichkeiten, mit asynchronen Datenströmen in .net umzugehen. GrpC-Streams sind sowohl für Paradigmen als auch für eine enge Integration mit .net Core und für reaktive und asynchrone Programmier Stile gleich.

>[!div class="step-by-step"]
>[Zurück](streaming-versus-repeated.md)
>[Weiter](security.md)
