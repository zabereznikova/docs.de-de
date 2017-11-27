---
title: "Let-Klausel (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="30e03-102">Let-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30e03-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="30e03-103">Berechnet einen Wert ein, und weist sie einer neuen Variablen innerhalb der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="30e03-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30e03-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="30e03-105">Teile</span><span class="sxs-lookup"><span data-stu-id="30e03-105">Parts</span></span>  
  
|<span data-ttu-id="30e03-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="30e03-106">Term</span></span>|<span data-ttu-id="30e03-107">Definition</span><span class="sxs-lookup"><span data-stu-id="30e03-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="30e03-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30e03-108">Required.</span></span> <span data-ttu-id="30e03-109">Ein Alias, der verwendet werden kann, um auf die Ergebnisse des angegebenen Ausdrucks zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="30e03-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="30e03-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30e03-110">Required.</span></span> <span data-ttu-id="30e03-111">Ein Ausdruck, der ausgewertet wird, und der angegebenen Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="30e03-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e03-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30e03-112">Remarks</span></span>  
 <span data-ttu-id="30e03-113">Die `Let` -Klausel ermöglicht es Ihnen, berechnen Sie Werte für die einzelnen Abfrageergebnis und über einen Alias zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="30e03-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="30e03-114">Der Alias kann z. B. in anderen Klauseln verwendet werden die `Where` Klausel.</span><span class="sxs-lookup"><span data-stu-id="30e03-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="30e03-115">Die `Let` -Klausel ermöglichen es Ihnen, eine abfrageanweisung zu erstellen, ist einfacher zu lesen, da Geben Sie einen Alias für einen Ausdrucksklausel in der Abfrage enthaltenen und ersetzen den Alias jedes Mal wird die Ausdrucksklausel verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="30e03-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="30e03-116">Sie können eine beliebige Anzahl von einschließen `variable` und `expression` Zuweisungen in der `Let` Klausel.</span><span class="sxs-lookup"><span data-stu-id="30e03-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="30e03-117">Trennen Sie jede Zuweisung durch ein Komma (,) ein.</span><span class="sxs-lookup"><span data-stu-id="30e03-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30e03-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30e03-118">Example</span></span>  
 <span data-ttu-id="30e03-119">Im folgenden Codebeispiel wird mit der `Let` -Klausel, um 10 Prozent Rabatt zu Produkten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="30e03-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="30e03-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30e03-120">See Also</span></span>  
 [<span data-ttu-id="30e03-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30e03-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="30e03-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="30e03-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="30e03-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="30e03-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="30e03-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="30e03-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="30e03-125">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="30e03-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
