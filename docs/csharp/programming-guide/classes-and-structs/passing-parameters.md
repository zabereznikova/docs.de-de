---
title: Übergeben von Parametern – C#-Programmierhandbuch
description: Sie können Argumente als Werte oder Verweise an Parameter in C# übergeben. Änderungen, die als Verweise an Argumente übergeben werden, bleiben erhalten. Verwenden Sie „ref“ oder „out“, um Argumente als Verweise zu übergeben.
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 875a42aacf3d7aa4124684aefafdcb07ff4c87d6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864734"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="ed4bf-105">Übergeben von Parametern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ed4bf-105">Passing Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="ed4bf-106">In C# können Argumente an Parameter entweder als Wert oder als Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-106">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="ed4bf-107">Durch die Übergabe als Verweis können Funktionsmember, Methoden, Eigenschaften, Indexer, Operatoren und Konstruktoren den Wert der Parameter ändern und behalten diese Änderung in der aufrufenden Umgebung bei.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-107">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="ed4bf-108">Wenn Sie den Wert ändern und darum den Parameter pro Verweis übergeben möchten, verwenden Sie die Schlüsselwörter `ref` oder `out`.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-108">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="ed4bf-109">Wenn Sie den Wert zwar ändern, aber keine Kopie erstellen möchten, und darum den Parameter pro Verweis übergeben möchten, verwenden Sie den Modifizierer `in`.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-109">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="ed4bf-110">Der Einfachheit halber wird in den Beispielen in diesem Thema nur das Schlüsselwort `ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-110">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="ed4bf-111">Weitere Informationen zum Unterschied zwischen `in`, `ref` und `out` finden Sie unter [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) und [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-111">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="ed4bf-112">Das folgende Beispiel veranschaulicht die Unterschiede zwischen Wert- und Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-112">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="ed4bf-113">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ed4bf-113">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="ed4bf-114">Übergeben von Werttypparametern</span><span class="sxs-lookup"><span data-stu-id="ed4bf-114">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="ed4bf-115">Übergeben von Verweistypparametern</span><span class="sxs-lookup"><span data-stu-id="ed4bf-115">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ed4bf-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ed4bf-116">C# Language Specification</span></span>  

<span data-ttu-id="ed4bf-117">Weitere Informationen erhalten Sie in den [Argumentlisten](~/_csharplang/spec/expressions.md#argument-lists) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ed4bf-117">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ed4bf-118">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="ed4bf-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed4bf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed4bf-119">See also</span></span>

- [<span data-ttu-id="ed4bf-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed4bf-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ed4bf-121">Methoden</span><span class="sxs-lookup"><span data-stu-id="ed4bf-121">Methods</span></span>](./methods.md)
