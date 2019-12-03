---
title: 'Erstellen von GrpC-Client Bibliotheken: GrpC für WCF-Entwickler'
description: Erörterung von freigegebenen Client Bibliotheken/-Paketen für GrpC-Dienste
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711459"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="81933-103">Erstellen von GrpC-Client Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="81933-103">Create gRPC client libraries</span></span>

<span data-ttu-id="81933-104">Es ist nicht erforderlich, Client Bibliotheken für eine GrpC-Anwendung zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="81933-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="81933-105">Sie können eine freigegebene Bibliothek von `.proto` Dateien in Ihrer Organisation erstellen, und andere Teams können diese Dateien verwenden, um Client Code in ihren eigenen Projekten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="81933-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="81933-106">Wenn Sie jedoch über ein privates nuget-Repository verfügen und viele andere Teams .net Core verwenden, können Sie Client-nuget-Pakete im Rahmen Ihres Dienst Projekts erstellen und veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="81933-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="81933-107">Dies kann eine gute Möglichkeit zum Freigeben und herauf Stufen Ihres Dienstanbieter sein.</span><span class="sxs-lookup"><span data-stu-id="81933-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="81933-108">Ein Vorteil der Verteilung einer Client Bibliothek besteht darin, dass Sie die generierten GrpC-und protobuf-Klassen mit nützlichen Methoden und Eigenschaften verbessern können.</span><span class="sxs-lookup"><span data-stu-id="81933-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="81933-109">Im Client Code, wie auf dem Server, werden alle Klassen als `partial`deklariert, sodass Sie Sie erweitern können, ohne den generierten Code zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="81933-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="81933-110">Dies bedeutet, dass es einfach ist, den Grundtypen Konstruktoren, Methoden und berechnete Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="81933-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="81933-111">Sie sollten keinen benutzerdefinierten Code verwenden, um wesentliche Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="81933-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="81933-112">Sie möchten diese wesentlichen Funktionen nicht auf .NET-Teams beschränken, die die freigegebene Bibliothek verwenden, und Sie nicht für Teams bereitstellen, die andere Sprachen oder Plattformen wie Python oder Java verwenden.</span><span class="sxs-lookup"><span data-stu-id="81933-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="81933-113">Stellen Sie sicher, dass so viele Teams wie möglich auf Ihren GrpC-Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="81933-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="81933-114">Die beste Möglichkeit hierfür ist die Freigabe von `.proto` Dateien, damit Entwickler ihre eigenen Clients generieren können.</span><span class="sxs-lookup"><span data-stu-id="81933-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="81933-115">Dies gilt insbesondere in einer Umgebung mit mehreren Plattformen, in der unterschiedliche Teams häufig verschiedene Programmiersprachen und-Frameworks verwenden, oder wenn die API Extern zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="81933-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="81933-116">Nützliche Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="81933-116">Useful extensions</span></span>

<span data-ttu-id="81933-117">Für den Umgang mit Objekten von Objekten gibt es zwei häufig verwendete Schnittstellen in .net: <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="81933-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="81933-118">Ab .net Core 3,0 und C# 8,0 gibt es eine <xref:System.Collections.Generic.IAsyncEnumerable%601>-Schnittstelle für die asynchrone Verarbeitung von Streams und eine `await foreach` Syntax für die Verwendung der-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="81933-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="81933-119">Dieser Abschnitt enthält wiederverwendbaren Code zum Anwenden dieser Schnittstellen auf GrpC-Streams.</span><span class="sxs-lookup"><span data-stu-id="81933-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="81933-120">Mit den .net Core-GrpC-Client Bibliotheken gibt es eine `ReadAllAsync` Erweiterungsmethode für `IAsyncStreamReader<T>`, die eine `IAsyncEnumerable<T>`-Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="81933-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="81933-121">Für Entwickler, die reaktive Programmierung verwenden, könnte eine äquivalente Erweiterungsmethode zum Erstellen einer `IObservable<T>`-Schnittstelle wie im folgenden Abschnitt aussehen.</span><span class="sxs-lookup"><span data-stu-id="81933-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="81933-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="81933-122">IObservable</span></span>

<span data-ttu-id="81933-123">Die `IObservable<T>`-Schnittstelle ist die "reaktive" Umkehrung von `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="81933-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="81933-124">Anstatt Elemente aus einem Stream abzurufen, ermöglicht der reaktive Ansatz dem Stream das Übertragen von Push-Elementen an einen Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="81933-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="81933-125">Dies ist sehr ähnlich wie bei GrpC-Streams, und es ist einfach, eine `IObservable<T>`-Schnittstelle um eine `IAsyncStreamReader<T>` Schnittstelle zu umschließen.</span><span class="sxs-lookup"><span data-stu-id="81933-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="81933-126">Dieser Code ist länger als der `IAsyncEnumerable<T>`-Code, C# da nicht über eine integrierte Unterstützung für die Arbeit mit Observables verfügt.</span><span class="sxs-lookup"><span data-stu-id="81933-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="81933-127">Sie müssen die Implementierungs Klasse manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="81933-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="81933-128">Dabei handelt es sich jedoch um eine generische Klasse, sodass eine einzelne Implementierung über alle Typen hinweg funktioniert.</span><span class="sxs-lookup"><span data-stu-id="81933-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="81933-129">Diese Observable-Implementierung ermöglicht, dass die `Subscribe`-Methode nur einmal aufgerufen werden kann, da mehrere Abonnenten, die versuchen, aus dem Stream zu lesen, zu Chaos führen würden.</span><span class="sxs-lookup"><span data-stu-id="81933-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="81933-130">Es gibt Operatoren, wie z. b [. `Replay` in System. reaktivem. Linq](https://www.nuget.org/packages/System.Reactive.Linq), die die Pufferung und wiederholbare Freigabe von Observables ermöglichen, die mit dieser Implementierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="81933-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="81933-131">Die `GrpcStreamSubscription` Klasse behandelt die Enumeration des `IAsyncStreamReader`:</span><span class="sxs-lookup"><span data-stu-id="81933-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="81933-132">Dies ist nun eine einfache Erweiterungsmethode, mit der das Observable-Objekt aus dem StreamReader erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="81933-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="81933-133">Summary</span><span class="sxs-lookup"><span data-stu-id="81933-133">Summary</span></span>

<span data-ttu-id="81933-134">Die `IAsyncEnumerable`-und `IObservable` Modelle sind sowohl gut unterstützte als auch gut dokumentierte Möglichkeiten, mit asynchronen Datenströmen in .net umzugehen.</span><span class="sxs-lookup"><span data-stu-id="81933-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="81933-135">GrpC-Streams sind sowohl für Paradigmen als auch für eine enge Integration mit .net Core und für reaktive und asynchrone Programmier Stile gleich.</span><span class="sxs-lookup"><span data-stu-id="81933-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="81933-136">[Zurück](streaming-versus-repeated.md)
>[Weiter](security.md)</span><span class="sxs-lookup"><span data-stu-id="81933-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
