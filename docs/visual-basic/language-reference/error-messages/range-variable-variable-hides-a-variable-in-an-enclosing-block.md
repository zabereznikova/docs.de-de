---
title: Range-Variable &lt;Variable&gt; verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit deklarierte Variable in einem Abfrageausdruck
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: aef52ea912a4180a6505949c8077296628592c72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748115"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="8171b-102">Range-Variable &lt;Variable&gt; verbirgt eine Variable in einem einschließenden Block, eine zuvor definierte Bereichsvariable oder eine implizit deklarierte Variable in einem Abfrageausdruck</span><span class="sxs-lookup"><span data-stu-id="8171b-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="8171b-103">Ein Bereich Variablenname, der im angegebenen ein `Select`, `From`, `Aggregate`, oder `Let` Klausel, um Duplikate der Name einer Bereichsvariablen, die bereits zuvor angegeben werden, in der Abfrage oder den Namen einer Variablen, die von der Abfrage implizit deklariert ist z. B. ein Feldname oder der Name der Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="8171b-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="8171b-104">**Fehler-ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="8171b-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8171b-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8171b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="8171b-106">Stellen Sie sicher, dass alle Bereichsvariablen in einem bestimmten Abfragebereich eindeutige Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8171b-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="8171b-107">Sie können eine Abfrage einschließen, in Klammern einschließen, um sicherzustellen, dass geschachtelte Abfragen einen eindeutigen Bereich verfügen.</span><span class="sxs-lookup"><span data-stu-id="8171b-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8171b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8171b-108">See also</span></span>
- [<span data-ttu-id="8171b-109">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8171b-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8171b-110">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="8171b-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8171b-111">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="8171b-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="8171b-112">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="8171b-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="8171b-113">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="8171b-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
