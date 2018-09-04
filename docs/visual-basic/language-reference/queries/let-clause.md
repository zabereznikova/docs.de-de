---
title: Let-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 34c0fd239d9e08dab4a107cb8447941e7ab3ecbe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516762"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="6e279-102">Let-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e279-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="6e279-103">Berechnet einen Wert aus, und weist es eine neue Variable in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6e279-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e279-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e279-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="6e279-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6e279-105">Parts</span></span>  
  
|<span data-ttu-id="6e279-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="6e279-106">Term</span></span>|<span data-ttu-id="6e279-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6e279-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="6e279-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e279-108">Required.</span></span> <span data-ttu-id="6e279-109">Ein Alias, der verwendet werden kann, um die Ergebnisse des angegebenen Ausdrucks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="6e279-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="6e279-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e279-110">Required.</span></span> <span data-ttu-id="6e279-111">Ein Ausdruck, der ausgewertet und der angegebenen Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6e279-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e279-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e279-112">Remarks</span></span>  
 <span data-ttu-id="6e279-113">Die `Let` -Klausel können Sie Werte für die einzelnen Abfrageergebnis, und verweisen sie mithilfe eines Alias zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="6e279-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="6e279-114">Der Alias kann verwendet werden in anderen Klauseln, z. B. die `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="6e279-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="6e279-115">Die `Let` -Klausel können Sie eine abfrageanweisung zu erstellen, ist einfacher zu lesen, da Sie geben Sie einen Alias für eine Expression-Klausel in der Abfrage enthalten, und ersetzen den Alias jedes Mal, die die Ausdrucksklausel verwendet wird, können.</span><span class="sxs-lookup"><span data-stu-id="6e279-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="6e279-116">Sie können eine beliebige Anzahl von einschließen `variable` und `expression` Zuweisungen in der `Let` Klausel.</span><span class="sxs-lookup"><span data-stu-id="6e279-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="6e279-117">Trennen Sie jede Zuweisung durch ein Komma (,) ein.</span><span class="sxs-lookup"><span data-stu-id="6e279-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e279-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e279-118">Example</span></span>  
 <span data-ttu-id="6e279-119">Im folgenden Codebeispiel wird die `Let` -Klausel, um einen Rabatt von 10 Prozent zu Produkten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="6e279-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6e279-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e279-120">See Also</span></span>  
 [<span data-ttu-id="6e279-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e279-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="6e279-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="6e279-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="6e279-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e279-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="6e279-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e279-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="6e279-125">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="6e279-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
