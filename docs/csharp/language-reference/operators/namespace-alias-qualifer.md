---
title: 'Operator :: (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ba294-102">Operator :: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ba294-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="ba294-103">Der Namespacealias-Qualifizierer (`::`) wird verwendet, um nach Bezeichnern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ba294-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="ba294-104">Er befindet sich immer zwischen zwei Bezeichnern, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba294-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="ba294-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba294-105">Remarks</span></span>  
 <span data-ttu-id="ba294-106">Der Namespacealias-Qualifizierer kann `global` sein.</span><span class="sxs-lookup"><span data-stu-id="ba294-106">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="ba294-107">Dadurch wird eine Suche im globalen Namespace anstatt Namespacealias aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ba294-107">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ba294-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba294-108">For More Information</span></span>  
 <span data-ttu-id="ba294-109">Ein Beispiel zur Verwendung des `::`-Operators finden Sie im folgenden Abschnitt:</span><span class="sxs-lookup"><span data-stu-id="ba294-109">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="ba294-110">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="ba294-110">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ba294-111">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ba294-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba294-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba294-112">See Also</span></span>  
 [<span data-ttu-id="ba294-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ba294-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ba294-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ba294-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ba294-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ba294-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="ba294-116">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ba294-116">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="ba294-117">. Operator</span><span class="sxs-lookup"><span data-stu-id="ba294-117">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
 [<span data-ttu-id="ba294-118">extern alias</span><span class="sxs-lookup"><span data-stu-id="ba294-118">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
