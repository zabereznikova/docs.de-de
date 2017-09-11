---
title: try-finally (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 88b9960b8c026d1fcd8eed1815ade57422cd2a15
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="try-finally-c-reference"></a><span data-ttu-id="9a65e-102">try-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9a65e-102">try-finally (C# Reference)</span></span>
<span data-ttu-id="9a65e-103">Mit einem `finally`-Block können Sie alle Ressourcen bereinigen, die in einem [try](../../../csharp/language-reference/keywords/try-catch.md)-Block belegt sind, und Sie können Code selbst dann ausführen, wenn eine Ausnahme im `try`-Block auftritt.</span><span class="sxs-lookup"><span data-stu-id="9a65e-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](../../../csharp/language-reference/keywords/try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="9a65e-104">In der Regel werden die Anweisungen eines `finally`-Blocks ausgeführt, wenn die Steuerung eine `try`-Anweisung verlässt.</span><span class="sxs-lookup"><span data-stu-id="9a65e-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="9a65e-105">Die Übertragung eines Steuerelements kann infolge einer normalen Ausführung, der Ausführung einer `break`-, `continue`-, `goto`- oder `return`-Anweisung oder der Weitergabe einer Ausnahme aus der `try`-Anweisung auftreten.</span><span class="sxs-lookup"><span data-stu-id="9a65e-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>  
  
 <span data-ttu-id="9a65e-106">Innerhalb einer behandelten Ausnahme ist sichergestellt, dass der zugeordnete `finally`-Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a65e-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="9a65e-107">Wenn die Ausnahme jedoch nicht behandelt wird, erfolgt die Ausführung des `finally`-Blocks je nachdem, wie der Entladevorgang für die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9a65e-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="9a65e-108">Das hängt wiederum davon ab, wie der Computer eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="9a65e-108">That, in turn, is dependent on how your computer is set up.</span></span> <span data-ttu-id="9a65e-109">Weitere Informationen finden Sie unter [Ausnahmefehlerverarbeitung in der CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span><span class="sxs-lookup"><span data-stu-id="9a65e-109">For more information, see [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span></span>  
  
 <span data-ttu-id="9a65e-110">Wenn eine Anwendung durch einen Ausnahmefehler beendet wird, ist es in der Regel nicht wichtig, ob der `finally`-Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a65e-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="9a65e-111">Wenn der `finally`-Block jedoch Anweisungen aufweist, die auch in dieser Situation ausgeführt werden müssen, kann als Lösung ein `catch`-Block der `try`-`finally`-Anweisung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9a65e-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="9a65e-112">Sie können auch die Ausnahme abfangen, die möglicherweise im `try`-Block einer `try`-`finally`-Anweisung weiter oben in der Aufrufliste ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9a65e-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="9a65e-113">Die Ausnahme kann also in der Methode abgefangen werden, mit der die Methode mit der `try`-`finally`-Anweisung aufgerufen wird. Die Ausnahme kann aber auch in der Methode abgefangen werden, mit der diese Methode aufgerufen wird, oder in einer beliebigen Methode in der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="9a65e-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="9a65e-114">Wenn die Ausnahme nicht abgefangen wird, wird der `finally`-Block je nachdem, ob vom Betriebssystem ein Entladevorgang für die Ausnahme ausgelöst wird, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9a65e-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a65e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a65e-115">Example</span></span>  
 <span data-ttu-id="9a65e-116">Im folgenden Beispiel wird eine `System.InvalidCastException` Ausnahme durch eine ungültige Konvertierungsanweisung verursacht.</span><span class="sxs-lookup"><span data-stu-id="9a65e-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="9a65e-117">Die Ausnahme wird nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="9a65e-117">The exception is unhandled.</span></span>  
  
 <span data-ttu-id="9a65e-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a65e-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span></span>  
  
 <span data-ttu-id="9a65e-119">Im folgenden Beispiel wird eine Ausnahme von der `TryCast`-Methode in einer Methode weiter oben in der Aufrufliste abgefangen.</span><span class="sxs-lookup"><span data-stu-id="9a65e-119">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>  
  
 <span data-ttu-id="9a65e-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a65e-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="9a65e-121">Weitere Informationen zu `finally` finden Sie unter [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="9a65e-121">For more information about `finally`, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
 <span data-ttu-id="9a65e-122">C# enthält auch die [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md), die eine ähnliche Funktionalität für <xref:System.IDisposable>-Objekte in einer zweckmäßigen Syntax bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="9a65e-122">C# also contains the [using statement](../../../csharp/language-reference/keywords/using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9a65e-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9a65e-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a65e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a65e-124">See Also</span></span>  
 <span data-ttu-id="9a65e-125">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9a65e-126">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9a65e-127">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9a65e-128">[try-, throw- und catch-Anweisungen (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="9a65e-128">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="9a65e-129">[Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-129">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="9a65e-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="9a65e-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="9a65e-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 [<span data-ttu-id="9a65e-132">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="9a65e-132">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

