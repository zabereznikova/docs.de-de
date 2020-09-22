---
title: Distinct-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 49eaab2e6a8c48d61518ea51ef2f644b6eb48314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875282"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="f5295-102">Distinct-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5295-102">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="f5295-103">Schränkt die Werte der aktuellen Bereichs Variablen ein, um doppelte Werte in nachfolgenden Abfrage Klauseln auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="f5295-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5295-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5295-104">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="f5295-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f5295-105">Remarks</span></span>  

 <span data-ttu-id="f5295-106">Mit der-Klausel können Sie `Distinct` eine Liste eindeutiger Elemente zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f5295-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="f5295-107">Die- `Distinct` Klausel bewirkt, dass die Abfrage doppelte Abfrageergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f5295-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="f5295-108">Die- `Distinct` Klausel gilt für doppelte Werte für alle Rückgabe Felder, die durch die-Klausel angegeben werden `Select` .</span><span class="sxs-lookup"><span data-stu-id="f5295-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="f5295-109">Wenn keine- `Select` Klausel angegeben wird, `Distinct` wird die-Klausel auf die Bereichs Variable für die in der-Klausel identifizierte Abfrage angewendet `From` .</span><span class="sxs-lookup"><span data-stu-id="f5295-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="f5295-110">Wenn es sich bei der Bereichs Variablen nicht um einen unveränderlichen Typ handelt, wird von der Abfrage nur ein Abfrageergebnis ignoriert, wenn alle Member des Typs mit einem vorhandenen Abfrageergebnis zu vergleichen sind.</span><span class="sxs-lookup"><span data-stu-id="f5295-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5295-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5295-111">Example</span></span>  

 <span data-ttu-id="f5295-112">Der folgende Abfrage Ausdruck verbindet eine Liste von Kunden und eine Liste mit Kundenaufträgen.</span><span class="sxs-lookup"><span data-stu-id="f5295-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="f5295-113">Die `Distinct` -Klausel ist enthalten, um eine Liste der eindeutigen Kundennamen und Bestelldaten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f5295-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="f5295-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5295-114">See also</span></span>

- [<span data-ttu-id="f5295-115">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5295-115">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f5295-116">Abfragen</span><span class="sxs-lookup"><span data-stu-id="f5295-116">Queries</span></span>](index.md)
- [<span data-ttu-id="f5295-117">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="f5295-117">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="f5295-118">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="f5295-118">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="f5295-119">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="f5295-119">Where Clause</span></span>](where-clause.md)
