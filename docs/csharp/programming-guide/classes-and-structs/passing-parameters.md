---
title: "Übergeben von Parametern (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9e0e06d67f9da39c6b55f91e35d4a75b43353f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="f2486-102">Übergeben von Parametern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f2486-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="f2486-103">In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2486-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="f2486-104">Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei.</span><span class="sxs-lookup"><span data-stu-id="f2486-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="f2486-105">Verwenden Sie das Schlüsselwort `ref` oder `out`, um einen Parameter als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f2486-105">To pass a parameter by reference, use the `ref` or `out` keyword.</span></span> <span data-ttu-id="f2486-106">Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2486-106">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="f2486-107">Weitere Informationen zu den Unterschieden zwischen `ref` und `out` finden Sie unter [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) sowie [Übergeben von Arrays mithilfe von „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="f2486-107">For more information about the difference between `ref` and `out`, see [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md), and [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="f2486-108">Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="f2486-108">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="f2486-109">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f2486-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f2486-110">Übergeben von Werttypparametern</span><span class="sxs-lookup"><span data-stu-id="f2486-110">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="f2486-111">Übergeben von Verweistypparametern</span><span class="sxs-lookup"><span data-stu-id="f2486-111">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f2486-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f2486-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2486-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2486-113">See Also</span></span>  
 [<span data-ttu-id="f2486-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f2486-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f2486-115">Methoden</span><span class="sxs-lookup"><span data-stu-id="f2486-115">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
