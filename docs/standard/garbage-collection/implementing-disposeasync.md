---
title: Implementieren einer DisposeAsync-Methode
description: Hier erfahren Sie, wie Sie die Methoden „DisposeAsync“ und „DisposeAsyncCore“ implementieren, um eine asynchrone Ressourcenbereinigung durchzuführen.
author: IEvangelist
ms.author: dapine
ms.date: 08/25/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 268cea7584040ad92e2da75e5e03112480cda93c
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053177"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="25942-103">Implementieren einer DisposeAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="25942-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="25942-104">Dies <xref:System.IAsyncDisposable?displayProperty=nameWithType>-Schnittstelle wurde als Teil von C# 8.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="25942-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="25942-105">Sie implementieren die <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Methode, wenn Sie eine Ressourcenbereinigung durchführen müssen, genauso wie bei [der Implementierung einer Dispose-Methode](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="25942-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="25942-106">Einer der Hauptunterschiede besteht jedoch darin, dass diese Implementierung asynchrone Bereinigungsvorgänge zulässt.</span><span class="sxs-lookup"><span data-stu-id="25942-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="25942-107"><xref:System.IAsyncDisposable.DisposeAsync> gibt eine <xref:System.Threading.Tasks.ValueTask> zurück, die den asynchronen Dispose-Vorgang darstellt.</span><span class="sxs-lookup"><span data-stu-id="25942-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="25942-108">Bei der Implementierung der <xref:System.IAsyncDisposable>-Schnittstelle ist es typisch, dass Klassen auch die <xref:System.IDisposable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="25942-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="25942-109">Ein gutes Implementierungsmuster der <xref:System.IAsyncDisposable>-Schnittstelle besteht darin, sowohl auf den synchronen als auch auf den asynchronen Dispose-Vorgang vorbereitet zu sein.</span><span class="sxs-lookup"><span data-stu-id="25942-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="25942-110">Alle Anleitungen zum Implementieren des Dispose-Musters gelten auch für die asynchrone Implementierung.</span><span class="sxs-lookup"><span data-stu-id="25942-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="25942-111">In diesem Artikel wird davon ausgegangen, dass Sie bereits mit der [Implementierung einer Dispose-Methode](implementing-dispose.md) vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="25942-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="25942-112">DisposeAsync() und DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="25942-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="25942-113">Die <xref:System.IAsyncDisposable>-Schnittstelle deklariert eine einzelne parameterlose Methode: <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="25942-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="25942-114">Jede nicht versiegelte Klasse sollte über eine zusätzliche `DisposeAsyncCore()`-Methode verfügen, die ebenfalls eine <xref:System.Threading.Tasks.ValueTask> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="25942-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="25942-115">Eine `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Implementierung, die keine Parameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="25942-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="25942-116">Eine `protected virtual ValueTask DisposeAsyncCore()`-Methode mit der folgenden Signatur:</span><span class="sxs-lookup"><span data-stu-id="25942-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="25942-117">Die DisposeAsync()-Methode</span><span class="sxs-lookup"><span data-stu-id="25942-117">The DisposeAsync() method</span></span>

