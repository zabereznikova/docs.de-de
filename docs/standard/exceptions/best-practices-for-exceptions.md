---
title: Best Practices für Ausnahmen – .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 1de231b01e3fa97e78a87ae6b0595a9b5536374e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160169"
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="74bff-102">Best Practices für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="74bff-102">Best practices for exceptions</span></span>

<span data-ttu-id="74bff-103">Eine ausgereifte App behandelt Ausnahmen und Fehler, um App-Abstürze zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="74bff-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="74bff-104">In diesem Abschnitt werden Best Practices für die Behandlung und Erstellung von Ausnahmen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74bff-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a><span data-ttu-id="74bff-105">Verwenden Sie Try/Catch/Finally-Blöcke zum Beheben von Fehlern oder zum Freigeben von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="74bff-105">Use try/catch/finally blocks to recover from errors or release resources</span></span>

<span data-ttu-id="74bff-106">Betten Sie Code, der Ausnahmen erzeugen kann, in `try`/`catch`-Blöcke ein, ***damit*** ihr Code nach diesen Ausnahmen wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="74bff-106">Use `try`/`catch` blocks around code that can potentially generate an exception ***and*** your code can recover from that exception.</span></span> <span data-ttu-id="74bff-107">Ordnen Sie Ausnahmen in `catch`-Blöcken immer von der am stärksten abgeleiteten zur am wenigsten abgeleiteten.</span><span class="sxs-lookup"><span data-stu-id="74bff-107">In `catch` blocks, always order exceptions from the most derived to the least derived.</span></span> <span data-ttu-id="74bff-108">Alle Ausnahmen sind von <xref:System.Exception> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="74bff-108">All exceptions derive from <xref:System.Exception>.</span></span> <span data-ttu-id="74bff-109">Stärker abgeleitete Ausnahmen werden nicht durch eine catch-Klausel verarbeitet, der eine catch-Klausel für eine Ausnahmebasisklasse vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="74bff-109">More derived exceptions are not handled by a catch clause that is preceded by a catch clause for a base exception class.</span></span> <span data-ttu-id="74bff-110">Wenn Ihr Code aus einer Ausnahme nicht wiederhergestellt werden kann, fangen Sie diese Ausnahme nicht ab.</span><span class="sxs-lookup"><span data-stu-id="74bff-110">When your code cannot recover from an exception, don't catch that exception.</span></span> <span data-ttu-id="74bff-111">Aktivieren Sie Methoden weiter oben in der Aufrufliste, um nach Möglichkeit eine Wiederherstellung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74bff-111">Enable methods further up the call stack to recover if possible.</span></span>

<span data-ttu-id="74bff-112">Bereinigen Sie die Ressourcen, die mit `using`-Anweisungen oder `finally`-Blöcken zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="74bff-112">Clean up resources allocated with either `using` statements, or `finally` blocks.</span></span> <span data-ttu-id="74bff-113">Bevorzugen Sie `using`-Anweisungen, um Ressourcen automatisch zu bereinigen, wenn Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="74bff-113">Prefer `using` statements to automatically clean up resources when exceptions are thrown.</span></span> <span data-ttu-id="74bff-114">Verwenden Sie `finally`-Blöcke, um Ressourcen zu bereinigen, die <xref:System.IDisposable> nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="74bff-114">Use `finally` blocks to clean up resources that don't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="74bff-115">Code in einer `finally`-Klausel wird fast immer – d. h. auch bei Auslösen einer Ausnahme – ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74bff-115">Code in a `finally` clause is almost always executed even when exceptions are thrown.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="74bff-116">Behandeln häufig auftretender Bedingungen ohne Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="74bff-116">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="74bff-117">Bedingungen, deren Auftreten wahrscheinlich ist, die aber möglicherweise eine Ausnahme auslösen, sollten Sie so behandeln, dass die Ausnahme vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="74bff-117">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="74bff-118">Wenn Sie z. B. versuchen, eine bereits geschlossene Verbindung erneut zu schließen, erhalten Sie eine `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="74bff-118">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="74bff-119">Dies können Sie verhindern, indem Sie eine `if`-Anweisung verwenden, um den Verbindungsstatus zu überprüfen, bevor Sie versuchen, die Verbindung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="74bff-119">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

