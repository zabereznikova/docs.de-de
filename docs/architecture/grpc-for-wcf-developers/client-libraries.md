---
title: erstellen von gRPC-Clientbibliotheken - gRPC für WCF-Entwickler
description: Diskussion freigegebener Clientbibliotheken/-pakete für gRPC-Dienste.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401772"
---
# <a name="create-grpc-client-libraries"></a>Erstellen von gRPC-Clientbibliotheken

Es ist nicht erforderlich, Clientbibliotheken für eine gRPC-Anwendung zu verteilen. Sie können eine freigegebene Bibliothek mit `.proto` Dateien in Ihrer Organisation erstellen, und andere Teams können diese Dateien verwenden, um Clientcode in ihren eigenen Projekten zu generieren. Wenn Sie jedoch über ein privates NuGet-Repository verfügen und viele andere Teams .NET Core verwenden, können Sie NuGet-Clientpakete als Teil Ihres Serviceprojekts erstellen und veröffentlichen. Dies kann eine gute Möglichkeit sein, Ihren Dienst zu teilen und zu bewerben.

Ein Vorteil der Verteilung einer Clientbibliothek besteht darin, dass Sie die generierten gRPC- und Protobuf-Klassen mit hilfreichen "Convenience"-Methoden und -Eigenschaften erweitern können. Im Clientcode werden, wie auch im Server, `partial`alle Klassen als deklariert, sodass Sie sie erweitern können, ohne den generierten Code zu bearbeiten. Dies bedeutet, dass es einfach ist, Konstruktoren, Methoden und berechnete Eigenschaften zu den Basistypen hinzuzufügen.

> [!CAUTION]
> Sie sollten keinen benutzerdefinierten Code verwenden, um wesentliche Funktionen bereitzustellen. Sie möchten diese wesentlichen Funktionen nicht auf .NET-Teams beschränken, die die freigegebene Bibliothek verwenden, und sie nicht Für Teams bereitstellen, die andere Sprachen oder Plattformen wie Python oder Java verwenden.

Stellen Sie sicher, dass so viele Teams wie möglich auf Ihren gRPC-Dienst zugreifen können. Der beste Weg, dies `.proto` zu tun, ist Dateien freizugeben, damit Entwickler ihre eigenen Clients generieren können. Dies gilt insbesondere für eine Umgebung mit mehreren Plattformen, in der verschiedene Teams häufig unterschiedliche Programmiersprachen und Frameworks verwenden oder in der Ihre API extern zugänglich ist.

## <a name="useful-extensions"></a>Nützliche Erweiterungen

Es gibt zwei häufig verwendete Schnittstellen in .NET <xref:System.Collections.Generic.IEnumerable%601> für <xref:System.IObservable%601>den Umgang mit Datenströmen von Objekten: und . Beginnend mit .NET Core 3.0 und C-8.0 gibt es eine <xref:System.Collections.Generic.IAsyncEnumerable%601> Schnittstelle `await foreach` zum asynchronen Verarbeiten von Streams und eine Syntax für die Verwendung der Schnittstelle. In diesem Abschnitt wird wiederverwendbarer Code zum Anwenden dieser Schnittstellen auf gRPC-Streams dargestellt.

Mit den .NET Core gRPC-Clientbibliotheken `ReadAllAsync` gibt `IAsyncStreamReader<T>` es eine `IAsyncEnumerable<T>` Erweiterungsmethode, die eine Schnittstelle erstellt. Für Entwickler, die reaktive Programmierung verwenden, `IObservable<T>` könnte eine gleichwertige Erweiterungsmethode zum Erstellen einer Schnittstelle wie das Beispiel im folgenden Abschnitt aussehen.

### <a name="iobservable"></a>IObservable

Die `IObservable<T>` Schnittstelle ist die "reaktive" Umkehrung von `IEnumerable<T>`. Anstatt Elemente aus einem Stream zu ziehen, ermöglicht der reaktive Ansatz, dass der Stream Elemente an einen Abonnenten überträgt. Dies ist sehr ähnlich zu gRPC-Streams, `IObservable<T>` und es `IAsyncStreamReader<T>` ist einfach, eine Schnittstelle um eine Schnittstelle zu wickeln.

Dieser Code ist `IAsyncEnumerable<T>` länger als der Code, da die Datei für die Arbeit mit Beobachtbaren nicht integriert ist. Sie müssen die Implementierungsklasse manuell erstellen. Es ist jedoch eine generische Klasse, sodass eine einzelne Implementierung für alle Typen funktioniert.

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
> Diese beobachtbare `Subscribe` Implementierung ermöglicht es, die Methode nur einmal aufzuführen, da mehrere Abonnenten versuchen würden, aus dem Stream zu lesen, was zu Chaos führen würde. Es gibt Operatoren, z. `Replay` B. in Der [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), die Pufferung und wiederholbare Freigabe von Beobachtbaren ermöglichen, die mit dieser Implementierung verwendet werden können.

Die `GrpcStreamSubscription` Klasse behandelt die Aufzählung `IAsyncStreamReader`von :

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

Alles, was jetzt erforderlich ist, ist eine einfache Erweiterungsmethode, um das Beobachtbare aus dem Streamleser zu erstellen.

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

Die `IAsyncEnumerable` `IObservable` und Modelle sind sowohl gut unterstützte als auch gut dokumentierte Methoden zum Umgang mit asynchronen Datenströmen in .NET. gRPC-Streams können beide Paradigmen gut zuordnen und bieten eine enge Integration mit .NET Core sowie reaktive und asynchrone Programmierstile.

>[!div class="step-by-step"]
>[VorherigeS](streaming-versus-repeated.md)
>[Weiter](security.md)
