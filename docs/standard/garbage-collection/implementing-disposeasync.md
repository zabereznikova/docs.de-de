---
title: Implementieren einer DisposeAsync-Methode
description: Hier erfahren Sie, wie Sie die Methoden „DisposeAsync“ und „DisposeAsyncCore“ implementieren, um eine asynchrone Ressourcenbereinigung durchzuführen.
author: IEvangelist
ms.author: dapine
ms.date: 10/26/2020
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 551dbc30f6f5c99c7bfa468d7d708789c06acb7b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827801"
---
# <a name="implement-a-disposeasync-method"></a>Implementieren einer DisposeAsync-Methode

Dies <xref:System.IAsyncDisposable?displayProperty=nameWithType>-Schnittstelle wurde als Teil von C# 8.0 eingeführt. Sie implementieren die <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Methode, wenn Sie eine Ressourcenbereinigung durchführen müssen, genauso wie bei [der Implementierung einer Dispose-Methode](implementing-dispose.md). Einer der Hauptunterschiede besteht jedoch darin, dass diese Implementierung asynchrone Bereinigungsvorgänge zulässt. <xref:System.IAsyncDisposable.DisposeAsync> gibt eine <xref:System.Threading.Tasks.ValueTask> zurück, die den asynchronen Dispose-Vorgang darstellt.

Bei der Implementierung der <xref:System.IAsyncDisposable>-Schnittstelle ist es typisch, dass Klassen auch die <xref:System.IDisposable>-Schnittstelle implementieren. Ein gutes Implementierungsmuster der <xref:System.IAsyncDisposable>-Schnittstelle besteht darin, sowohl auf den synchronen als auch auf den asynchronen Dispose-Vorgang vorbereitet zu sein. Alle Anleitungen zum Implementieren des Dispose-Musters gelten auch für die asynchrone Implementierung. In diesem Artikel wird davon ausgegangen, dass Sie bereits mit der [Implementierung einer Dispose-Methode](implementing-dispose.md) vertraut sind.

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() und DisposeAsyncCore()

Die <xref:System.IAsyncDisposable>-Schnittstelle deklariert eine einzelne parameterlose Methode: <xref:System.IAsyncDisposable.DisposeAsync>. Jede nicht versiegelte Klasse sollte über eine zusätzliche `DisposeAsyncCore()`-Methode verfügen, die ebenfalls eine <xref:System.Threading.Tasks.ValueTask> zurückgibt.

