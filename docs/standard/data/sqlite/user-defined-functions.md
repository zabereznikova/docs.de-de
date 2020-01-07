---
title: Benutzerdefinierte Funktionen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie benutzerdefinierte skalare und Aggregatfunktionen erstellen.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450411"
---
# <a name="user-defined-functions"></a><span data-ttu-id="7a3ac-103">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-103">User-defined functions</span></span>

<span data-ttu-id="7a3ac-104">Die meisten Datenbanken verfügen über einen prozeduralen Dialekt von SQL, den Sie verwenden können, um eigene Funktionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="7a3ac-105">SQLite wird jedoch in-Process mit ihrer app ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="7a3ac-106">Anstatt einen neuen Dialekt von SQL erlernen zu müssen, können Sie einfach die Programmiersprache Ihrer APP verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="7a3ac-107">Skalarfunktionen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-107">Scalar functions</span></span>

<span data-ttu-id="7a3ac-108">Skalare Funktionen geben einen einzelnen Skalarwert für jede Zeile in einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="7a3ac-109">Definieren Sie neue Skalarfunktionen, und überschreiben Sie die integrierten, indem Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="7a3ac-110">Eine Liste der unterstützten Parameter und Rückgabe Typen für das `func`-Argument finden Sie unter [Datentypen](types.md) .</span><span class="sxs-lookup"><span data-stu-id="7a3ac-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="7a3ac-111">Wenn Sie das `state`-Argument angeben, wird dieser Wert an jeden Aufruf der Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="7a3ac-112">Verwenden Sie dies, um Abschlüsse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-112">Use this to avoid closures.</span></span>

<span data-ttu-id="7a3ac-113">Geben Sie `isDeterministic` an, wenn ihre Funktion deterministisch ist, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="7a3ac-114">Im folgenden Beispiel wird gezeigt, wie Sie eine Skalarfunktion hinzufügen, um den Radius eines Zylinders zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="7a3ac-115">Operatoren</span><span class="sxs-lookup"><span data-stu-id="7a3ac-115">Operators</span></span>

