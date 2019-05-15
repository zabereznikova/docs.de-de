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
ms.openlocfilehash: 324f6711cdec478e5647b05d84c281f79e95f036
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452362"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="75ef8-102">::-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="75ef8-102">:: operator (C# Reference)</span></span>

<span data-ttu-id="75ef8-103">Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="75ef8-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="75ef8-104">Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75ef8-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="75ef8-105">Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="75ef8-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="75ef8-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="75ef8-106">Remarks</span></span>

<span data-ttu-id="75ef8-107">Der Namespacealias-Qualifizierer kann `global` sein.</span><span class="sxs-lookup"><span data-stu-id="75ef8-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="75ef8-108">Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="75ef8-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="75ef8-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75ef8-109">For more information</span></span>

<span data-ttu-id="75ef8-110">Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="75ef8-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="75ef8-111">Vorgehensweise: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="75ef8-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="75ef8-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="75ef8-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="75ef8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75ef8-113">See also</span></span>

- [<span data-ttu-id="75ef8-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="75ef8-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="75ef8-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="75ef8-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="75ef8-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="75ef8-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="75ef8-117">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="75ef8-117">Namespace Keywords</span></span>](../keywords/namespace-keywords.md)
- [<span data-ttu-id="75ef8-118">.-Operator</span><span class="sxs-lookup"><span data-stu-id="75ef8-118">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="75ef8-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="75ef8-119">extern alias</span></span>](../keywords/extern-alias.md)