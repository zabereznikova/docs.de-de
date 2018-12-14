---
title: -&gt;-Operator (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144129"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="7fec7-102">-&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7fec7-102">-&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="7fec7-103">Der Zeigermember-Zugriffsoperator `->` kombiniert Zeigerdereferenzierung mit Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="7fec7-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="7fec7-104">Wenn `x` ein Zeiger des Typs `T*` und `y` ein Member von `T` ist, auf den zugegriffen werden kann, dann ist ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="7fec7-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="7fec7-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="7fec7-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="7fec7-106">Der `->`-Operator erfordert [unsicheren](../keywords/unsafe.md) Kontext.</span><span class="sxs-lookup"><span data-stu-id="7fec7-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="7fec7-107">Weitere Informationen finden Sie unter [Gewusst wie: Zugreifen auf einen Member mit einem Zeiger](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="7fec7-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="7fec7-108">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="7fec7-108">Operator overloadability</span></span>

<span data-ttu-id="7fec7-109">Operator `->` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7fec7-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7fec7-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7fec7-110">C# language specification</span></span>

<span data-ttu-id="7fec7-111">Weitere Informationen finden Sie im Abschnitt [Zeigermemberzugriff](~/_csharplang/spec/unsafe-code.md#pointer-member-access) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="7fec7-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fec7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fec7-112">See also</span></span>

- [<span data-ttu-id="7fec7-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7fec7-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7fec7-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7fec7-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7fec7-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7fec7-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="7fec7-116">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="7fec7-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
