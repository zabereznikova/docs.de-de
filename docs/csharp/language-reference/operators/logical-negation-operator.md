---
title: '! -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333225"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="39d17-103">!</span><span class="sxs-lookup"><span data-stu-id="39d17-103">!</span></span> <span data-ttu-id="39d17-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="39d17-104">operator (C# Reference)</span></span>

<span data-ttu-id="39d17-105">Der logische Negationsoperator (`!`) ist ein unärer Operator, der seinen Operanden negiert.</span><span class="sxs-lookup"><span data-stu-id="39d17-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="39d17-106">Er wird für `bool` definiert, und gibt `true` nur dann zurück, wenn sein Operand `false` ist.</span><span class="sxs-lookup"><span data-stu-id="39d17-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="39d17-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39d17-107">Remarks</span></span>

<span data-ttu-id="39d17-108">Benutzerdefinierte Typen können den Operator `!` überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="39d17-108">User-defined types can overload the `!` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="39d17-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39d17-109">Example</span></span>

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a><span data-ttu-id="39d17-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39d17-110">See also</span></span>

- [<span data-ttu-id="39d17-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="39d17-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39d17-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="39d17-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39d17-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="39d17-113">C# Operators</span></span>](index.md)