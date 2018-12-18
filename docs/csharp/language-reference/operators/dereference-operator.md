---
title: -&gt;-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: bb1ccd026f403e68565c5c7681943d8017578d01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234889"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="20c81-102">-&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="20c81-102">-&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="20c81-103">Der Zeigermember-Zugriffsoperator `->` kombiniert Zeigerdereferenzierung mit Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="20c81-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="20c81-104">Wenn `x` ein Zeiger des Typs `T*` und `y` ein Member von `T` ist, auf den zugegriffen werden kann, dann ist ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="20c81-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="20c81-105">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="20c81-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="20c81-106">Der `->`-Operator erfordert [unsicheren](../keywords/unsafe.md) Kontext.</span><span class="sxs-lookup"><span data-stu-id="20c81-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="20c81-107">Weitere Informationen finden Sie unter [Vorgehensweise: Zugreifen auf einen Member mit einem Zeiger](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="20c81-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="20c81-108">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="20c81-108">Operator overloadability</span></span>

<span data-ttu-id="20c81-109">Operator `->` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="20c81-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="20c81-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="20c81-110">C# language specification</span></span>

<span data-ttu-id="20c81-111">Weitere Informationen finden Sie im Abschnitt [Zeigermemberzugriff](~/_csharplang/spec/unsafe-code.md#pointer-member-access) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="20c81-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20c81-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20c81-112">See also</span></span>

- [<span data-ttu-id="20c81-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="20c81-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="20c81-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="20c81-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="20c81-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="20c81-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="20c81-116">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="20c81-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
