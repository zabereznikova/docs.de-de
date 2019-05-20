---
title: '- -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 920981addd5c779c9ad1c666ef45e1de5cd23408
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633004"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="a3406-102">-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a3406-102">- operator (C# Reference)</span></span>

<span data-ttu-id="a3406-103">Der `-`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a3406-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3406-104">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a3406-104">Remarks</span></span>

<span data-ttu-id="a3406-105">Unäre `-`-Operatoren sind für alle numerischen Typen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="a3406-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="a3406-106">Das Ergebnis einer unären `-`-Operation für einen numerischen Typ ist die numerische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="a3406-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="a3406-107">Binäre `-` Operatoren sind für alle numerischen Typen und Enumerationstypen vordefiniert, um den zweiten Operanden vom ersten zu subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="a3406-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="a3406-108">Delegattypen bieten auch einen binären `-`-Operator, der die Delegatentfernung durchführt.</span><span class="sxs-lookup"><span data-stu-id="a3406-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="a3406-109">Benutzerdefinierte Typen können die unären `-`- und binären `-`-Operatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="a3406-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="a3406-110">Weitere Informationen finden Sie unter [operator (C#-Referenz)](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="a3406-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3406-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3406-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="a3406-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3406-112">See also</span></span>

- [<span data-ttu-id="a3406-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a3406-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3406-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a3406-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3406-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a3406-115">C# operators</span></span>](index.md)
