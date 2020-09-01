---
description: try-finally – C#-Referenz
title: try-finally – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 621c5bf1607136361b72f978681607ec2aec150f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141971"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="f76fa-103">try-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f76fa-103">try-finally (C# Reference)</span></span>

<span data-ttu-id="f76fa-104">Mit einem `finally`-Block können Sie alle Ressourcen bereinigen, die in einem [try](try-catch.md)-Block belegt sind, und Sie können Code selbst dann ausführen, wenn eine Ausnahme im `try`-Block auftritt.</span><span class="sxs-lookup"><span data-stu-id="f76fa-104">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="f76fa-105">In der Regel werden die Anweisungen eines `finally`-Blocks ausgeführt, wenn die Steuerung eine `try`-Anweisung verlässt.</span><span class="sxs-lookup"><span data-stu-id="f76fa-105">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="f76fa-106">Die Übertragung eines Steuerelements kann infolge einer normalen Ausführung, der Ausführung einer `break`-, `continue`-, `goto`- oder `return`-Anweisung oder der Weitergabe einer Ausnahme aus der `try`-Anweisung auftreten.</span><span class="sxs-lookup"><span data-stu-id="f76fa-106">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="f76fa-107">Innerhalb einer behandelten Ausnahme ist sichergestellt, dass der zugeordnete `finally`-Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f76fa-107">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="f76fa-108">Wenn die Ausnahme jedoch nicht behandelt wird, erfolgt die Ausführung des `finally`-Blocks je nachdem, wie der Entladevorgang für die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f76fa-108">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="f76fa-109">Das hängt wiederum davon ab, wie der Computer eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f76fa-109">That, in turn, is dependent on how your computer is set up.</span></span>

<span data-ttu-id="f76fa-110">Wenn eine Anwendung durch einen Ausnahmefehler beendet wird, ist es in der Regel nicht wichtig, ob der `finally`-Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f76fa-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="f76fa-111">Wenn der `finally`-Block jedoch Anweisungen aufweist, die auch in dieser Situation ausgeführt werden müssen, kann als Lösung ein `catch`-Block der `try`-`finally`-Anweisung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f76fa-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="f76fa-112">Sie können auch die Ausnahme abfangen, die möglicherweise im `try`-Block einer `try`-`finally`-Anweisung weiter oben in der Aufrufliste ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f76fa-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="f76fa-113">Die Ausnahme kann also in der Methode abgefangen werden, mit der die Methode mit der `try`-`finally`-Anweisung aufgerufen wird. Die Ausnahme kann aber auch in der Methode abgefangen werden, mit der diese Methode aufgerufen wird, oder in einer beliebigen Methode in der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="f76fa-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="f76fa-114">Wenn die Ausnahme nicht abgefangen wird, wird der `finally`-Block je nachdem, ob vom Betriebssystem ein Entladevorgang für die Ausnahme ausgelöst wird, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f76fa-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="f76fa-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f76fa-115">Example</span></span>

<span data-ttu-id="f76fa-116">Im folgenden Beispiel wird eine `System.InvalidCastException` Ausnahme durch eine ungültige Konvertierungsanweisung verursacht.</span><span class="sxs-lookup"><span data-stu-id="f76fa-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="f76fa-117">Die Ausnahme wird nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="f76fa-117">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="f76fa-118">Im folgenden Beispiel wird eine Ausnahme von der `TryCast`-Methode in einer Methode weiter oben in der Aufrufliste abgefangen.</span><span class="sxs-lookup"><span data-stu-id="f76fa-118">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="f76fa-119">Weitere Informationen zu `finally` finden Sie unter [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="f76fa-119">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="f76fa-120">C# enthält auch die [Using-Anweisung](using-statement.md), die eine ähnliche Funktionalität für <xref:System.IDisposable>-Objekte in einer zweckmäßigen Syntax bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f76fa-120">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f76fa-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f76fa-121">C# language specification</span></span>

<span data-ttu-id="f76fa-122">Weitere Informationen finden Sie im Abschnitt [Die Try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f76fa-122">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f76fa-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f76fa-123">See also</span></span>

- [<span data-ttu-id="f76fa-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f76fa-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f76fa-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f76fa-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f76fa-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f76fa-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f76fa-127">try-, throw- und catch-Anweisungen (C++)</span><span class="sxs-lookup"><span data-stu-id="f76fa-127">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="f76fa-128">throw</span><span class="sxs-lookup"><span data-stu-id="f76fa-128">throw</span></span>](throw.md)
- [<span data-ttu-id="f76fa-129">try-catch</span><span class="sxs-lookup"><span data-stu-id="f76fa-129">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="f76fa-130">How to: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f76fa-130">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
