---
title: Anonyme Funktionen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: c949bf5af441728b311391ecb42623951d0145ab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608145"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="347b6-102">Anonyme Funktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="347b6-102">Anonymous Functions (C# Programming Guide)</span></span>
<span data-ttu-id="347b6-103">Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="347b6-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="347b6-104">Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="347b6-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>  
  
 <span data-ttu-id="347b6-105">Es gibt zwei Arten von anonymen Funktionen, die in den folgenden Themen einzeln erläutert werden:</span><span class="sxs-lookup"><span data-stu-id="347b6-105">There are two kinds of anonymous functions, which are discussed individually in the following topics:</span></span>  
  
- <span data-ttu-id="347b6-106">[Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="347b6-106">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
- [<span data-ttu-id="347b6-107">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="347b6-107">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  <span data-ttu-id="347b6-108">Lambdaausdrücke können an Ausdrucksstrukturen und an Delegaten gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="347b6-108">Lambda expressions can be bound to expression trees and also to delegates.</span></span>  
  
## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="347b6-109">Entwicklung von Delegaten in C\#</span><span class="sxs-lookup"><span data-stu-id="347b6-109">The Evolution of Delegates in C\#</span></span>
 <span data-ttu-id="347b6-110">In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="347b6-110">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="347b6-111">C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="347b6-111">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="347b6-112">C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind.</span><span class="sxs-lookup"><span data-stu-id="347b6-112">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="347b6-113">Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="347b6-113">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="347b6-114">In der Regel sollten Anwendungen, die für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Version 3.5 und höher gedacht sind, Lambdaausdrücke verwenden.</span><span class="sxs-lookup"><span data-stu-id="347b6-114">In general, applications that target version 3.5 and later of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] should use lambda expressions.</span></span>  
  
 <span data-ttu-id="347b6-115">Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="347b6-115">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="347b6-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="347b6-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="347b6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="347b6-117">See also</span></span>

- [<span data-ttu-id="347b6-118">Anweisungen, Ausdrücke und Operatoren</span><span class="sxs-lookup"><span data-stu-id="347b6-118">Statements, Expressions, and Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [<span data-ttu-id="347b6-119">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="347b6-119">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [<span data-ttu-id="347b6-120">Delegaten</span><span class="sxs-lookup"><span data-stu-id="347b6-120">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="347b6-121">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="347b6-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
