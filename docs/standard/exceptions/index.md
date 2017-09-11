---
title: "Behandeln und Auslösen von Ausnahmen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d44996042d167c029291f2b454dc1a22cfbcfb4
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="589c0-102">Behandeln und Auslösen von Ausnahmen in .NET</span><span class="sxs-lookup"><span data-stu-id="589c0-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="589c0-103">Anwendungen müssen in der Lage sein, Fehler zu behandeln, die während der Ausführung konsistent auftreten. </span><span class="sxs-lookup"><span data-stu-id="589c0-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="589c0-104">.NET bietet ein Modell, um Anwendungen auf einheitliche Weise über Fehler zu benachrichtigen: .NET-Vorgänge geben Fehler durch Auslösen von Ausnahmen an.</span><span class="sxs-lookup"><span data-stu-id="589c0-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="589c0-105">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-105">Exceptions</span></span>

<span data-ttu-id="589c0-106">Bei einer Ausnahme handelt es sich um einen Fehlerzustand oder unerwartetes Verhalten beim Ausführen eines Programms.</span><span class="sxs-lookup"><span data-stu-id="589c0-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="589c0-107">Ausnahmen können durch Fehler in Ihrem oder in aufgerufenem Code (z.B. bei freigegebenen Bibliotheken), nicht verfügbare Betriebssystemressourcen, unerwartete, von der Runtime festgestellte Fehlerzustände (z.B. durch nicht überprüfbaren Code) und andere Ereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="589c0-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that cannot be verified), and so on.</span></span> <span data-ttu-id="589c0-108">Anwendungen können in einigen, aber nicht allen Fällen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="589c0-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="589c0-109">Obwohl bei den meisten Anwendungsausnahmen eine Wiederherstellung möglich ist, ist dies beim Großteil der Laufzeitausnahmen nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="589c0-109">Although you can recover from most application exceptions, you cannot recover from most runtime exceptions.</span></span>

