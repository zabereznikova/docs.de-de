---
title: Verwenden von Indexern – C#-Programmierhandbuch
description: Erfahren Sie, wie Sie einen Indexer für eine Klasse, Struktur oder Schnittstelle in C# deklarieren und verwenden. Dieser Artikel enthält Beispielcode.
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: a8a9e05c1d2e44841177a924c6ff51c6c9e6a05a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301865"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="64bb2-104">Verwenden von Indexern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="64bb2-104">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="64bb2-105">Indexer sind ein syntaktisches Hilfsmittel, um Ihnen die Erstellung einer [Klasse](../../language-reference/keywords/class.md), [Struktur](../../language-reference/builtin-types/struct.md) oder [Schnittstelle](../../language-reference/keywords/interface.md) zu ermöglichen, auf die Clientanwendungen als Array zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="64bb2-105">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="64bb2-106">Der Compiler generiert die Eigenschaft `Item` (oder eine anders benannte Eigenschaft, wenn <xref:System.Runtime.CompilerServices.IndexerNameAttribute> vorhanden ist) und die entsprechenden Zugriffsmethoden.</span><span class="sxs-lookup"><span data-stu-id="64bb2-106">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="64bb2-107">Indexer werden am häufigsten in Typen implementiert, deren Hauptzweck darin besteht, eine interne Auflistung oder ein Array zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="64bb2-107">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="64bb2-108">Angenommen, Sie verfügen beispielsweise über eine Klasse namens `TempRecord` zur Darstellung der Temperatur in Fahrenheit zu 10 verschiedenen Zeitpunkten während eines 24-stündigen Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="64bb2-108">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="64bb2-109">Die Klasse enthält das Array `temps` vom Typ `float[]` zum Speichern der Temperaturwerte.</span><span class="sxs-lookup"><span data-stu-id="64bb2-109">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="64bb2-110">Durch die Implementierung eines Indexers in dieser Klasse können Clients auf die Temperaturen in einer `TempRecord`-Instanz als `float temp = tempRecord[4]` zugreifen, statt als `float temp = tempRecord.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="64bb2-110">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="64bb2-111">Die Indexernotation vereinfacht nicht nur die Syntax für Clientanwendungen. Sie ermöglicht es auch anderen Entwicklern, die Klasse und deren Zweck intuitiver zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="64bb2-111">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="64bb2-112">Um einen Indexer in einer Klasse oder Struktur zu deklarieren, verwenden Sie das [this](../../language-reference/keywords/this.md) -Schlüsselwort, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="64bb2-112">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="64bb2-113">Beim Deklarieren eines Indexers wird automatisch eine Eigenschaft mit dem Namen `Item` für das Objekt generiert.</span><span class="sxs-lookup"><span data-stu-id="64bb2-113">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="64bb2-114">Auf die Eigenschaft `Item` kann nicht direkt über den [Memberzugriffsausdruck](../../language-reference/operators/member-access-operators.md#member-access-expression-) der Instanz zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="64bb2-114">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="64bb2-115">Wenn Sie Ihre eigene Eigenschaft `Item` zu einem Objekt mit einem Indexer hinzufügen, wird außerdem der [Compilerfehler CS0102](../../misc/cs0102.md) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64bb2-115">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="64bb2-116">Verwenden Sie <xref:System.Runtime.CompilerServices.IndexerNameAttribute>, und benennen Sie den Indexer wie unten beschrieben um, um diesen Fehler zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="64bb2-116">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="64bb2-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64bb2-117">Remarks</span></span>

