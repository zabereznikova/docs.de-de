---
description: new-Einschränkung – C#-Referenz
title: new-Einschränkung – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: f7b097729fe973aba7b85c48e1b1033aade83080
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139449"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="a2a6d-103">new-Einschränkung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a2a6d-103">new constraint (C# Reference)</span></span>

<span data-ttu-id="a2a6d-104">Die `new`-Einschränkung gibt an, dass ein Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="a2a6d-104">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="a2a6d-105">Der Typ kann nicht abstrakt sein, um die `new`-Einschränkung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2a6d-105">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="a2a6d-106">Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="a2a6d-106">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="a2a6d-107">Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="a2a6d-107">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="a2a6d-108">Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a2a6d-108">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="a2a6d-109">Sie können das Schlüsselwort `new` auch verwenden, um [eine Instanz eines Typs](../operators/new-operator.md) zu erstellen oder als [Memberdeklarationsmodifizierer](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="a2a6d-109">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a2a6d-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a2a6d-110">C# language specification</span></span>

<span data-ttu-id="a2a6d-111">Weitere Informationen finden Sie im Abschnitt [Einschränkungen für Typparameter](~/_csharplang/spec/classes.md#type-parameter-constraints) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a2a6d-111">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2a6d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a6d-112">See also</span></span>

- [<span data-ttu-id="a2a6d-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a2a6d-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2a6d-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a2a6d-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2a6d-115">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a2a6d-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a2a6d-116">Generics</span><span class="sxs-lookup"><span data-stu-id="a2a6d-116">Generics</span></span>](../../programming-guide/generics/index.md)