<span data-ttu-id="589c0-110">In .NET stellt eine Ausnahme ein Objekt dar, das von der [System.Exception](xref:System.Exception)-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="589c0-110">In .NET, an exception is an object that inherits from the [System.Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="589c0-111">Eine Ausnahme wird in einem Codebereich ausgelöst, in dem ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="589c0-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="589c0-112">Die Ausnahme bleibt solange im Stapel, bis sie durch die Anwendung behandelt oder das Programm beendet wird.</span><span class="sxs-lookup"><span data-stu-id="589c0-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="589c0-113">Ausnahmen vs. herkömmliche Fehlerbehandlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="589c0-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="589c0-114">Herkömmliche Modelle der Fehlerbehandlung in Sprachen beruhten bisher entweder auf eigenen sprachenabhängigen Methoden der Fehlererkennung und -behandlung oder auf dem Fehlerbehandlungsmechanismus des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="589c0-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="589c0-115">Die Art und Weise, in der die Ausnahmebehandlung in .NET implementiert ist, bietet folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="589c0-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="589c0-116">Das Auslösen und Behandeln von Ausnahmen funktioniert für alle .NET-Programmiersprachen gleich.</span><span class="sxs-lookup"><span data-stu-id="589c0-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="589c0-117">Eine besondere Sprachsyntax ist für die Ausnahmebehandlung nicht erforderlich, trotzdem kann jede Sprache ihre eigene Syntax definieren.</span><span class="sxs-lookup"><span data-stu-id="589c0-117">Does not require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="589c0-118">Ausnahmen können prozess- und sogar computerübergreifend ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="589c0-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="589c0-119">Einer Anwendung kann Ausnahmebehandlungscode hinzugefügt werden, um die Programmzuverlässigkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="589c0-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="589c0-120">Ausnahmen bieten verschiedene Vorteile gegenüber anderen Methoden zur Fehlerbenachrichtigung, z.B. Rückgabecodes.</span><span class="sxs-lookup"><span data-stu-id="589c0-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="589c0-121">Fehler bleiben nicht unerkannt, da die Runtime Ihre Anwendung beendet, wenn eine Ausnahme ausgelöst wurde und diese nicht behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="589c0-121">Failures do not go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="589c0-122">Ungültige Werte werden nicht weiter im System weitergegeben – was passieren kann, wenn im Code nicht geprüft wird, ob ein Fehlerrückgabecode vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="589c0-122">Invalid values do not continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span> 

## <a name="common-exceptions"></a><span data-ttu-id="589c0-123">Allgemeine Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-123">Common Exceptions</span></span>

<span data-ttu-id="589c0-124">In der folgenden Tabelle sind einige allgemeine Ausnahmen sowie Beispiele aufgeführt, die die Ausnahmen verursachen können.</span><span class="sxs-lookup"><span data-stu-id="589c0-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="589c0-125">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="589c0-125">Exception type</span></span> | <span data-ttu-id="589c0-126">Basistyp</span><span class="sxs-lookup"><span data-stu-id="589c0-126">Base type</span></span> | <span data-ttu-id="589c0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="589c0-127">Description</span></span> | <span data-ttu-id="589c0-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="589c0-128">Example</span></span> |
| -------------- | --------- | ----------- | ------- |
| @System.Exception | @System.Object | <span data-ttu-id="589c0-129">Die Basisklasse für alle Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="589c0-129">Base class for all exceptions.</span></span> | <span data-ttu-id="589c0-130">Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="589c0-130">None (use a derived class of this exception).</span></span> |
| @System.IndexOutOfRangeException | @System.Exception | <span data-ttu-id="589c0-131">Wird von der Runtime nur dann ausgelöst, wenn ein Array falsch indiziert ist.</span><span class="sxs-lookup"><span data-stu-id="589c0-131">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="589c0-132">Indizieren eines Arrays außerhalb seines gültigen Bereichs: `arr[arr.Length+1]`</span><span class="sxs-lookup"><span data-stu-id="589c0-132">Indexing an array outside its valid range: `arr[arr.Length+1]`</span></span> |
| @System.NullReferenceException | @System.Exception | <span data-ttu-id="589c0-133">Wird von der Runtime nur dann ausgelöst, wenn auf ein NULL-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="589c0-133">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null; o.ToString();` |
| @System.InvalidOperationException | @System.Exception | <span data-ttu-id="589c0-134">Wird von Methoden ausgelöst, wenn ein ungültiger Status vorliegt.</span><span class="sxs-lookup"><span data-stu-id="589c0-134">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="589c0-135">Aufrufen von `Enumerator.GetNext()` nach Entfernen eines Elements aus der zugrunde liegenden Auflistung.</span><span class="sxs-lookup"><span data-stu-id="589c0-135">Calling `Enumerator.GetNext()` after removing an Item from the underlying collection.</span></span> |
| @System.ArgumentException | @System.Exception | <span data-ttu-id="589c0-136">Die Basisklasse für alle Argumentausnahmen.</span><span class="sxs-lookup"><span data-stu-id="589c0-136">Base class for all argument exceptions.</span></span> | <span data-ttu-id="589c0-137">Keines (verwenden Sie eine abgeleitete Klasse dieser Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="589c0-137">None (use a derived class of this exception).</span></span> |
| @System.ArgumentNullException | @System.Exception | <span data-ttu-id="589c0-138">Wird von Methoden ausgelöst, bei denen ein Argument nicht gleich NULL sein darf.</span><span class="sxs-lookup"><span data-stu-id="589c0-138">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null; "Calculate".IndexOf (s);` |
| @System.ArgumentOutOfRangeException | @System.Exception | <span data-ttu-id="589c0-139">Wird von Methoden ausgelöst, die überprüfen, ob Argumente in einem angegebenen Bereich liegen.</span><span class="sxs-lookup"><span data-stu-id="589c0-139">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="589c0-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="589c0-140">See Also</span></span>

* [<span data-ttu-id="589c0-141">Exception-Klasse und Exception-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="589c0-141">Exception Class and Properties</span></span>](exception-class-and-properties.md)
* [<span data-ttu-id="589c0-142">Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-142">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [<span data-ttu-id="589c0-143">Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block</span><span class="sxs-lookup"><span data-stu-id="589c0-143">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
* [<span data-ttu-id="589c0-144">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-144">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
* [<span data-ttu-id="589c0-145">Gewusst wie: Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-145">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
* [<span data-ttu-id="589c0-146">Verwenden benutzergefilterter Ausnahmehandler</span><span class="sxs-lookup"><span data-stu-id="589c0-146">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
* [<span data-ttu-id="589c0-147">Gewusst wie: Verwenden von Finally-Blöcken</span><span class="sxs-lookup"><span data-stu-id="589c0-147">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
* [<span data-ttu-id="589c0-148">Behandeln von COM-Interop-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-148">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
* [<span data-ttu-id="589c0-149">Bewährte Methoden für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="589c0-149">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)

<span data-ttu-id="589c0-150">Weitere Informationen zur Funktionsweise von Ausnahmen in .NET finden Sie in [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Was jeder Entwickler über Ausnahmen in der Runtime wissen muss).</span><span class="sxs-lookup"><span data-stu-id="589c0-150">To learn more about how exceptions work in .NET, see [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md).</span></span>