<span data-ttu-id="74bff-120">Wenn Sie den Verbindungsstatus vor dem Schließen der Verbindung nicht überprüfen, können Sie die `InvalidOperationException` abfangen.</span><span class="sxs-lookup"><span data-stu-id="74bff-120">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

<span data-ttu-id="74bff-121">Die Wahl der Methode hängt von der erwarteten Häufigkeit des Ereignisses ab.</span><span class="sxs-lookup"><span data-stu-id="74bff-121">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="74bff-122">Verwenden Sie die Ausnahmebehandlung, wenn das Ereignis nicht sehr häufig auftritt, d.  h. wenn es wirklich ungewöhnlich ist und auf einen Fehler hinweist (z. B. ein unerwartetes Dateiende).</span><span class="sxs-lookup"><span data-stu-id="74bff-122">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="74bff-123">Wenn Sie die Ausnahmebehandlung verwenden, wird weniger Code in normalen Bedingungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74bff-123">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="74bff-124">Wenn das Ereignis regelmäßig auftritt und als Teil der normalen Programmausführung betrachtet werden kann, suchen Sie im Code nach Fehlerbedingungen.</span><span class="sxs-lookup"><span data-stu-id="74bff-124">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="74bff-125">Wenn Sie auf gängige Fehlerbedingungen prüfen, wird weniger Code ausgeführt, da Ausnahmen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="74bff-125">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="74bff-126">Entwerfen von Klassen mit dem Ziel, Ausnahmen zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="74bff-126">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="74bff-127">Eine Klasse kann Methoden oder Eigenschaften bereitstellen, mit deren Hilfe ein Aufruf vermieden werden kann, der andernfalls eine Ausnahme auslösen würde.</span><span class="sxs-lookup"><span data-stu-id="74bff-127">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="74bff-128">Beispielsweise stellt eine <xref:System.IO.FileStream>-Klasse Methoden bereit, mithilfe derer bestimmt werden kann, ob das Ende der Datei erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="74bff-128">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="74bff-129">Dadurch kann die Ausnahme vermieden werden, die andernfalls durch den Versuch ausgelöst würde, nach Erreichen des Dateiendes weiterzulesen.</span><span class="sxs-lookup"><span data-stu-id="74bff-129">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="74bff-130">Das folgende Beispiel zeigt, wie eine Datei bis zum Ende gelesen werden kann, ohne dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="74bff-130">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

<span data-ttu-id="74bff-131">Eine andere Möglichkeit zum Vermeiden von Ausnahmen besteht darin, bei sehr häufig auftretenden Fehlern NULL (oder einen Standardwert) zurückzugeben, statt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="74bff-131">Another way to avoid exceptions is to return null (or default) for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="74bff-132">Ein sehr häufig auftretender Fehler kann durchaus als normale Ablaufsteuerung betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="74bff-132">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="74bff-133">Indem Sie in diesen Fällen NULL (oder einen Standardwert) zurückgeben, minimieren Sie die Auswirkungen auf die Leistung einer App.</span><span class="sxs-lookup"><span data-stu-id="74bff-133">By returning null (or default) in these cases, you minimize the performance impact to an app.</span></span>

<span data-ttu-id="74bff-134">Ob Sie bei Werttypen `Nullable<T>` oder einen Standardwert als Fehlerindikator verwenden, richtet sich nach Ihrer speziellen App.</span><span class="sxs-lookup"><span data-stu-id="74bff-134">For value types, whether to use `Nullable<T>` or default as your error indicator is something to consider for your particular app.</span></span> <span data-ttu-id="74bff-135">Durch Verwendung von `Nullable<Guid>` wird `default` zu `null` statt zu `Guid.Empty`.</span><span class="sxs-lookup"><span data-stu-id="74bff-135">By using `Nullable<Guid>`, `default` becomes `null` instead of `Guid.Empty`.</span></span> <span data-ttu-id="74bff-136">Manchmal wird durch Hinzufügen von `Nullable<T>` klarer, ob ein Wert vorhanden oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="74bff-136">Some times, adding `Nullable<T>` can make it clearer when a value is present or absent.</span></span> <span data-ttu-id="74bff-137">Andererseits kann das Hinzufügen von `Nullable<T>` dazu führen, dass zusätzliche Fälle geprüft werden müssen, die eigentlich nicht notwendig sind und nur zu potenzielle Fehlerquellen führen.</span><span class="sxs-lookup"><span data-stu-id="74bff-137">Other times, adding `Nullable<T>` can create extra cases to check that aren't necessary, and only serve to create potential sources of errors.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="74bff-138">Auslösen von Ausnahmen statt Zurückgeben eines Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="74bff-138">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="74bff-139">Ausnahmen sorgen dafür, dass Fehler nicht unbemerkt bleiben, nur weil der aufrufende Code einen Rückgabecode nicht überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="74bff-139">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span>

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="74bff-140">Verwenden der vordefinierten .NET-Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="74bff-140">Use the predefined .NET exception types</span></span>

