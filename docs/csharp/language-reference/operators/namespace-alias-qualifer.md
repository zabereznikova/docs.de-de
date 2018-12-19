---
title: ':: Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243477"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9dc52-102">:: Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9dc52-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="9dc52-103">Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9dc52-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="9dc52-104">Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9dc52-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="9dc52-105">Der Operator `::` kann auch mit einer *Alias-Direktive* verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="9dc52-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="9dc52-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9dc52-106">Remarks</span></span>  
 <span data-ttu-id="9dc52-107">Der Namespacealias-Qualifizierer kann `global` sein.</span><span class="sxs-lookup"><span data-stu-id="9dc52-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="9dc52-108">Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="9dc52-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9dc52-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9dc52-109">For More Information</span></span>  
 <span data-ttu-id="9dc52-110">Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="9dc52-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="9dc52-111">Vorgehensweise: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="9dc52-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9dc52-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9dc52-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9dc52-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dc52-113">See Also</span></span>

- [<span data-ttu-id="9dc52-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9dc52-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9dc52-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9dc52-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9dc52-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="9dc52-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="9dc52-117">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9dc52-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="9dc52-118">. Operator</span><span class="sxs-lookup"><span data-stu-id="9dc52-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="9dc52-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="9dc52-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
