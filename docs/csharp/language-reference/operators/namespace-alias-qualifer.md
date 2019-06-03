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
ms.openlocfilehash: 0b456ed3ce9965ef389d8ce40167afa4ac33da18
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422525"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c6725-102">::-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c6725-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="c6725-103">Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c6725-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="c6725-104">Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c6725-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="c6725-105">Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c6725-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="c6725-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c6725-106">Remarks</span></span>

<span data-ttu-id="c6725-107">Der Namespacealias-Qualifizierer kann `global` sein.</span><span class="sxs-lookup"><span data-stu-id="c6725-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="c6725-108">Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c6725-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c6725-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6725-109">For more information</span></span>

<span data-ttu-id="c6725-110">Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="c6725-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="c6725-111">Vorgehensweise: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="c6725-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="c6725-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c6725-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c6725-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6725-113">See also</span></span>

- [<span data-ttu-id="c6725-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c6725-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c6725-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c6725-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c6725-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c6725-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="c6725-117">.-Operator</span><span class="sxs-lookup"><span data-stu-id="c6725-117">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="c6725-118">extern alias</span><span class="sxs-lookup"><span data-stu-id="c6725-118">extern alias</span></span>](../keywords/extern-alias.md)
