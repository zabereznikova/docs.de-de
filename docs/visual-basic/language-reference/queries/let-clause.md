---
title: Let-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 63eaf97016db259870eb77199651ecbdc5f809c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350431"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="758b9-102">Let-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="758b9-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="758b9-103">Berechnet einen Wert und weist ihn einer neuen Variablen in der Abfrage zu.</span><span class="sxs-lookup"><span data-stu-id="758b9-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="758b9-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="758b9-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="758b9-105">Parts</span></span>  
  
|<span data-ttu-id="758b9-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="758b9-106">Term</span></span>|<span data-ttu-id="758b9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="758b9-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="758b9-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="758b9-108">Required.</span></span> <span data-ttu-id="758b9-109">Ein Alias, der zum Verweisen auf die Ergebnisse des angegebenen Ausdrucks verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="758b9-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="758b9-110">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="758b9-110">Required.</span></span> <span data-ttu-id="758b9-111">Ein Ausdruck, der ausgewertet und der angegebenen Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="758b9-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="758b9-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="758b9-112">Remarks</span></span>  
 <span data-ttu-id="758b9-113">Mit der `Let`-Klausel können Sie Werte für jedes Abfrageergebnis berechnen und mithilfe eines Alias referenzieren.</span><span class="sxs-lookup"><span data-stu-id="758b9-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="758b9-114">Der Alias kann in anderen Klauseln verwendet werden, z. b. in der `Where`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="758b9-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="758b9-115">Mit der `Let`-Klausel können Sie eine Abfrage Anweisung erstellen, die leichter lesbar ist, da Sie einen Alias für eine in der Abfrage enthaltene Ausdrucks Klausel angeben und bei jeder Verwendung der Expression-Klausel den Alias ersetzen können.</span><span class="sxs-lookup"><span data-stu-id="758b9-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="758b9-116">Sie können eine beliebige Anzahl von `variable`-und `expression` Zuweisungen in die `Let`-Klausel einschließen.</span><span class="sxs-lookup"><span data-stu-id="758b9-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="758b9-117">Trennen Sie jede Zuweisung durch ein Komma (,).</span><span class="sxs-lookup"><span data-stu-id="758b9-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="758b9-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="758b9-118">Example</span></span>  
 <span data-ttu-id="758b9-119">Im folgenden Codebeispiel wird die `Let`-Klausel verwendet, um einen Rabatt von 10% auf Produkte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="758b9-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="758b9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="758b9-120">See also</span></span>

- [<span data-ttu-id="758b9-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="758b9-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="758b9-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="758b9-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="758b9-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="758b9-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="758b9-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="758b9-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="758b9-125">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="758b9-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