<span data-ttu-id="74bff-141">Verwenden Sie eine neue Ausnahmeklasse nur dann, wenn sich keine vordefinierte Klasse anbietet.</span><span class="sxs-lookup"><span data-stu-id="74bff-141">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="74bff-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74bff-142">For example:</span></span>

- <span data-ttu-id="74bff-143">Lösen Sie eine <xref:System.InvalidOperationException> immer dann aus, wenn aufgrund des aktuellen Status des Objekts weder ein Eigenschaftensatz noch ein Methodenaufruf geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="74bff-143">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="74bff-144">Lösen Sie eine <xref:System.ArgumentException> oder eine der von <xref:System.ArgumentException> abgeleiteten vordefinierten Klassen in dem Fall aus, dass ungültige Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="74bff-144">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="74bff-145">Verwenden des Worts `Exception` am Ende von Ausnahmeklassennamen</span><span class="sxs-lookup"><span data-stu-id="74bff-145">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="74bff-146">Wenn eine benutzerdefinierte Ausnahme erforderlich ist, benennen Sie diese entsprechend, und leiten Sie sie von der <xref:System.Exception>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="74bff-146">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="74bff-147">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74bff-147">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="74bff-148">Einschließen von drei Konstruktoren in benutzerdefinierte Ausnahmeklassen</span><span class="sxs-lookup"><span data-stu-id="74bff-148">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="74bff-149">Verwenden Sie beim Erstellen eigener Ausnahmeklassen mindestens die drei gängigen Konstruktoren: den parameterlosen Konstruktor, einen Konstruktor, der eine Zeichenfolgenmeldung entgegennimmt, und einen Konstruktor, der eine Zeichenfolgenmeldung und eine innere Ausnahme entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="74bff-149">Use at least the three common constructors when creating your own exception classes: the parameterless constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

- <span data-ttu-id="74bff-150"><xref:System.Exception.%23ctor>, der Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="74bff-150"><xref:System.Exception.%23ctor>, which uses default values.</span></span>

- <span data-ttu-id="74bff-151"><xref:System.Exception.%23ctor%28System.String%29>, der eine Zeichenfolgenmeldung entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="74bff-151"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>

- <span data-ttu-id="74bff-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, der eine Zeichenfolgenmeldung und eine interne Ausnahme entgegennimmt.</span><span class="sxs-lookup"><span data-stu-id="74bff-152"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>