<span data-ttu-id="64bb2-118">Der Typ eines Indexers und der Typ seiner Parameter müssen zumindest dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst.</span><span class="sxs-lookup"><span data-stu-id="64bb2-118">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="64bb2-119">Weitere Informationen zu den Zugriffsebenen finden Sie unter [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="64bb2-119">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="64bb2-120">Weitere Informationen zum Verwenden von Indexern mit einer Schnittstelle finden Sie unter [Schnittstellenindexer](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="64bb2-120">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="64bb2-121">Die Signatur eines Indexers besteht aus der Anzahl und den Typen seiner formalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="64bb2-121">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="64bb2-122">Sie umfasst weder den Indexertyp noch die Namen der formalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="64bb2-122">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="64bb2-123">Wenn Sie mehrere Indexer in derselben Klasse deklarieren, müssen sie verschiedene Signaturen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="64bb2-123">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="64bb2-124">Ein Indexerwert wird nicht als Variable klassifiziert. Aus diesem Grund können Sie keinen Indexerwert als [Ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="64bb2-124">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="64bb2-125">Um für den Indexer einen Namen anzugeben, den andere Sprachen verwenden können, verwenden Sie <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="64bb2-125">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="64bb2-126">Dieser Indexer hat den Namen `TheItem`, da er vom Indexernamensattribut überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="64bb2-126">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="64bb2-127">Standardmäßig ist der Indexername `Item`.</span><span class="sxs-lookup"><span data-stu-id="64bb2-127">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="64bb2-128">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="64bb2-128">Example 1</span></span>

<span data-ttu-id="64bb2-129">Im folgenden Beispiel wird die Deklaration eines öffentlichen Arrayfelds, `temps`, und eines Indexers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="64bb2-129">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="64bb2-130">Der Indexer ermöglicht den direkten Zugriff auf die Instanz `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="64bb2-130">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="64bb2-131">Als Alternative zur Verwendung des Indexers, kann das Array als [öffentliches](../../language-reference/keywords/public.md) Mitglied deklariert und direkt auf dessen Mitglieder, `tempRecord.temps[i]`, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="64bb2-131">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="64bb2-132">Beachten Sie, dass, wenn der Zugriff eines Indexers, z.B. in einer `Console.Write`-Anweisung ausgewertet wird, der [get](../../language-reference/keywords/get.md)-Accessor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="64bb2-132">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="64bb2-133">Wenn kein `get`-Accessor vorhanden ist, tritt deshalb ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="64bb2-133">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="64bb2-134">Indizieren mit anderen Werten</span><span class="sxs-lookup"><span data-stu-id="64bb2-134">Indexing using other values</span></span>

<span data-ttu-id="64bb2-135">C# beschränkt den Indexer-Parametertyp nicht auf Integer.</span><span class="sxs-lookup"><span data-stu-id="64bb2-135">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="64bb2-136">Beispielsweise kann es sinnvoll sein, eine Zeichenfolge mit einem Indexer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="64bb2-136">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="64bb2-137">Ein solcher Indexer kann implementiert werden, indem die Zeichenfolge in der Auflistung gesucht und der richtige Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64bb2-137">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="64bb2-138">Da Zugriffsmethoden überladen werden können, können die Zeichenfolgen- und die Integer-Version gleichzeitig vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="64bb2-138">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="64bb2-139">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="64bb2-139">Example 2</span></span>

<span data-ttu-id="64bb2-140">Das folgende Beispiel deklariert eine Klasse, die die Wochentage speichert.</span><span class="sxs-lookup"><span data-stu-id="64bb2-140">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="64bb2-141">Ein `get`-Accessor akzeptiert eine Zeichenfolge – den Namen eines Tages – und gibt den entsprechenden Integer-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="64bb2-141">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="64bb2-142">„Sunday“ gibt beispielsweise 0 zurück, „Monday“ 1 usw.</span><span class="sxs-lookup"><span data-stu-id="64bb2-142">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="64bb2-143">Verwendungsbeispiel 2</span><span class="sxs-lookup"><span data-stu-id="64bb2-143">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="64bb2-144">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="64bb2-144">Example 3</span></span>

<span data-ttu-id="64bb2-145">Im folgenden Beispiel wird eine Klasse deklariert, die die Wochentage mithilfe der Enumeration <xref:System.DayOfWeek?displayProperty=fullName> speichert.</span><span class="sxs-lookup"><span data-stu-id="64bb2-145">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="64bb2-146">Eine `get`-Zugriffsmethode akzeptiert `DayOfWeek` (den Wert für einen Tag) und gibt den entsprechenden Integer-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="64bb2-146">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="64bb2-147">Bei `DayOfWeek.Sunday` wird beispielsweise 0 zurückgegeben, bei `DayOfWeek.Monday` 1 und so weiter.</span><span class="sxs-lookup"><span data-stu-id="64bb2-147">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="64bb2-148">Verwendungsbeispiel 3</span><span class="sxs-lookup"><span data-stu-id="64bb2-148">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="64bb2-149">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="64bb2-149">Robust programming</span></span>

<span data-ttu-id="64bb2-150">Es gibt zwei grundlegende Möglichkeiten, mit denen die Sicherheit und die Zuverlässigkeit von Indexern verbessert werden kann:</span><span class="sxs-lookup"><span data-stu-id="64bb2-150">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="64bb2-151">Integrieren Sie irgendeine Form von Fehlerbehandlungsstrategie, für den Fall, dass Clientcode in einem ungültigen Indexwert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="64bb2-151">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="64bb2-152">Im ersten Beispiel weiter oben in diesem Thema stellt die TempRecord-Klasse eine Length-Eigenschaft bereit, die dem Clientcode ermöglicht, die Eingabe vor der Übergabe an den Indexer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="64bb2-152">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="64bb2-153">Sie können den Fehlerbehandlungscode auch in den Indexer selbst einfügen.</span><span class="sxs-lookup"><span data-stu-id="64bb2-153">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="64bb2-154">Achten Sie darauf alle Ausnahmen, die Sie innerhalb eines Indexeraccessors auslösen, für Benutzer zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="64bb2-154">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="64bb2-155">Schränken Sie den Zugriff auf die [get](../../language-reference/keywords/get.md)- und [set](../../language-reference/keywords/set.md)-Accessors so weit wie möglich ein.</span><span class="sxs-lookup"><span data-stu-id="64bb2-155">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="64bb2-156">Dies ist insbesondere wichtig für den `set`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="64bb2-156">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="64bb2-157">Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="64bb2-157">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64bb2-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64bb2-158">See also</span></span>

- [<span data-ttu-id="64bb2-159">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="64bb2-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="64bb2-160">Indexer</span><span class="sxs-lookup"><span data-stu-id="64bb2-160">Indexers</span></span>](./index.md)
- [<span data-ttu-id="64bb2-161">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="64bb2-161">Properties</span></span>](../classes-and-structs/properties.md)
