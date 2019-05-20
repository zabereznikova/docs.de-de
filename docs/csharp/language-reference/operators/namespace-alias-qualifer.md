---
title: ::-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 5bd43bb60736bbcaf8034cc2b369c34f977319ac
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633920"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="12f5e-102">::-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="12f5e-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="12f5e-103">Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="12f5e-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="12f5e-104">Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="12f5e-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="12f5e-105">Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="12f5e-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="12f5e-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="12f5e-106">Remarks</span></span>

<span data-ttu-id="12f5e-107">Der Namespacealias-Qualifizierer kann `global` sein.</span><span class="sxs-lookup"><span data-stu-id="12f5e-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="12f5e-108">Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="12f5e-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="12f5e-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12f5e-109">For more information</span></span>

<span data-ttu-id="12f5e-110">Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="12f5e-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="12f5e-111">Vorgehensweise: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="12f5e-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="12f5e-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="12f5e-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="12f5e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12f5e-113">See also</span></span>

- [<span data-ttu-id="12f5e-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="12f5e-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12f5e-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="12f5e-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12f5e-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="12f5e-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="12f5e-117">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="12f5e-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="12f5e-118">.-Operator</span><span class="sxs-lookup"><span data-stu-id="12f5e-118">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="12f5e-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="12f5e-119">extern alias</span></span>](../keywords/extern-alias.md)
