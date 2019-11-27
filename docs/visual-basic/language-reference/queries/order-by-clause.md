---
title: Order By-Klausel
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
ms.openlocfilehash: a7104e3dd82ff2dde2911861ce98a7367faf3b25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350420"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="b906d-102">ORDER BY-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b906d-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="b906d-103">Gibt die Sortierreihenfolge für ein Abfrageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="b906d-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b906d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b906d-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b906d-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="b906d-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="b906d-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b906d-106">Required.</span></span> <span data-ttu-id="b906d-107">Ein oder mehrere Felder aus dem aktuellen Abfrageergebnis, die die Reihenfolge der zurückgegebenen Werte bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b906d-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="b906d-108">Die Feldnamen müssen durch Kommas (,) getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="b906d-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="b906d-109">Sie können jedes Feld in aufsteigender oder absteigender Reihenfolge mithilfe der Schlüsselwörter `Ascending` oder `Descending` ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b906d-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="b906d-110">Wenn keine `Ascending` oder `Descending` Schlüsselwort angegeben ist, ist die Standard Sortierreihenfolge aufsteigend.</span><span class="sxs-lookup"><span data-stu-id="b906d-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="b906d-111">Die Sortier Reihenfolgen Felder haben Vorrang vor von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="b906d-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b906d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b906d-112">Remarks</span></span>  
 <span data-ttu-id="b906d-113">Sie können die `Order By`-Klausel verwenden, um die Ergebnisse einer Abfrage zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b906d-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="b906d-114">Die `Order By`-Klausel kann ein Ergebnis nur basierend auf der Bereichs Variablen für den aktuellen Gültigkeitsbereich sortieren.</span><span class="sxs-lookup"><span data-stu-id="b906d-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="b906d-115">Die `Select`-Klausel führt z. b. einen neuen Bereich in einem Abfrage Ausdruck mit neuen Iterations Variablen für diesen Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="b906d-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="b906d-116">Bereichs Variablen, die vor einer `Select`-Klausel in einer Abfrage definiert sind, sind nach der `Select`-Klausel nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b906d-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="b906d-117">Wenn Sie also die Ergebnisse nach einem Feld sortieren möchten, das in der `Select`-Klausel nicht verfügbar ist, müssen Sie die `Order By`-Klausel vor der `Select`-Klausel ablegen.</span><span class="sxs-lookup"><span data-stu-id="b906d-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="b906d-118">Ein Beispiel hierfür wäre, wenn Sie die Abfrage nach Feldern sortieren möchten, die nicht als Teil des Ergebnisses zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b906d-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="b906d-119">Die aufsteigende und absteigende Reihenfolge für ein Feld wird durch die Implementierung der <xref:System.IComparable>-Schnittstelle für den Datentyp des Felds bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b906d-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="b906d-120">Wenn der Datentyp die <xref:System.IComparable>-Schnittstelle nicht implementiert, wird die Sortierreihenfolge ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b906d-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b906d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b906d-121">Example</span></span>  
 <span data-ttu-id="b906d-122">Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um eine Bereichs Variable `book` für die `books` Collection zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b906d-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="b906d-123">Die `Order By`-Klausel sortiert das Abfrageergebnis nach Preis in aufsteigender Reihenfolge (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="b906d-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="b906d-124">Bücher mit demselben Preis werden nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="b906d-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="b906d-125">Die `Select`-Klausel wählt die Eigenschaften `Title` und `Price` als die von der Abfrage zurückgegebenen Werte aus.</span><span class="sxs-lookup"><span data-stu-id="b906d-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="b906d-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b906d-126">Example</span></span>  
 <span data-ttu-id="b906d-127">Der folgende Abfrage Ausdruck verwendet die `Order By`-Klausel, um das Abfrageergebnis nach Preis in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b906d-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="b906d-128">Bücher mit demselben Preis werden nach Titel in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="b906d-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="b906d-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b906d-129">Example</span></span>  
 <span data-ttu-id="b906d-130">Der folgende Abfrage Ausdruck verwendet eine `Select`-Klausel, um den Buchtitel, den Preis, das Veröffentlichungsdatum und den Autor auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b906d-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="b906d-131">Anschließend werden die Felder "`Title`", "`Price`", "`PublishDate`" und "`Author`" der Bereichs Variablen für den neuen Bereich aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b906d-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="b906d-132">Die `Order By`-Klausel ordnet die neue Bereichs Variable nach Autor Name, Titel Titel und Preis an.</span><span class="sxs-lookup"><span data-stu-id="b906d-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="b906d-133">Jede Spalte wird in der Standard Reihenfolge sortiert (aufsteigend).</span><span class="sxs-lookup"><span data-stu-id="b906d-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="b906d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b906d-134">See also</span></span>

- [<span data-ttu-id="b906d-135">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b906d-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b906d-136">Abfragen</span><span class="sxs-lookup"><span data-stu-id="b906d-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b906d-137">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="b906d-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b906d-138">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="b906d-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
