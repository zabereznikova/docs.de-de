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
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004793"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="97e33-102">Distinct-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97e33-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="97e33-103">Schränkt die Werte der aktuellen Bereichs Variablen ein, um doppelte Werte in nachfolgenden Abfrage Klauseln auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="97e33-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97e33-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="97e33-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97e33-105">Remarks</span></span>  
 <span data-ttu-id="97e33-106">Mit der `Distinct`-Klausel können Sie eine Liste eindeutiger Elemente zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="97e33-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="97e33-107">Die `Distinct`-Klausel bewirkt, dass die Abfrage doppelte Abfrageergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="97e33-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="97e33-108">Die `Distinct`-Klausel gilt für doppelte Werte für alle Rückgabe Felder, die durch die `Select`-Klausel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="97e33-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="97e33-109">Wenn keine `Select`-Klausel angegeben ist, wird die `Distinct`-Klausel auf die Bereichs Variable der in der `From`-Klausel identifizierten Abfrage angewendet.</span><span class="sxs-lookup"><span data-stu-id="97e33-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="97e33-110">Wenn es sich bei der Bereichs Variablen nicht um einen unveränderlichen Typ handelt, wird von der Abfrage nur ein Abfrageergebnis ignoriert, wenn alle Member des Typs mit einem vorhandenen Abfrageergebnis zu vergleichen sind.</span><span class="sxs-lookup"><span data-stu-id="97e33-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97e33-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97e33-111">Example</span></span>  
 <span data-ttu-id="97e33-112">Der folgende Abfrage Ausdruck verbindet eine Liste von Kunden und eine Liste mit Kundenaufträgen.</span><span class="sxs-lookup"><span data-stu-id="97e33-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="97e33-113">Die `Distinct`-Klausel ist enthalten, um eine Liste der eindeutigen Kundennamen und Bestelldaten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="97e33-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="97e33-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97e33-114">See also</span></span>

- [<span data-ttu-id="97e33-115">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97e33-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="97e33-116">Abfragen</span><span class="sxs-lookup"><span data-stu-id="97e33-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="97e33-117">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="97e33-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="97e33-118">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="97e33-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="97e33-119">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="97e33-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
