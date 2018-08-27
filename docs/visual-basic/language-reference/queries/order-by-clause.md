---
title: ORDER BY-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935486"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="1287e-102">ORDER BY-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1287e-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="1287e-103">Gibt die Sortierreihenfolge für eine Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="1287e-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1287e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1287e-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="1287e-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1287e-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="1287e-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1287e-106">Required.</span></span> <span data-ttu-id="1287e-107">Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die identifizieren, wie Sie die Reihenfolge der zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="1287e-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="1287e-108">Die Feldnamen müssen durch Kommas (,) getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="1287e-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="1287e-109">Sie können jedes Felds identifizieren, als sortiert in aufsteigender oder absteigender Reihenfolge unter Verwendung der `Ascending` oder `Descending` Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="1287e-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="1287e-110">Wenn kein `Ascending` oder `Descending` -Schlüsselwort angegeben ist, die die Sortierreihenfolge ist Aufsteigend.</span><span class="sxs-lookup"><span data-stu-id="1287e-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="1287e-111">Die Felder werden die Rangfolge von links nach rechts angegeben.</span><span class="sxs-lookup"><span data-stu-id="1287e-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1287e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1287e-112">Remarks</span></span>  
 <span data-ttu-id="1287e-113">Sie können die `Order By` -Klausel zum Sortieren der Ergebnisse einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1287e-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="1287e-114">Die `Order By` -Klausel kann nur basierend auf der die Bereichsvariable für den aktuellen Bereich sortieren.</span><span class="sxs-lookup"><span data-stu-id="1287e-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="1287e-115">Z. B. die `Select` Klausel führt einen neuen Bereich in einem Abfrageausdruck mit neuen Iterationsvariablen für diesen Bereich.</span><span class="sxs-lookup"><span data-stu-id="1287e-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="1287e-116">Bereichsvariablen, die definiert, bevor eine `Select` -Klausel in einer Abfrage sind nicht verfügbar, nachdem die `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="1287e-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="1287e-117">Aus diesem Grund sollten Sie die Ergebnisse nach einem Feld zu sortieren, die in nicht verfügbar ist die `Select` -Klausel, müssen Sie setzen das `Order By` -Klausel, bevor die `Select` Klausel.</span><span class="sxs-lookup"><span data-stu-id="1287e-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="1287e-118">Ein Beispiel wenn Sie dazu müssten ist, wenn eine Abfrage nach Feldern zu sortieren, die nicht als Teil des Ergebnisses zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1287e-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="1287e-119">Auf- und absteigender Reihenfolge aus, für ein Feld von der Implementierung der bestimmt wird die <xref:System.IComparable> Schnittstelle für den Datentyp des Felds.</span><span class="sxs-lookup"><span data-stu-id="1287e-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="1287e-120">Wenn der Datentyp nicht implementiert die <xref:System.IComparable> -Schnittstelle, die Sortierreihenfolge wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1287e-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1287e-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1287e-121">Example</span></span>  
 <span data-ttu-id="1287e-122">Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `book` für die `books` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1287e-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="1287e-123">Die `Order By` -Klausel sortiert das Resultset der Abfrage nach Preis in aufsteigender Reihenfolge (Standard).</span><span class="sxs-lookup"><span data-stu-id="1287e-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="1287e-124">Bücher mit den gleichen Preis sind nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="1287e-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="1287e-125">Die `Select` -Klausel wählt die `Title` und `Price` Eigenschaften wie die von der Abfrage zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="1287e-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="1287e-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1287e-126">Example</span></span>  
 <span data-ttu-id="1287e-127">Der folgende Abfrageausdruck verwendet die `Order By` -Klausel, um das Ergebnis der Abfrage nach Preis in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="1287e-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="1287e-128">Bücher mit den gleichen Preis sind nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="1287e-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="1287e-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1287e-129">Example</span></span>  
 <span data-ttu-id="1287e-130">Der folgende Abfrageausdruck verwendet eine `Select` -Klausel, um Wählen Sie den Titel, Preis, Veröffentlichungsdatum und erstellen.</span><span class="sxs-lookup"><span data-stu-id="1287e-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="1287e-131">Dann füllt es die `Title`, `Price`, `PublishDate`, und `Author` Felder die Bereichsvariable für den neuen Bereich.</span><span class="sxs-lookup"><span data-stu-id="1287e-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="1287e-132">Die `Order By` -Klausel sortiert die neue Bereichsvariable, die vom Autorenname, Titel und Preis.</span><span class="sxs-lookup"><span data-stu-id="1287e-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="1287e-133">Jede Spalte ist in der Standardreihenfolge (in aufsteigender Reihenfolge) sortiert.</span><span class="sxs-lookup"><span data-stu-id="1287e-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1287e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1287e-134">See Also</span></span>  
 [<span data-ttu-id="1287e-135">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1287e-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="1287e-136">Abfragen</span><span class="sxs-lookup"><span data-stu-id="1287e-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="1287e-137">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="1287e-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="1287e-138">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="1287e-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
