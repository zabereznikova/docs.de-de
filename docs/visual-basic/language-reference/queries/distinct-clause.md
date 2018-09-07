---
title: Distinct-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 18d09d8018303aab6a69801c84c7ec9c6ea19ca9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083831"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="f969a-102">Distinct-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f969a-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="f969a-103">Schränkt die Werte des die aktuelle Bereichsvariable, doppelte Werte in nachfolgenden Abfrageklauseln zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="f969a-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f969a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f969a-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="f969a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f969a-105">Remarks</span></span>  
 <span data-ttu-id="f969a-106">Sie können die `Distinct` -Klausel, um eine Liste von eindeutigen Elementen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f969a-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="f969a-107">Die `Distinct` -Klausel bewirkt, dass die Abfrage, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f969a-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="f969a-108">Die `Distinct` Klausel gilt für doppelte Werte für alle Felder, die anhand des Zurückgeben der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="f969a-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="f969a-109">Wenn kein `Select` -Klausel angegeben ist, die `Distinct` -Klausel wird angewendet, auf die Bereichsvariable für die Abfrage, der `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="f969a-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="f969a-110">Ist die Bereichsvariable kein unveränderlicher Typ, ignoriert die Abfrage nur ein Abfrageergebnis zu, wenn alle Elemente des Typs einer vorhandenen Ergebnis der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f969a-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f969a-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f969a-111">Example</span></span>  
 <span data-ttu-id="f969a-112">Der folgende Abfrageausdruck verknüpft eine Liste von Kunden und eine Liste mit kundenbestellungen.</span><span class="sxs-lookup"><span data-stu-id="f969a-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="f969a-113">Die `Distinct` -Klausel zum Zurückgeben einer Liste der Namen der eindeutigen Kunden und Sortieren von Datumsangaben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f969a-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f969a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f969a-114">See Also</span></span>  
 [<span data-ttu-id="f969a-115">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f969a-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="f969a-116">Abfragen</span><span class="sxs-lookup"><span data-stu-id="f969a-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="f969a-117">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="f969a-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="f969a-118">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="f969a-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="f969a-119">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="f969a-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
