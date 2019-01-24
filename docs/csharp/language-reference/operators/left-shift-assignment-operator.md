---
title: '&lt;&lt;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 4513c4b78dea3e8102c72a43249b4a44ffa2421d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333251"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="91954-102">&lt;&lt;=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="91954-102">&lt;&lt;= operator (C# Reference)</span></span>

<span data-ttu-id="91954-103">Der Linksschiebezuweisungs-Operator</span><span class="sxs-lookup"><span data-stu-id="91954-103">The left-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="91954-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91954-104">Remarks</span></span>

<span data-ttu-id="91954-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="91954-105">An expression of the form</span></span>

```csharp
x <<= y
```

<span data-ttu-id="91954-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="91954-106">is evaluated as</span></span>

```csharp
x = x << y
```

<span data-ttu-id="91954-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="91954-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="91954-108">Der [Operator <<](left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.</span><span class="sxs-lookup"><span data-stu-id="91954-108">The [<< operator](left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>

<span data-ttu-id="91954-109">Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](left-shift-operator.md) überladen (weitere Informationen unter [Operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="91954-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](left-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="91954-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91954-110">Example</span></span>

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a><span data-ttu-id="91954-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91954-111">See also</span></span>

- [<span data-ttu-id="91954-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="91954-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="91954-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="91954-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="91954-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="91954-114">C# Operators</span></span>](index.md)
