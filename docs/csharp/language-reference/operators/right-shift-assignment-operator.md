---
title: '>>=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278979"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9226d-102">>>=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9226d-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="9226d-103">Der Rechtsschiebezuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="9226d-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="9226d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9226d-104">Remarks</span></span>

<span data-ttu-id="9226d-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="9226d-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="9226d-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="9226d-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="9226d-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="9226d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="9226d-108">Der [>>-Operator](right-shift-operator.md) verschiebt `x` um einen durch `y` angegebenen Wert nach rechts.</span><span class="sxs-lookup"><span data-stu-id="9226d-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="9226d-109">Der >>=-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [>>-Operator](right-shift-operator.md) überladen (siehe [Operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9226d-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="9226d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9226d-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="9226d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9226d-111">See also</span></span>

- [<span data-ttu-id="9226d-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9226d-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9226d-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9226d-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9226d-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9226d-114">C# operators</span></span>](index.md)