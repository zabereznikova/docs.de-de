---
title: '*=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333433"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="92035-102">Operator \*= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="92035-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="92035-103">Der binäre Multiplikationszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="92035-103">The binary multiplication assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="92035-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92035-104">Remarks</span></span>

<span data-ttu-id="92035-105">Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="92035-105">An expression using the `*=` assignment operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="92035-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="92035-106">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="92035-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="92035-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="92035-108">Der [\*-Operator](multiplication-operator.md) ist für numerische Typen für die Multiplikation vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="92035-108">The [\* operator](multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>

<span data-ttu-id="92035-109">Der `*=`-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [\*-Operator](multiplication-operator.md) überladen (siehe [Operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="92035-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](multiplication-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="92035-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92035-110">Example</span></span>

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a><span data-ttu-id="92035-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92035-111">See also</span></span>

- [<span data-ttu-id="92035-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92035-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="92035-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="92035-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="92035-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="92035-114">C# Operators</span></span>](index.md)
