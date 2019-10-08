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
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004730"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="b8602-102">Let-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8602-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="b8602-103">Berechnet einen Wert und weist ihn einer neuen Variablen in der Abfrage zu.</span><span class="sxs-lookup"><span data-stu-id="b8602-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8602-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8602-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="b8602-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b8602-105">Parts</span></span>  
  
|<span data-ttu-id="b8602-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b8602-106">Term</span></span>|<span data-ttu-id="b8602-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b8602-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="b8602-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b8602-108">Required.</span></span> <span data-ttu-id="b8602-109">Ein Alias, der zum Verweisen auf die Ergebnisse des angegebenen Ausdrucks verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8602-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="b8602-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b8602-110">Required.</span></span> <span data-ttu-id="b8602-111">Ein Ausdruck, der ausgewertet und der angegebenen Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b8602-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8602-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8602-112">Remarks</span></span>  
 <span data-ttu-id="b8602-113">Mit der `Let`-Klausel können Sie Werte für jedes Abfrageergebnis berechnen und mithilfe eines Alias referenzieren.</span><span class="sxs-lookup"><span data-stu-id="b8602-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="b8602-114">Der Alias kann in anderen Klauseln verwendet werden, z. b. in der `Where`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="b8602-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="b8602-115">Mit der `Let`-Klausel können Sie eine Abfrage Anweisung erstellen, die leichter lesbar ist, da Sie einen Alias für eine in der Abfrage enthaltene Ausdrucks Klausel angeben und bei jeder Verwendung der Expression-Klausel den Alias ersetzen können.</span><span class="sxs-lookup"><span data-stu-id="b8602-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="b8602-116">Sie können eine beliebige Anzahl von `variable`-und `expression`-Zuweisungen in die `Let`-Klausel einschließen.</span><span class="sxs-lookup"><span data-stu-id="b8602-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="b8602-117">Trennen Sie jede Zuweisung durch ein Komma (,).</span><span class="sxs-lookup"><span data-stu-id="b8602-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8602-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8602-118">Example</span></span>  
 <span data-ttu-id="b8602-119">Im folgenden Codebeispiel wird die `Let`-Klausel verwendet, um einen Rabatt von 10% auf Produkte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b8602-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="b8602-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8602-120">See also</span></span>

- [<span data-ttu-id="b8602-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8602-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b8602-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="b8602-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b8602-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="b8602-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b8602-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="b8602-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b8602-125">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="b8602-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