<span data-ttu-id="7a3ac-116">Die folgenden SQLite-Operatoren werden durch entsprechende Skalarfunktionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="7a3ac-117">Wenn Sie diese Skalarfunktionen in Ihrer APP definieren, wird das Verhalten dieser Operatoren überschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="7a3ac-118">Operator</span><span class="sxs-lookup"><span data-stu-id="7a3ac-118">Operator</span></span>          | <span data-ttu-id="7a3ac-119">Funktion</span><span class="sxs-lookup"><span data-stu-id="7a3ac-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="7a3ac-120">X-glob-Y</span><span class="sxs-lookup"><span data-stu-id="7a3ac-120">X GLOB Y</span></span>          | <span data-ttu-id="7a3ac-121">glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7a3ac-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="7a3ac-122">X wie Y</span><span class="sxs-lookup"><span data-stu-id="7a3ac-122">X LIKE Y</span></span>          | <span data-ttu-id="7a3ac-123">Like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7a3ac-123">like(Y, X)</span></span>    |
| <span data-ttu-id="7a3ac-124">X wie Y Escape Z</span><span class="sxs-lookup"><span data-stu-id="7a3ac-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="7a3ac-125">Like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="7a3ac-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="7a3ac-126">X-Treffer Y</span><span class="sxs-lookup"><span data-stu-id="7a3ac-126">X MATCH Y</span></span>         | <span data-ttu-id="7a3ac-127">Match (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7a3ac-127">match(Y, X)</span></span>   |
| <span data-ttu-id="7a3ac-128">X regexp Y</span><span class="sxs-lookup"><span data-stu-id="7a3ac-128">X REGEXP Y</span></span>        | <span data-ttu-id="7a3ac-129">RegExp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7a3ac-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="7a3ac-130">Im folgenden Beispiel wird gezeigt, wie die regexp-Funktion definiert wird, um den entsprechenden-Operator zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="7a3ac-131">SQLite schließt keine Standard Implementierung der RegExp-Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="7a3ac-132">Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-132">Aggregate functions</span></span>

<span data-ttu-id="7a3ac-133">Aggregatfunktionen geben einen einzelnen aggregierten Wert für alle Zeilen in einer Abfrage zurück.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="7a3ac-134">Definieren und Überschreiben von Aggregatfunktionen mit <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="7a3ac-135">Das `seed`-Argument gibt den ursprünglichen Zustand des Kontexts an.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="7a3ac-136">Verwenden Sie diese Informationen, um auch keine Abschlüsse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="7a3ac-137">Das `func`-Argument wird einmal pro Zeile aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="7a3ac-138">Verwenden Sie den Kontext, um ein endgültiges Ergebnis zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="7a3ac-139">Gibt den Kontext zurück.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-139">Return the context.</span></span> <span data-ttu-id="7a3ac-140">Mit diesem Muster kann der Kontext ein Werttyp oder unveränderlich sein.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="7a3ac-141">Wenn keine `resultSelector` angegeben wird, wird der endgültige Zustand des Kontexts als Ergebnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="7a3ac-142">Dies kann die Definition von Funktionen wie Sum und count vereinfachen, die jeweils nur eine Zahl für jede Zeile erhöhen und zurückgeben müssen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="7a3ac-143">Geben Sie `resultSelector` an, um das Endergebnis aus dem Kontext zu berechnen, nachdem Sie alle Zeilen durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="7a3ac-144">Eine Liste der unterstützten Parametertypen für das `func` Argument und Rückgabe Typen für `resultSelector`finden Sie unter [Datentypen](types.md) .</span><span class="sxs-lookup"><span data-stu-id="7a3ac-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="7a3ac-145">Wenn Ihre Funktion deterministisch ist, geben Sie `isDeterministic` an, damit SQLite bei der Kompilierung von Abfragen zusätzliche Optimierungen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="7a3ac-146">Im folgenden Beispiel wird eine Aggregatfunktion definiert, um die Standardabweichung einer Spalte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="7a3ac-147">-Fehler</span><span class="sxs-lookup"><span data-stu-id="7a3ac-147">Errors</span></span>

<span data-ttu-id="7a3ac-148">Wenn eine benutzerdefinierte Funktion eine Ausnahme auslöst, wird die Nachricht an SQLite zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="7a3ac-149">SQLite löst dann einen Fehler aus, und Microsoft. Data. sqlite löst eine sqliteexception aus.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="7a3ac-150">Weitere Informationen finden Sie unter [Datenbankfehler](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="7a3ac-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="7a3ac-151">Standardmäßig ist der Fehler SQLite-Fehlercode SQLITE_ERROR (oder 1).</span><span class="sxs-lookup"><span data-stu-id="7a3ac-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="7a3ac-152">Sie können Sie jedoch ändern, indem Sie eine <xref:Microsoft.Data.Sqlite.SqliteException> in ihrer Funktion mit dem gewünschten <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> auslösen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="7a3ac-153">Debugging</span><span class="sxs-lookup"><span data-stu-id="7a3ac-153">Debugging</span></span>

<span data-ttu-id="7a3ac-154">SQLite ruft Ihre Implementierung direkt auf.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="7a3ac-155">Auf diese Weise können Sie Haltepunkte hinzufügen, die beim Auswerten von Abfragen durch SQLite auslöst werden.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="7a3ac-156">Die vollständige .net-Debuggingfunktion ist verfügbar, um Sie beim Erstellen benutzerdefinierter Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7a3ac-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a3ac-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a3ac-157">See also</span></span>

* [<span data-ttu-id="7a3ac-158">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-158">Data types</span></span>](types.md)
* [<span data-ttu-id="7a3ac-159">SQLite Core-Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="7a3ac-160">SQLite-Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="7a3ac-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
