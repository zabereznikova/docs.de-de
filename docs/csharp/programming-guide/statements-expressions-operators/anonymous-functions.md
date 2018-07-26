---
title: Anonyme Funktionen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: e368105c090f95435a4529470bdf1b41346d039c
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936749"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="193aa-102">Anonyme Funktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="193aa-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="193aa-103">Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="193aa-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="193aa-104">Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="193aa-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="193aa-105">Es gibt zwei Arten von anonymen Funktionen, die in den folgenden Themen einzeln erläutert werden:</span><span class="sxs-lookup"><span data-stu-id="193aa-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
-   <span data-ttu-id="193aa-106">[Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="193aa-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
-   [<span data-ttu-id="193aa-107">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="193aa-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="193aa-108">Lambdaausdrücke können an Ausdrucksstrukturen und an Delegaten gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="193aa-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="193aa-109">Entwicklung von Delegaten in C#</span><span class="sxs-lookup"><span data-stu-id="193aa-109">The Evolution of Delegates in C#</span></span>  
 <span data-ttu-id="193aa-110">In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="193aa-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="193aa-111">C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="193aa-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="193aa-112">C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind.</span><span class="sxs-lookup"><span data-stu-id="193aa-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="193aa-113">Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="193aa-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="193aa-114">In der Regel sollten Anwendungen, die für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Version 3.5 und höher gedacht sind, Lambdaausdrücke verwenden.</span><span class="sxs-lookup"><span data-stu-id="193aa-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="193aa-115">Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="193aa-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="193aa-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="193aa-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="193aa-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="193aa-117">See also</span></span>

[<span data-ttu-id="193aa-118">Anweisungen, Ausdrücke und Operatoren</span><span class="sxs-lookup"><span data-stu-id="193aa-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
[<span data-ttu-id="193aa-119">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="193aa-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
[<span data-ttu-id="193aa-120">Delegaten</span><span class="sxs-lookup"><span data-stu-id="193aa-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
[<span data-ttu-id="193aa-121">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="193aa-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)  