<span data-ttu-id="74bff-153">Ein Beispiel finden Sie unter [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="74bff-153">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="74bff-154">Sicherstellen, dass Ausnahmedaten bei der Remoteausführung von Code verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="74bff-154">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="74bff-155">Stellen Sie beim Erstellen benutzerdefinierter Ausnahmen sicher, dass die Metadaten für die Ausnahmen für remote ausgeführten Code verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="74bff-155">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span>

<span data-ttu-id="74bff-156">In .NET-Implementierungen, die App-Domänen unterstützen, können Ausnahmen beispielsweise über mehrere App-Domänen hinweg auftreten.</span><span class="sxs-lookup"><span data-stu-id="74bff-156">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="74bff-157">Nehmen wir an, App-Domäne A erstellt App-Domäne B, und in App-Domäne B wird Code ausgeführt, der eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="74bff-157">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="74bff-158">Damit App-Domäne A die Ausnahme ordnungsgemäß abfängt und behandelt, muss sie die Assembly finden, in der die durch App-Domäne B ausgelöste Ausnahme enthalten ist. Wenn App-Domäne B eine Ausnahme auslöst, die in einer Assembly in ihrer Anwendungsbasis, nicht aber in der Anwendungsbasis von App-Domäne A enthalten ist, kann App-Domäne A die Ausnahme nicht finden. Daraufhin löst die Common Language Runtime eine <xref:System.IO.FileNotFoundException> aus.</span><span class="sxs-lookup"><span data-stu-id="74bff-158">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="74bff-159">Um diese Situation zu vermeiden, haben Sie zwei Möglichkeiten, die Assembly mit den Ausnahmeinformationen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="74bff-159">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="74bff-160">Sie legen die Assembly in einer gemeinsamen Anwendungsbasis ab, die von beiden App-Domänen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74bff-160">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="74bff-161">\- oder -</span><span class="sxs-lookup"><span data-stu-id="74bff-161">\- or -</span></span>

- <span data-ttu-id="74bff-162">Sofern die Domänen keine gemeinsame Anwendungsbasis verwenden, signieren Sie die Assembly, in der die Ausnahmeinformationen enthalten sind, mit einem starken Namen und legen sie in einem globalen Assemblycache ab.</span><span class="sxs-lookup"><span data-stu-id="74bff-162">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="74bff-163">Verwenden grammatisch korrekter Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="74bff-163">Use grammatically correct error messages</span></span>

<span data-ttu-id="74bff-164">Verfassen Sie klar verständliche Meldungen und achten Sie vor allem am Ende eines Satzes auf korrekte Satzzeichen.</span><span class="sxs-lookup"><span data-stu-id="74bff-164">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="74bff-165">Jeder Satz in der Zeichenfolge, der der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft zugeordnet ist, muss mit einem Punkt enden.</span><span class="sxs-lookup"><span data-stu-id="74bff-165">Each sentence in the string assigned to the <xref:System.Exception.Message?displayProperty=nameWithType> property should end in a period.</span></span> <span data-ttu-id="74bff-166">So ist der Satz „In der Protokolltabelle ist ein Überlauf aufgetreten.“</span><span class="sxs-lookup"><span data-stu-id="74bff-166">For example, "The log table has overflowed."</span></span> <span data-ttu-id="74bff-167">ein Beispiel für eine angemessene Meldungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="74bff-167">would be an appropriate message string.</span></span>

## <a name="include-a-localized-string-message-in-every-exception"></a><span data-ttu-id="74bff-168">Einschließen einer lokalisierten Meldungszeichenfolge in jede Ausnahme</span><span class="sxs-lookup"><span data-stu-id="74bff-168">Include a localized string message in every exception</span></span>

<span data-ttu-id="74bff-169">Die dem Benutzer angezeigte Fehlermeldung wird von der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft der ausgelösten Ausnahme abgeleitet, nicht vom Namen der Ausnahmeklasse.</span><span class="sxs-lookup"><span data-stu-id="74bff-169">The error message that the user sees is derived from the <xref:System.Exception.Message?displayProperty=nameWithType> property of the exception that was thrown, and not from the name of the exception class.</span></span> <span data-ttu-id="74bff-170">In der Regel können Sie der <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft einen Wert zuweisen, indem Sie die Meldungszeichenfolge an das `message`-Argument eines [Ausnahmekonstruktors](xref:System.Exception.%23ctor%2A) übergeben.</span><span class="sxs-lookup"><span data-stu-id="74bff-170">Typically, you assign a value to the <xref:System.Exception.Message?displayProperty=nameWithType>  property by passing the message string to the `message` argument of an [Exception constructor](xref:System.Exception.%23ctor%2A).</span></span>

<span data-ttu-id="74bff-171">Sie sollten für lokalisierte Anwendungen eine lokalisierte Meldungszeichenfolge für jede Ausnahme angeben, die Ihre Anwendung ausgeben könnte.</span><span class="sxs-lookup"><span data-stu-id="74bff-171">For localized applications, you should provide a localized message string for every exception that your application can throw.</span></span> <span data-ttu-id="74bff-172">Verwenden Sie Ressourcendateien, um lokalisierte Fehlermeldungen zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="74bff-172">You use resource files to provide localized error messages.</span></span> <span data-ttu-id="74bff-173">Weitere Informationen zum Lokalisieren von Anwendungen und zum Abrufen lokalisierter Zeichenfolgen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="74bff-173">For information on localizing applications and retrieving localized strings, see the following articles:</span></span>

- [<span data-ttu-id="74bff-174">Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen</span><span class="sxs-lookup"><span data-stu-id="74bff-174">How to: create user-defined exceptions with localized exception messages</span></span>](how-to-create-localized-exception-messages.md)
- [<span data-ttu-id="74bff-175">Ressourcen in Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="74bff-175">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="74bff-176">Bereitstellen zusätzlicher Eigenschaften in benutzerdefinierten Ausnahmen, sofern erforderlich</span><span class="sxs-lookup"><span data-stu-id="74bff-176">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="74bff-177">Geben Sie zusätzliche Eigenschaften für eine Ausnahme nur dann neben der benutzerdefinierten Meldungszeichenfolge an, wenn es ein programmgesteuertes Szenario gibt, in dem ein solcher Zusatz sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="74bff-177">Provide additional properties for an exception (in addition to the custom message string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="74bff-178">Beispielsweise gibt die <xref:System.IO.FileNotFoundException> die <xref:System.IO.FileNotFoundException.FileName>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="74bff-178">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="74bff-179">Platzieren von throw-Anweisungen in einer Weise, dass die Stapelüberwachung nützlich ist</span><span class="sxs-lookup"><span data-stu-id="74bff-179">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="74bff-180">Die Stapelüberwachung beginnt bei der Anweisung, bei der die Ausnahme ausgelöst wurde, und endet mit der `catch`-Anweisung, mit der die Ausnahme abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="74bff-180">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="74bff-181">Verwenden von Methoden zum Generieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="74bff-181">Use exception builder methods</span></span>

<span data-ttu-id="74bff-182">Häufig löst eine Klasse die jeweils gleiche Ausnahme an unterschiedlichen Stellen in der Implementierung aus.</span><span class="sxs-lookup"><span data-stu-id="74bff-182">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="74bff-183">Verwenden Sie Hilfsmethoden, die eine Ausnahme erstellen und zurückgeben, um ausufernden Code zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="74bff-183">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="74bff-184">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="74bff-184">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

<span data-ttu-id="74bff-185">In einigen Fällen ist es besser, eine Ausnahme mithilfe des zugehörigen Konstruktors zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74bff-185">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="74bff-186">Ein Beispiel hierfür ist eine globale Ausnahmeklasse wie etwa <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="74bff-186">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a><span data-ttu-id="74bff-187">Wiederherstellen des Status, wenn Methoden aufgrund von Ausnahmen nicht abgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="74bff-187">Restore state when methods don't complete due to exceptions</span></span>

<span data-ttu-id="74bff-188">Aufrufende Funktionen sollten erwarten können, dass beim Auslösen einer Ausnahme durch eine Methode keine Nebeneffekte auftreten.</span><span class="sxs-lookup"><span data-stu-id="74bff-188">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="74bff-189">Angenommen, Sie haben Code für Geldüberweisungen geschrieben. Ihr Code bucht einen Betrag von einem Konto ab und schreibt ihn einem anderen Konto gut. Wenn nun beim Ausführen der Gutschrift eine Ausnahme ausgelöst wird, darf die Abbuchung natürlich nicht bestehen bleiben.</span><span class="sxs-lookup"><span data-stu-id="74bff-189">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

<span data-ttu-id="74bff-190">Die obige Methode löst Ausnahmen nicht direkt aus, sondern muss defensiv geschrieben werden, damit, wenn die Gutschrift fehlschlägt, die Abbuchung rückgängig gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="74bff-190">The method above does not directly throw any exceptions, but must be written defensively so that if the deposit operation fails, the withdrawal is reversed.</span></span>

<span data-ttu-id="74bff-191">In dieser Situation besteht eine Möglichkeit darin, alle Ausnahmen abzufangen, die von der Gutschrifttransaktion ausgelöst wurden, und für die Abbuchung einen Rollback auszuführen.</span><span class="sxs-lookup"><span data-stu-id="74bff-191">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

<span data-ttu-id="74bff-192">Dieses Beispiel veranschaulicht die Verwendung von `throw`, um die ursprüngliche Ausnahme erneut auszulösen, damit aufrufende Funktionen die tatsächliche Ursache des Problems erkennen können, ohne die <xref:System.Exception.InnerException>-Eigenschaft untersuchen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="74bff-192">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="74bff-193">Eine Alternative besteht darin, eine neue Ausnahme auszulösen und die ursprüngliche Ausnahme als innere Ausnahme einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="74bff-193">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a><span data-ttu-id="74bff-194">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74bff-194">See also</span></span>

- [<span data-ttu-id="74bff-195">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="74bff-195">Exceptions</span></span>](index.md)