- Eine `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Implementierung, die keine Parameter aufweist.
- Eine `protected virtual ValueTask DisposeAsyncCore()`-Methode mit der folgenden Signatur:

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a>Die DisposeAsync()-Methode

Die `public` parameterlose `DisposeAsync()`-Methode wird implizit in einer `await using`-Anweisung aufgerufen, und ihr Zweck ist es, nicht verwaltete Ressourcen freizugeben, eine generelle Bereinigung durchzuführen und anzugeben, dass der Finalizer, sofern vorhanden, nicht ausgeführt werden muss. Das Freigeben des Speichers, der einem verwalteten Objekt zugeordnet ist, ist immer die Domäne des [Garbage Collectors](index.md). Daher weist sie eine Standardimplementierung auf:

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
> Ein primärer Unterschied im asynchronen Dispose-Muster im Vergleich zum Dispose-Muster besteht darin, dass dem Aufruf von <xref:System.IAsyncDisposable.DisposeAsync> an die `Dispose(bool)`-Überladungsmethode `false` als Argument übergeben wird. Beim Implementieren der <xref:System.IDisposable.Dispose?displayProperty=nameWithType>-Methode wird jedoch stattdessen `true` übergeben. Dadurch wird die funktionale Äquivalenz mit dem synchronen Dispose-Muster sichergestellt, und es wird weiterhin sichergestellt, dass Finalizer-Codepfade auch noch aufgerufen werden. Mit anderen Worten: Die `DisposeAsyncCore()`-Methode gibt verwaltete Ressourcen asynchron frei, sodass Sie diese nicht auch noch synchron löschen sollten. Rufen Sie daher `Dispose(false)` anstelle von `Dispose(true)` auf.

### <a name="the-disposeasynccore-method"></a>DisposeAsyncCore()-Methode

Die `DisposeAsyncCore()`-Methode ist dafür vorgesehen, die asynchrone Bereinigung verwalteter Ressourcen oder kaskadierende Aufrufe von `DisposeAsync()` auszuführen. Sie kapselt die allgemeinen asynchronen Bereinigungsvorgänge, wenn eine Unterklasse eine Basisklasse erbt, die eine Implementierung von <xref:System.IAsyncDisposable> ist. Die `DisposeAsyncCore()`-Methode ist `virtual`, damit abgeleitete Klassen zusätzliche Bereinigungen in ihren Außerkraftsetzungen definieren können.

> [!TIP]
> Wenn eine Implementierung von <xref:System.IAsyncDisposable> `sealed` ist, wird die `DisposeAsyncCore()`-Methode nicht benötigt, und die asynchrone Bereinigung kann direkt in der <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Methode ausgeführt werden.

## <a name="implement-the-async-dispose-pattern"></a>Implementieren des asynchronen Dispose-Musters

Alle nicht versiegelten Klassen sollten als potenzielle Basisklasse angesehen werden, da sie geerbt werden könnten. Wenn Sie das asynchrone Dispose-Muster für eine potenzielle Basisklasse implementieren, müssen Sie die `protected virtual ValueTask DisposeAsyncCore()`-Methode bereitstellen. Im Folgenden finden Sie eine Beispielimplementierung des asynchronen Dispose-Musters, das eine <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> verwendet.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

Im vorangehenden Beispiel wird <xref:System.Text.Json.Utf8JsonWriter> verwendet. Weitere Informationen zu `System.Text.Json` finden Sie unter [Migration von Newtonsoft.Json zu System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="implement-both-dispose-and-async-dispose-patterns"></a>Implementieren von Dispose-Mustern und asynchronen Dispose-Mustern

Möglicherweise müssen Sie sowohl die <xref:System.IDisposable>- als auch die <xref:System.IAsyncDisposable>-Schnittstelle implementieren, insbesondere wenn der Klassenbereich Instanzen dieser Implementierungen enthält. Dadurch wird sichergestellt, dass Bereinigungsaufrufe ordnungsgemäß kaskadiert werden können. Unten sehen Sie eine Beispielklasse, die beide Schnittstellen implementiert und die richtige Vorgehensweise beim Bereinigen veranschaulicht.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

Bei der <xref:System.IDisposable.Dispose?displayProperty=nameWithType>- und der <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>-Implementierung handelt es sich um einfache Codebausteine.

In der Überladungsmethode `Dispose(bool)` wird die <xref:System.IDisposable>-Instanz bedingt verworfen, wenn sie nicht den Wert `null` aufweist. Die <xref:System.IAsyncDisposable>-Instanz wird in <xref:System.IDisposable> umgewandelt. Wenn der Wert dieser Instanz auch nicht `null` ist, wird sie ebenfalls verworfen. Beiden Instanzen wird dann der Wert `null` zugewiesen.

Bei der `DisposeAsyncCore()`-Methode wird der gleiche logische Ansatz verfolgt. Wenn die <xref:System.IAsyncDisposable>-Instanz nicht `null` ist, wird auf ihren Aufruf von `DisposeAsync().ConfigureAwait(false)` gewartet. Wenn die <xref:System.IDisposable>-Instanz auch eine Implementierung von <xref:System.IAsyncDisposable> ist, wird sie auch asynchron verworfen. Beiden Instanzen wird dann der Wert `null` zugewiesen.

## <a name="using-async-disposable"></a>Verwenden von asynchron verwerfbar

Wenn Sie ein Objekt ordnungsgemäß nutzen können möchten, das die <xref:System.IAsyncDisposable>-Schnittstelle implementiert, verwenden Sie die Schlüsselwörter [await](../../csharp/language-reference/operators/await.md) und [using](../../csharp/language-reference/keywords/using-statement.md) zusammen. Sehen Sie sich das folgende Beispiel an, in dem die `ExampleAsyncDisposable`-Klasse instanziiert und dann von einer `await using`-Anweisung umschlossen wird.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Verwenden Sie die <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>-Erweiterungsmethode der <xref:System.IAsyncDisposable>-Schnittstelle, um zu konfigurieren, wie die Fortsetzung der Aufgabe in ihrem ursprünglichen Kontext oder Scheduler gemarshallt wird. Weitere Informationen zu `ConfigureAwait` finden Sie in den [Häufig gestellten Fragen zu ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

In Situationen, in denen die Verwendung von `ConfigureAwait` nicht erforderlich ist, könnte die `await using`-Anweisung wie folgt vereinfacht werden:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Darüber hinaus könnte sie so geschrieben werden, dass Sie den impliziten Bereich einer [using-Deklaration](../../csharp/whats-new/csharp-8.md#using-declarations) verwendet.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Gestapelte using-Anweisungen

In Situationen, in denen Sie mehrere Objekte erstellen und verwenden, die <xref:System.IAsyncDisposable> implementieren, kann das Stapeln von `await using`-Anweisungen mit <xref:System.Threading.Tasks.ValueTask.ConfigureAwait%2A> in fehlgeleiteten Bedingungen Aufrufe von <xref:System.IAsyncDisposable.DisposeAsync> verhindern. Sie sollten das Stapeln vermeiden, um sicherzustellen, dass <xref:System.IAsyncDisposable.DisposeAsync> immer aufgerufen wird. Die folgenden drei Codebeispiele zeigen akzeptable Muster, die stattdessen verwendet werden können.

### <a name="acceptable-pattern-one"></a>Akzeptables Muster 1

:::code language="csharp" id="one" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

Im vorherigen Beispiel ist der Bereich für die einzelnen asynchronen Bereinigungsvorgänge jeweils explizit unter dem `await using`-Block festgelegt. Der äußere Bereich wird dadurch definiert, wie `objOne` Klammern setzt und dabei `objTwo` umschließt. Insofern wird also zuerst `objTwo` und danach `objOne` gelöscht. Beide `IAsyncDisposable`-Instanzen warten auf ihre <xref:System.IAsyncDisposable.DisposeAsync>-Methoden, führen also den asynchronen Bereinigungsvorgang durch. Die Aufrufe werden geschachtelt, nicht gestapelt.

### <a name="acceptable-pattern-two"></a>Akzeptables Muster 2

:::code language="csharp" id="two" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

Im vorherigen Beispiel ist der Bereich für die einzelnen asynchronen Bereinigungsvorgänge jeweils explizit unter dem `await using`-Block festgelegt. Am Ende jedes Blocks wartet die entsprechende `IAsyncDisposable`-Instanz auf ihre <xref:System.IAsyncDisposable.DisposeAsync>-Methode, führt also den asynchronen Bereinigungsvorgang durch. Die Aufrufe erfolgen sequenziell, nicht gestapelt. In diesem Szenario wird zunächst `objOne` und dann `objTwo` gelöscht.

### <a name="acceptable-pattern-three"></a>Akzeptables Muster 3

:::code language="csharp" id="three" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

Im vorherigen Beispiel wird der Bereich für die einzelnen asynchronen Bereinigungsvorgänge implizit mit dem Methodenkörper festgelegt, in dem die Vorgänge jeweils enthalten sind. Am Ende des umschließenden Blocks führen die `IAsyncDisposable`-Instanzen die asynchronen Bereinigungsvorgänge durch. Die Ausführung erfolgt in umgekehrter Reihenfolge dazu, wie sie deklariert wurden, d. h. `objTwo` wird vor `objOne` gelöscht.

### <a name="unacceptable-pattern"></a>Unzulässiges Muster

Wenn vom `AnotherAsyncDisposable`-Konstruktor eine Ausnahme zurückgegeben wird, wird `objOne` nicht ordnungsgemäß gelöscht:

:::code language="csharp" id="dontdothis" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

> [!TIP]
> Vermeiden Sie dieses Muster, da es zu unerwartetem Verhalten führen kann.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
