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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="7aed4-103">Erstellen von gRPC-Clientbibliotheken</span><span class="sxs-lookup"><span data-stu-id="7aed4-103">Create gRPC client libraries</span></span>

<span data-ttu-id="7aed4-104">Es ist nicht erforderlich, Clientbibliotheken für eine gRPC-Anwendung zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="7aed4-105">Sie können eine freigegebene Bibliothek mit `.proto` Dateien in Ihrer Organisation erstellen, und andere Teams können diese Dateien verwenden, um Clientcode in ihren eigenen Projekten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7aed4-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="7aed4-106">Wenn Sie jedoch über ein privates NuGet-Repository verfügen und viele andere Teams .NET Core verwenden, können Sie NuGet-Clientpakete als Teil Ihres Serviceprojekts erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="7aed4-107">Dies kann eine gute Möglichkeit sein, Ihren Dienst zu teilen und zu bewerben.</span><span class="sxs-lookup"><span data-stu-id="7aed4-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="7aed4-108">Ein Vorteil der Verteilung einer Clientbibliothek besteht darin, dass Sie die generierten gRPC- und Protobuf-Klassen mit hilfreichen "Convenience"-Methoden und -Eigenschaften erweitern können.</span><span class="sxs-lookup"><span data-stu-id="7aed4-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="7aed4-109">Im Clientcode werden, wie auch im Server, `partial`alle Klassen als deklariert, sodass Sie sie erweitern können, ohne den generierten Code zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7aed4-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="7aed4-110">Dies bedeutet, dass es einfach ist, Konstruktoren, Methoden und berechnete Eigenschaften zu den Basistypen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="7aed4-111">Sie sollten keinen benutzerdefinierten Code verwenden, um wesentliche Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="7aed4-112">Sie möchten diese wesentlichen Funktionen nicht auf .NET-Teams beschränken, die die freigegebene Bibliothek verwenden, und sie nicht Für Teams bereitstellen, die andere Sprachen oder Plattformen wie Python oder Java verwenden.</span><span class="sxs-lookup"><span data-stu-id="7aed4-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="7aed4-113">Stellen Sie sicher, dass so viele Teams wie möglich auf Ihren gRPC-Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7aed4-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="7aed4-114">Der beste Weg, dies `.proto` zu tun, ist Dateien freizugeben, damit Entwickler ihre eigenen Clients generieren können.</span><span class="sxs-lookup"><span data-stu-id="7aed4-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="7aed4-115">Dies gilt insbesondere für eine Umgebung mit mehreren Plattformen, in der verschiedene Teams häufig unterschiedliche Programmiersprachen und Frameworks verwenden oder in der Ihre API extern zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="7aed4-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="7aed4-116">Nützliche Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="7aed4-116">Useful extensions</span></span>

<span data-ttu-id="7aed4-117">Es gibt zwei häufig verwendete Schnittstellen in .NET <xref:System.Collections.Generic.IEnumerable%601> für <xref:System.IObservable%601>den Umgang mit Datenströmen von Objekten: und .</span><span class="sxs-lookup"><span data-stu-id="7aed4-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="7aed4-118">Beginnend mit .NET Core 3.0 und C-8.0 gibt es eine <xref:System.Collections.Generic.IAsyncEnumerable%601> Schnittstelle `await foreach` zum asynchronen Verarbeiten von Streams und eine Syntax für die Verwendung der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7aed4-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="7aed4-119">In diesem Abschnitt wird wiederverwendbarer Code zum Anwenden dieser Schnittstellen auf gRPC-Streams dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7aed4-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="7aed4-120">Mit den .NET Core gRPC-Clientbibliotheken `ReadAllAsync` gibt `IAsyncStreamReader<T>` es eine `IAsyncEnumerable<T>` Erweiterungsmethode, die eine Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="7aed4-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="7aed4-121">Für Entwickler, die reaktive Programmierung verwenden, `IObservable<T>` könnte eine gleichwertige Erweiterungsmethode zum Erstellen einer Schnittstelle wie das Beispiel im folgenden Abschnitt aussehen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="7aed4-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="7aed4-122">IObservable</span></span>

<span data-ttu-id="7aed4-123">Die `IObservable<T>` Schnittstelle ist die "reaktive" Umkehrung von `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="7aed4-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="7aed4-124">Anstatt Elemente aus einem Stream zu ziehen, ermöglicht der reaktive Ansatz, dass der Stream Elemente an einen Abonnenten überträgt.</span><span class="sxs-lookup"><span data-stu-id="7aed4-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="7aed4-125">Dies ist sehr ähnlich zu gRPC-Streams, `IObservable<T>` und es `IAsyncStreamReader<T>` ist einfach, eine Schnittstelle um eine Schnittstelle zu wickeln.</span><span class="sxs-lookup"><span data-stu-id="7aed4-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="7aed4-126">Dieser Code ist `IAsyncEnumerable<T>` länger als der Code, da die Datei für die Arbeit mit Beobachtbaren nicht integriert ist.</span><span class="sxs-lookup"><span data-stu-id="7aed4-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="7aed4-127">Sie müssen die Implementierungsklasse manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="7aed4-128">Es ist jedoch eine generische Klasse, sodass eine einzelne Implementierung für alle Typen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7aed4-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="7aed4-129">Diese beobachtbare `Subscribe` Implementierung ermöglicht es, die Methode nur einmal aufzuführen, da mehrere Abonnenten versuchen würden, aus dem Stream zu lesen, was zu Chaos führen würde.</span><span class="sxs-lookup"><span data-stu-id="7aed4-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="7aed4-130">Es gibt Operatoren, z. `Replay` B. in Der [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), die Pufferung und wiederholbare Freigabe von Beobachtbaren ermöglichen, die mit dieser Implementierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7aed4-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="7aed4-131">Die `GrpcStreamSubscription` Klasse behandelt die Aufzählung `IAsyncStreamReader`von :</span><span class="sxs-lookup"><span data-stu-id="7aed4-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="7aed4-132">Alles, was jetzt erforderlich ist, ist eine einfache Erweiterungsmethode, um das Beobachtbare aus dem Streamleser zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7aed4-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="7aed4-133">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7aed4-133">Summary</span></span>

<span data-ttu-id="7aed4-134">Die `IAsyncEnumerable` `IObservable` und Modelle sind sowohl gut unterstützte als auch gut dokumentierte Methoden zum Umgang mit asynchronen Datenströmen in .NET.</span><span class="sxs-lookup"><span data-stu-id="7aed4-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="7aed4-135">gRPC-Streams können beide Paradigmen gut zuordnen und bieten eine enge Integration mit .NET Core sowie reaktive und asynchrone Programmierstile.</span><span class="sxs-lookup"><span data-stu-id="7aed4-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7aed4-136">[VorherigeS](streaming-versus-repeated.md)
>[Weiter](security.md)</span><span class="sxs-lookup"><span data-stu-id="7aed4-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
