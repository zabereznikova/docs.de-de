---
title: ORDER BY-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="acbb3-102">ORDER BY-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acbb3-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="acbb3-103">Gibt die Sortierreihenfolge für ein Abfrageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="acbb3-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acbb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acbb3-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="acbb3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="acbb3-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="acbb3-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="acbb3-106">Required.</span></span> <span data-ttu-id="acbb3-107">Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die bestimmen, wie die Reihenfolge der zurückgegebenen Werte werden.</span><span class="sxs-lookup"><span data-stu-id="acbb3-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="acbb3-108">Die Feldnamen müssen durch Kommas (,) getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="acbb3-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="acbb3-109">Bestimmen Sie jedes Feld als sortiert in aufsteigender oder absteigender Reihenfolge unter Verwendung der `Ascending` oder `Descending` Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="acbb3-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="acbb3-110">Wenn kein `Ascending` oder `Descending` -Schlüsselwort angegeben wird, wird eine aufsteigende die Standardsortierreihenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="acbb3-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="acbb3-111">Die Reihenfolge Sortierfelder erhalten Vorrang von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="acbb3-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acbb3-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acbb3-112">Remarks</span></span>  
 <span data-ttu-id="acbb3-113">Sie können die `Order By` -Klausel zum Sortieren der Ergebnisse einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="acbb3-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="acbb3-114">Die `Order By` -Klausel kann nur ein Ergebnis auf Grundlage der Bereichsvariablen für den aktuellen Bereich sortieren.</span><span class="sxs-lookup"><span data-stu-id="acbb3-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="acbb3-115">Z. B. die `Select` -Klausel führt einen neuen Bereich in einem Abfrageausdruck mit neuen Iterationsvariablen für diesen Bereich.</span><span class="sxs-lookup"><span data-stu-id="acbb3-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="acbb3-116">Bereichsvariablen, die definiert sind, bevor eine `Select` -Klausel in einer Abfrage sind nicht verfügbar, nachdem die `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="acbb3-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="acbb3-117">Aus diesem Grund sollten Sie die Ergebnisse nach einem Feld zu sortieren, die in nicht verfügbar ist die `Select` -Klausel, müssen Sie Ablegen der `Order By` -Klausel, bevor die `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="acbb3-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="acbb3-118">Ein Beispiel wenn Sie dazu müssten ist beim Sortieren der Abfrage nach Feldern, die nicht als Teil des Resultsets zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acbb3-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="acbb3-119">Auf- und absteigenden Reihenfolge für ein Feld wird durch die Implementierung von bestimmt die <xref:System.IComparable> Schnittstelle für den Datentyp des Felds.</span><span class="sxs-lookup"><span data-stu-id="acbb3-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="acbb3-120">Wenn der Datentyp nicht implementiert die <xref:System.IComparable> -Schnittstelle, die Sortierreihenfolge wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="acbb3-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acbb3-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acbb3-121">Example</span></span>  
 <span data-ttu-id="acbb3-122">Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `book` für die `books` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="acbb3-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="acbb3-123">Die `Order By` -Klausel sortiert das Ergebnis der Abfrage nach dem Preis in aufsteigender Reihenfolge (Standard).</span><span class="sxs-lookup"><span data-stu-id="acbb3-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="acbb3-124">Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="acbb3-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="acbb3-125">Die `Select` -Klausel wählt die `Title` und `Price` Eigenschaften als die von der Abfrage zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="acbb3-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="acbb3-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acbb3-126">Example</span></span>  
 <span data-ttu-id="acbb3-127">Die folgende Abfrage verwendet die `Order By` -Klausel, um das Ergebnis der Abfrage nach dem Preis in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="acbb3-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="acbb3-128">Bücher mit dem gleichen Preis werden nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="acbb3-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="acbb3-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="acbb3-129">Example</span></span>  
 <span data-ttu-id="acbb3-130">Die folgende Abfrage Ausdruck verwendet eine `Select` -Klausel, um die Buchtitel wählen, Preis, Veröffentlichungsdatum und erstellen.</span><span class="sxs-lookup"><span data-stu-id="acbb3-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="acbb3-131">Füllt dann die `Title`, `Price`, `PublishDate`, und `Author` Felder der Bereichsvariablen für den neuen Bereich.</span><span class="sxs-lookup"><span data-stu-id="acbb3-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="acbb3-132">Die `Order By` -Klausel sortiert die neue Bereichsvariable durch den Namen des Autors, Buchtitel und Preis.</span><span class="sxs-lookup"><span data-stu-id="acbb3-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="acbb3-133">Jede Spalte wird in die Standardreihenfolge (aufsteigend) sortiert.</span><span class="sxs-lookup"><span data-stu-id="acbb3-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="acbb3-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acbb3-134">See Also</span></span>  
 [<span data-ttu-id="acbb3-135">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acbb3-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="acbb3-136">Abfragen</span><span class="sxs-lookup"><span data-stu-id="acbb3-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="acbb3-137">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="acbb3-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="acbb3-138">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="acbb3-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
