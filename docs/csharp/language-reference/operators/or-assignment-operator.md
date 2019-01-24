---
title: '|=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333264"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f80df-102">|=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f80df-102">|= operator (C# Reference)</span></span>

<span data-ttu-id="f80df-103">Der OR-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="f80df-103">The OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="f80df-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f80df-104">Remarks</span></span>

<span data-ttu-id="f80df-105">Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="f80df-105">An expression using the `|=` assignment operator, such as</span></span>

```csharp
x |= y
```

<span data-ttu-id="f80df-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="f80df-106">is equivalent to</span></span>

```csharp
x = x | y
```

<span data-ttu-id="f80df-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="f80df-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f80df-108">Der [Operator &#124;](or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="f80df-108">The [&#124; operator](or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>

<span data-ttu-id="f80df-109">Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](or-operator.md) überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="f80df-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](or-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="f80df-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f80df-110">Example</span></span>

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a><span data-ttu-id="f80df-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f80df-111">See also</span></span>

- [<span data-ttu-id="f80df-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f80df-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f80df-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f80df-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f80df-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f80df-114">C# operators</span></span>](index.md)