<span data-ttu-id="25942-118">Die `public` parameterlose `DisposeAsync()`-Methode wird implizit in einer `await using`-Anweisung aufgerufen, und ihr Zweck ist es, nicht verwaltete Ressourcen freizugeben, eine generelle Bereinigung durchzuführen und anzugeben, dass der Finalizer, sofern vorhanden, nicht ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="25942-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="25942-119">Das Freigeben des Speichers, der einem verwalteten Objekt zugeordnet ist, ist immer die Domäne des [Garbage Collectors](index.md).</span><span class="sxs-lookup"><span data-stu-id="25942-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="25942-120">Daher weist sie eine Standardimplementierung auf:</span><span class="sxs-lookup"><span data-stu-id="25942-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="25942-121">Ein primärer Unterschied im asynchronen Dispose-Muster im Vergleich zum Dispose-Muster besteht darin, dass dem Aufruf von <xref:System.IAsyncDisposable.DisposeAsync> an die `Dispose(bool)`-Überladungsmethode `false` als Argument übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="25942-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="25942-122">Beim Implementieren der <xref:System.IDisposable.Dispose?displayProperty=nameWithType>-Methode wird jedoch stattdessen `true` übergeben.</span><span class="sxs-lookup"><span data-stu-id="25942-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="25942-123">Dadurch wird die funktionale Äquivalenz mit dem synchronen Dispose-Muster sichergestellt, und es wird weiterhin sichergestellt, dass Finalizer-Codepfade auch noch aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="25942-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="25942-124">Mit anderen Worten: Die `DisposeAsyncCore()`-Methode gibt verwaltete Ressourcen asynchron frei, sodass Sie diese nicht auch noch synchron löschen sollten.</span><span class="sxs-lookup"><span data-stu-id="25942-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="25942-125">Rufen Sie daher `Dispose(false)` anstelle von `Dispose(true)` auf.</span><span class="sxs-lookup"><span data-stu-id="25942-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="25942-126">DisposeAsyncCore()-Methode</span><span class="sxs-lookup"><span data-stu-id="25942-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="25942-127">Die `DisposeAsyncCore()`-Methode ist dafür vorgesehen, die asynchrone Bereinigung verwalteter Ressourcen oder kaskadierende Aufrufe von `DisposeAsync()` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25942-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="25942-128">Sie kapselt die allgemeinen asynchronen Bereinigungsvorgänge, wenn eine Unterklasse eine Basisklasse erbt, die eine Implementierung von <xref:System.IAsyncDisposable> ist.</span><span class="sxs-lookup"><span data-stu-id="25942-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="25942-129">Die `DisposeAsyncCore()`-Methode ist `virtual`, damit abgeleitete Klassen zusätzliche Bereinigungen in ihren Außerkraftsetzungen definieren können.</span><span class="sxs-lookup"><span data-stu-id="25942-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="25942-130">Wenn eine Implementierung von <xref:System.IAsyncDisposable> `sealed` ist, wird die `DisposeAsyncCore()`-Methode nicht benötigt, und die asynchrone Bereinigung kann direkt in der <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Methode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="25942-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="25942-131">Implementieren des asynchronen Dispose-Musters</span><span class="sxs-lookup"><span data-stu-id="25942-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="25942-132">Alle nicht versiegelten Klassen sollten als potenzielle Basisklasse angesehen werden, da sie geerbt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="25942-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="25942-133">Wenn Sie das asynchrone Dispose-Muster für eine potenzielle Basisklasse implementieren, müssen Sie die `protected virtual ValueTask DisposeAsyncCore()`-Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="25942-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="25942-134">Im Folgenden finden Sie eine Beispielimplementierung des asynchronen Dispose-Musters, das eine <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="25942-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="25942-135">Im vorangehenden Beispiel wird <xref:System.Text.Json.Utf8JsonWriter> verwendet.</span><span class="sxs-lookup"><span data-stu-id="25942-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="25942-136">Weitere Informationen zu `System.Text.Json` finden Sie unter [Migration von Newtonsoft.Json zu System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="25942-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="25942-137">Verwenden von asynchron verwerfbar</span><span class="sxs-lookup"><span data-stu-id="25942-137">Using async disposable</span></span>

<span data-ttu-id="25942-138">Wenn Sie ein Objekt ordnungsgemäß nutzen zu können, das die <xref:System.IAsyncDisposable>-Schnittstelle implementiert, verwenden Sie die Schlüsselwörter [await](../../csharp/language-reference/operators/await.md) und [using](../../csharp/language-reference/keywords/using-statement.md) zusammen.</span><span class="sxs-lookup"><span data-stu-id="25942-138">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="25942-139">Sehen Sie sich das folgende Beispiel an, in dem die `ExampleAsyncDisposable`-Klasse instanziiert und dann von einer `await using`-Anweisung umschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="25942-139">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="25942-140">Verwenden Sie die <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>-Erweiterungsmethode der <xref:System.IAsyncDisposable>-Schnittstelle, um zu konfigurieren, wie die Fortsetzung der Aufgabe in ihrem ursprünglichen Kontext oder Scheduler gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="25942-140">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="25942-141">Weitere Informationen zu `ConfigureAwait` finden Sie in den [Häufig gestellten Fragen zu ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="25942-141">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="25942-142">In Situationen, in denen die Verwendung von `ConfigureAwait` nicht erforderlich ist, könnte die `await using`-Anweisung wie folgt vereinfacht werden:</span><span class="sxs-lookup"><span data-stu-id="25942-142">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="25942-143">Darüber hinaus könnte sie so geschrieben werden, dass Sie den impliziten Bereich einer [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) verwendet.</span><span class="sxs-lookup"><span data-stu-id="25942-143">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="25942-144">Gestapelte using-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="25942-144">Stacked usings</span></span>

<span data-ttu-id="25942-145">In Situationen, in denen Sie mehrere Objekte erstellen und verwenden, die <xref:System.IAsyncDisposable> implementieren, kann das Stapeln von `using`-Anweisungen in fehlgeleiteten Bedingungen Aufrufe von <xref:System.IAsyncDisposable.DisposeAsync> verhindern.</span><span class="sxs-lookup"><span data-stu-id="25942-145">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="25942-146">Um potenzielle Probleme zu verhindern, sollten Sie das Stapeln vermeiden und stattdessen dieses Beispielmuster verwenden:</span><span class="sxs-lookup"><span data-stu-id="25942-146">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="25942-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25942-147">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
