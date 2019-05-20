---
title: var – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: a523e575f14c88ea385bf115f0b07f54190499a5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633203"
---
# <a name="var-c-reference"></a><span data-ttu-id="50be1-102">var (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="50be1-102">var (C# Reference)</span></span>

<span data-ttu-id="50be1-103">Ab Visual Studio C# 3.0 können Variablen, die im Methodenbereich deklariert wurden, den impliziten „Typ“ `var` haben.</span><span class="sxs-lookup"><span data-stu-id="50be1-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="50be1-104">Eine implizit typisierte lokale Variable ist stark typisiert, als hätten Sie den Typ selbst deklariert. Tatsächlich legt der Compiler den Typ fest.</span><span class="sxs-lookup"><span data-stu-id="50be1-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="50be1-105">Die folgenden beiden `i`-Aktivitäten sind funktional äquivalent:</span><span class="sxs-lookup"><span data-stu-id="50be1-105">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="50be1-106">Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Type relationships in LINQ query operations (Typbeziehungen in LINQ-Abfragevorgängen)](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="50be1-106">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="50be1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50be1-107">Example</span></span>

<span data-ttu-id="50be1-108">Im folgenden Beispiel werden zwei Abfrageausdrücke gezeigt.</span><span class="sxs-lookup"><span data-stu-id="50be1-108">The following example shows two query expressions.</span></span> <span data-ttu-id="50be1-109">Im ersten Ausdruck in das Verwenden von `var` erlaubt aber nicht erforderlich, da der Typ des Abfrageergebnisses explizit als `IEnumerable<string>` angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="50be1-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="50be1-110">Im zweiten Ausdruck ermöglicht `var`, dass das Ergebnis eine Auflistung von anonymen Typen ist und dass auf die Namen dieser Typen nicht zugegriffen werden kann. Nur der Compiler kann darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="50be1-110">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="50be1-111">Durch die Verwendung von `var` wird die Voraussetzung beseitigt, eine neue Klasse für das Ergebnis erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="50be1-111">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="50be1-112">Beachten Sie, dass die `foreach`-Iterationsvariable `item` im zweiten Beispiel auch implizit typisiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="50be1-112">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="50be1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50be1-113">See also</span></span>

- [<span data-ttu-id="50be1-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="50be1-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="50be1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="50be1-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="50be1-116">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="50be1-116">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
