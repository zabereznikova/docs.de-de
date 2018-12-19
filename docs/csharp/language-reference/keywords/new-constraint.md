---
title: new-Einschränkung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: de0798319d91032143cb806d6d39338c4f51ac8f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237843"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="7d589-102">new-Einschränkung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7d589-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="7d589-103">Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="7d589-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="7d589-104">Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d589-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="7d589-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d589-105">Example</span></span>

<span data-ttu-id="7d589-106">Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="7d589-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="7d589-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d589-107">Example</span></span>

<span data-ttu-id="7d589-108">Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="7d589-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="7d589-109">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7d589-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7d589-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7d589-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7d589-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d589-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="7d589-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7d589-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="7d589-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7d589-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7d589-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7d589-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7d589-115">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7d589-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="7d589-116">Generika</span><span class="sxs-lookup"><span data-stu-id="7d589-116">Generics</span></span>](../../programming-guide/generics/index.md)