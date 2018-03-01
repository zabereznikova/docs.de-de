---
title: "Distinct-Klausel (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="48975-102">Distinct-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48975-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="48975-103">Schränkt die Werte der aktuellen Bereichsvariablen doppelte Werte in nachfolgenden Abfrageklauseln zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="48975-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48975-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48975-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="48975-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48975-105">Remarks</span></span>  
 <span data-ttu-id="48975-106">Sie können die `Distinct` -Klausel, um eine Liste von eindeutigen Elementen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="48975-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="48975-107">Die `Distinct` -Klausel bewirkt, dass die Abfrage, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="48975-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="48975-108">Die `Distinct` -Klausel gilt für doppelte Werte für alle Felder, die vom angegebenen Zurückgeben der `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="48975-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="48975-109">Wenn kein `Select` -Klausel angegeben ist, die `Distinct` -Klausel wird angewendet, für die Bereichsvariable für die Abfrage identifiziert, der `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="48975-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="48975-110">Ist die Bereichsvariable kein unveränderlicher Typ, ignoriert die Abfrage nur ein Abfrageergebnisses, wenn alle Elemente des Typs ein vorhandenes Abfrageergebnis übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="48975-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48975-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48975-111">Example</span></span>  
 <span data-ttu-id="48975-112">Der folgende Abfrageausdruck verknüpft eine Liste von Kunden und eine Liste mit Kundenaufträgen.</span><span class="sxs-lookup"><span data-stu-id="48975-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="48975-113">Die `Distinct` -Klausel zum Zurückgeben einer Liste von eindeutigen Kundennamen und Bestelldaten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="48975-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="48975-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48975-114">See Also</span></span>  
 [<span data-ttu-id="48975-115">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48975-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="48975-116">Abfragen</span><span class="sxs-lookup"><span data-stu-id="48975-116">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="48975-117">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="48975-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="48975-118">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="48975-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="48975-119">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="48975-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
