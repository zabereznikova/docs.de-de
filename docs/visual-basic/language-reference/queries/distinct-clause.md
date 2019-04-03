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
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830057"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="85a45-102">Distinct-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a45-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="85a45-103">Schränkt die Werte des die aktuelle Bereichsvariable, doppelte Werte in nachfolgenden Abfrageklauseln zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="85a45-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85a45-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="85a45-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85a45-105">Remarks</span></span>  
 <span data-ttu-id="85a45-106">Sie können die `Distinct` -Klausel, um eine Liste von eindeutigen Elementen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="85a45-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="85a45-107">Die `Distinct` -Klausel bewirkt, dass die Abfrage, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="85a45-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="85a45-108">Die `Distinct` Klausel gilt für doppelte Werte für alle Felder, die anhand des Zurückgeben der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="85a45-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="85a45-109">Wenn kein `Select` -Klausel angegeben ist, die `Distinct` -Klausel wird angewendet, auf die Bereichsvariable für die Abfrage, der `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="85a45-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="85a45-110">Ist die Bereichsvariable kein unveränderlicher Typ, ignoriert die Abfrage nur ein Abfrageergebnis zu, wenn alle Elemente des Typs einer vorhandenen Ergebnis der Abfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="85a45-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85a45-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85a45-111">Example</span></span>  
 <span data-ttu-id="85a45-112">Der folgende Abfrageausdruck verknüpft eine Liste von Kunden und eine Liste mit kundenbestellungen.</span><span class="sxs-lookup"><span data-stu-id="85a45-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="85a45-113">Die `Distinct` -Klausel zum Zurückgeben einer Liste der Namen der eindeutigen Kunden und Sortieren von Datumsangaben enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="85a45-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="85a45-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85a45-114">See also</span></span>

- [<span data-ttu-id="85a45-115">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85a45-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="85a45-116">Abfragen</span><span class="sxs-lookup"><span data-stu-id="85a45-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="85a45-117">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="85a45-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="85a45-118">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="85a45-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="85a45-119">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="85a45-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
