---
description: var – C#-Referenz
title: var – C#-Referenz
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608711"
---
# <a name="var-c-reference"></a><span data-ttu-id="e9c2d-103">var (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e9c2d-103">var (C# reference)</span></span>

<span data-ttu-id="e9c2d-104">Ab C# 3 können Variablen, die im Methodenbereich deklariert wurden, den impliziten „Typ“ `var` haben.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-104">Beginning with C# 3, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="e9c2d-105">Eine implizit typisierte lokale Variable ist stark typisiert, als hätten Sie den Typ selbst deklariert. Tatsächlich legt der Compiler den Typ fest.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="e9c2d-106">Die folgenden beiden `i`-Aktivitäten sind funktional äquivalent:</span><span class="sxs-lookup"><span data-stu-id="e9c2d-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> <span data-ttu-id="e9c2d-107">Wenn `var` mit aktivierten [Verweistypen verwendet wird, die Nullwerte zulassen](../builtin-types/nullable-reference-types.md), impliziert dies immer einen Verweistyp, der Nullwerte zulässt, auch wenn der Ausdruckstyp diese zulässt.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-107">When `var` is used with [nullable reference types](../builtin-types/nullable-reference-types.md) enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

<span data-ttu-id="e9c2d-108">Das `var`-Schlüsselwort wird häufig verwendet, wenn Konstruktoraufrufausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-108">A common use of the `var` keyword is with constructor invocation expressions.</span></span> <span data-ttu-id="e9c2d-109">Durch die Verwendung von `var` können Sie einen Typnamen in einer Variablendeklaration und Objektinstanziierung nicht wiederholen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e9c2d-109">The use of `var` allows you to not repeat a type name in a variable declaration and object instantiation, as the following example shows:</span></span>

```csharp
var xs = new List<int>();
```

<span data-ttu-id="e9c2d-110">Ab C# 9.0 können Sie als Alternative einen als Ziel typisierten [`new`-Ausdruck](../operators/new-operator.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="e9c2d-110">Beginning with C# 9.0, you can use a target-typed [`new` expression](../operators/new-operator.md) as an alternative:</span></span>

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a><span data-ttu-id="e9c2d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9c2d-111">Example</span></span>

<span data-ttu-id="e9c2d-112">Im folgenden Beispiel werden zwei Abfrageausdrücke gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-112">The following example shows two query expressions.</span></span> <span data-ttu-id="e9c2d-113">Im ersten Ausdruck in das Verwenden von `var` erlaubt aber nicht erforderlich, da der Typ des Abfrageergebnisses explizit als `IEnumerable<string>` angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-113">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="e9c2d-114">Im zweiten Ausdruck ermöglicht `var`, dass das Ergebnis eine Auflistung von anonymen Typen ist und dass auf die Namen dieser Typen nicht zugegriffen werden kann. Nur der Compiler kann darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-114">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="e9c2d-115">Durch die Verwendung von `var` wird die Voraussetzung beseitigt, eine neue Klasse für das Ergebnis erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-115">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="e9c2d-116">Beachten Sie, dass die `foreach`-Iterationsvariable `item` im zweiten Beispiel auch implizit typisiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="e9c2d-116">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="e9c2d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c2d-117">See also</span></span>

- [<span data-ttu-id="e9c2d-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e9c2d-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e9c2d-119">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="e9c2d-119">Implicitly typed local variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="e9c2d-120">Type relationships in LINQ query operations (Typbeziehungen in LINQ-Abfragevorgängen)</span><span class="sxs-lookup"><span data-stu-id="e9c2d-120">Type relationships in LINQ query operations</span></span>](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
