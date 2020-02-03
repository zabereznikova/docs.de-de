---
title: Join-Vorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 6e2ec1a0c8120f6869b7c0a196b77d118762a8dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868004"
---
# <a name="join-operations-c"></a><span data-ttu-id="ceef9-102">Verknüpfungsvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="ceef9-102">Join Operations (C#)</span></span>

<span data-ttu-id="ceef9-103">Eine *Verknüpfung* zweier Datenquellen entspricht der Zuordnung von Objekten einer Datenquelle zu den Objekten einer anderen Datenquelle, die ein Attribut gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="ceef9-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="ceef9-104">Die Verknüpfung stellt für Abfragen einen wichtigen Vorgang dar, die auf Datenquellen ausgerichtet sind, deren Beziehungen zueinander nicht direkt verfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="ceef9-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="ceef9-105">Bei der objektorientierten Programmierung könnte dies eine nicht modellierte Korrelation zwischen Objekten bedeuten, z. B. die entgegengesetzte Richtung einer unidirektionalen Beziehung.</span><span class="sxs-lookup"><span data-stu-id="ceef9-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="ceef9-106">Ein Beispiel einer unidirektionalen Beziehung ist die Klasse "Kunde" mit der Eigenschaft vom Typ "Ort", während die Klasse "Ort" keine Eigenschaft besitzt, die einer Auflistung von "Kunde"-Objekten entspricht.</span><span class="sxs-lookup"><span data-stu-id="ceef9-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="ceef9-107">Wenn Sie eine Liste von "Ort"-Objekten besitzen und alle Kunden in den einzelnen Orten finden möchten, könnten Sie eine Join-Operation verwenden, um diese zu finden.</span><span class="sxs-lookup"><span data-stu-id="ceef9-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="ceef9-108">Die im LINQ-Framework bereitgestellten Join-Methoden sind <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceef9-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="ceef9-109">Diese Methoden führen Gleichheitsverknüpfungen oder Verknüpfungen durch, bei denen zwei Datenquellen auf Basis der Gleichheit ihrer Schlüssel verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="ceef9-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="ceef9-110">(Zum Vergleich: Transact-SQL unterstützt auch andere Join-Operatoren als "ist gleich", z. B. den Operator "kleiner als".) Für relationale Datenbanken bedeutet dies, dass <xref:System.Linq.Enumerable.Join%2A> eine innere Verknüpfung implementiert, d.h. eine Art von Verknüpfung, bei der nur die Objekte zurückgegeben werden, die über eine Entsprechung im anderen Datensatz verfügen.</span><span class="sxs-lookup"><span data-stu-id="ceef9-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="ceef9-111">Für die <xref:System.Linq.Enumerable.GroupJoin%2A>-Methode hat bei relationalen Datenbanken kein direktes Äquivalent. Sie implementieren eine übergeordnete Menge innerer und linker äußerer Joins.</span><span class="sxs-lookup"><span data-stu-id="ceef9-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="ceef9-112">Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ceef9-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="ceef9-113">Die folgende Abbildung zeigt eine Konzeptansicht zweier Sätze sowie der Elemente innerhalb dieser Sätze, die entweder in eine innere oder linke äußere Verknüpfung einbezogen sind.</span><span class="sxs-lookup"><span data-stu-id="ceef9-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Zwei überlappende Kreise innen&#47;außen.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="ceef9-115">Methoden</span><span class="sxs-lookup"><span data-stu-id="ceef9-115">Methods</span></span>  
  
|<span data-ttu-id="ceef9-116">Methodenname</span><span class="sxs-lookup"><span data-stu-id="ceef9-116">Method Name</span></span>|<span data-ttu-id="ceef9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ceef9-117">Description</span></span>|<span data-ttu-id="ceef9-118">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ceef9-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="ceef9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceef9-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="ceef9-120">Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und extrahiert Wertepaare.</span><span class="sxs-lookup"><span data-stu-id="ceef9-120">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="ceef9-121">Verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und gruppiert die sich ergebenden Übereinstimmungen für die einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="ceef9-121">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ceef9-122">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ceef9-122">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="ceef9-123">Im folgenden Beispiel wird die `join … in … on … equals …`-Klausel verwendet, um zwei Sequenzen auf der Grundlage eines bestimmten Werts zu verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="ceef9-123">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="ceef9-124">Im folgenden Beispiel wird die `join … in … on … equals … into …`-Klausel verwendet, um zwei Sequenzen auf der Grundlage eines bestimmten Werts zu verknüpfen und die resultierenden Übereinstimmungen für jedes Element zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="ceef9-124">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="ceef9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceef9-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ceef9-126">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="ceef9-126">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="ceef9-127">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="ceef9-127">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="ceef9-128">Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="ceef9-128">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="ceef9-129">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="ceef9-129">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- <span data-ttu-id="ceef9-130">[Join mithilfe zusammengesetzter Schlüssel](../../../linq/join-by-using-composite-keys.md)</span><span class="sxs-lookup"><span data-stu-id="ceef9-130">[Join by using composite keys](../../../linq/join-by-using-composite-keys.md)</span></span>
- [<span data-ttu-id="ceef9-131">Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ceef9-131">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="ceef9-132">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="ceef9-132">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="ceef9-133">Ausführen von benutzerdefinierten Verknüpfungsoperationen</span><span class="sxs-lookup"><span data-stu-id="ceef9-133">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="ceef9-134">Ausführen von Gruppenverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="ceef9-134">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="ceef9-135">Ausführen innerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="ceef9-135">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="ceef9-136">Ausführen linker äußerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="ceef9-136">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="ceef9-137">Vorgehensweise: Auffüllen von Objektsammlungen mit Daten aus mehreren Quellen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ceef9-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
