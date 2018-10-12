---
title: Übergeben von Parametern (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: a9538ee9f5f49554e9fe1822367404ab1d1e858d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194850"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="29346-102">Übergeben von Parametern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="29346-102">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="29346-103">In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="29346-103">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="29346-104">Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei.</span><span class="sxs-lookup"><span data-stu-id="29346-104">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="29346-105">Wenn Sie den Wert ändern und darum den Parameter pro Verweis übergeben möchten, verwenden Sie die Schlüsselwörter `ref` oder `out`.</span><span class="sxs-lookup"><span data-stu-id="29346-105">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="29346-106">Wenn Sie den Wert zwar ändern, aber keine Kopie erstellen möchten, und darum den Parameter pro Verweis übergeben möchten, verwenden Sie den Modifizierer `in`.</span><span class="sxs-lookup"><span data-stu-id="29346-106">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="29346-107">Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="29346-107">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="29346-108">Weitere Informationen zum Unterschied zwischen `in`, `ref` und `out` finden Sie unter [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) und [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="29346-108">For more information about the difference between `in`, `ref`, and `out`, see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md), and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="29346-109">Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="29346-109">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 <span data-ttu-id="29346-110">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="29346-110">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="29346-111">Übergeben von Werttypparametern</span><span class="sxs-lookup"><span data-stu-id="29346-111">Passing Value-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [<span data-ttu-id="29346-112">Übergeben von Verweistypparametern</span><span class="sxs-lookup"><span data-stu-id="29346-112">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="29346-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="29346-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29346-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29346-114">See Also</span></span>

- [<span data-ttu-id="29346-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="29346-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="29346-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="29346-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
