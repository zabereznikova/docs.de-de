---
title: Join-Vorgänge (C#)
description: Bei einem Join von zwei Datenquellen werden Objekte anderen Objekten mit einem gemeinsamen Attribut aus unterschiedlichen Datenquellen zugeordnet. Informationen zu Join-Methoden im LINQ-Framework in C#
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165696"
---
# <a name="no-locjoin-operations-c"></a><span data-ttu-id="33e9b-104">Join-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="33e9b-104">Join Operations (C#)</span></span>

<span data-ttu-id="33e9b-105">Eine *Verknüpfung* zweier Datenquellen entspricht der Zuordnung von Objekten einer Datenquelle zu den Objekten einer anderen Datenquelle, die ein Attribut gemeinsam haben.</span><span class="sxs-lookup"><span data-stu-id="33e9b-105">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="33e9b-106">Der Join-Vorgang ist für Abfragen sehr wichtig. Er ist auf Datenquellen ausgerichtet, deren Beziehungen zueinander nicht direkt verfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="33e9b-106">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="33e9b-107">Bei der objektorientierten Programmierung könnte dies eine nicht modellierte Korrelation zwischen Objekten bedeuten, z. B. die entgegengesetzte Richtung einer unidirektionalen Beziehung.</span><span class="sxs-lookup"><span data-stu-id="33e9b-107">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="33e9b-108">Ein Beispiel einer unidirektionalen Beziehung ist die Klasse "Kunde" mit der Eigenschaft vom Typ "Ort", während die Klasse "Ort" keine Eigenschaft besitzt, die einer Auflistung von "Kunde"-Objekten entspricht.</span><span class="sxs-lookup"><span data-stu-id="33e9b-108">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="33e9b-109">Wenn Sie eine Liste von "Ort"-Objekten besitzen und alle Kunden in den einzelnen Orten finden möchten, könnten Sie eine Join-Operation verwenden, um diese zu finden.</span><span class="sxs-lookup"><span data-stu-id="33e9b-109">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="33e9b-110">Die im LINQ-Framework bereitgestellten Join-Methoden sind <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="33e9b-110">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="33e9b-111">Diese Methoden führen Gleichheitsverknüpfungen oder Verknüpfungen durch, bei denen zwei Datenquellen auf Basis der Gleichheit ihrer Schlüssel verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="33e9b-111">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="33e9b-112">(Zum Vergleich: Transact-SQL unterstützt auch andere Join-Operatoren als "ist gleich", z. B. den Operator "kleiner als".) Für relationale Datenbanken bedeutet dies, dass <xref:System.Linq.Enumerable.Join%2A> eine innere Verknüpfung implementiert, d.h. eine Art von Verknüpfung, bei der nur die Objekte zurückgegeben werden, die über eine Entsprechung im anderen Datensatz verfügen.</span><span class="sxs-lookup"><span data-stu-id="33e9b-112">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="33e9b-113">Für die <xref:System.Linq.Enumerable.GroupJoin%2A>-Methode hat bei relationalen Datenbanken kein direktes Äquivalent. Sie implementieren eine übergeordnete Menge innerer und linker äußerer Joins.</span><span class="sxs-lookup"><span data-stu-id="33e9b-113">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="33e9b-114">Ein Left Outer Join ist eine Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="33e9b-114">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="33e9b-115">Die folgende Abbildung zeigt eine Konzeptansicht zweier Sätze sowie der Elemente innerhalb dieser Sätze, die entweder in eine innere oder linke äußere Verknüpfung einbezogen sind.</span><span class="sxs-lookup"><span data-stu-id="33e9b-115">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![Zwei überlappende Kreise innen&#47;außen.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="33e9b-117">Methoden</span><span class="sxs-lookup"><span data-stu-id="33e9b-117">Methods</span></span>  
  
|<span data-ttu-id="33e9b-118">Methodenname</span><span class="sxs-lookup"><span data-stu-id="33e9b-118">Method Name</span></span>|<span data-ttu-id="33e9b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e9b-119">Description</span></span>|<span data-ttu-id="33e9b-120">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="33e9b-120">C# Query Expression Syntax</span></span>|<span data-ttu-id="33e9b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33e9b-121">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="33e9b-122">Die Join-Methode verknüpft zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und extrahiert Wertepaare.</span><span class="sxs-lookup"><span data-stu-id="33e9b-122">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="33e9b-123">Die Methode verknüpft (Join) zwei Sequenzen auf Basis von Schlüsselauswahlfunktionen und gruppiert die daraus resultierenden Übereinstimmungen für die einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="33e9b-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="33e9b-124">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="33e9b-124">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="33e9b-125">Im folgenden Beispiel wird die `join … in … on … equals …`-Klausel verwendet, um zwei Sequenzen auf der Grundlage eines bestimmten Werts zu verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="33e9b-125">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="33e9b-126">Im folgenden Beispiel wird die `join … in … on … equals … into …`-Klausel verwendet, um zwei Sequenzen auf der Grundlage eines bestimmten Werts zu verknüpfen und die resultierenden Übereinstimmungen für jedes Element zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="33e9b-126">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="33e9b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33e9b-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="33e9b-128">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="33e9b-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="33e9b-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="33e9b-129">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="33e9b-130">Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="33e9b-130">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="33e9b-131">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="33e9b-131">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="33e9b-132">Join mithilfe zusammengesetzter Schlüssel</span><span class="sxs-lookup"><span data-stu-id="33e9b-132">Join by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="33e9b-133">Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33e9b-133">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="33e9b-134">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="33e9b-134">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="33e9b-135">Ausführen von benutzerdefinierten Verknüpfungsoperationen</span><span class="sxs-lookup"><span data-stu-id="33e9b-135">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="33e9b-136">Ausführen von Gruppenverknüpfungen</span><span class="sxs-lookup"><span data-stu-id="33e9b-136">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="33e9b-137">Ausführen innerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="33e9b-137">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="33e9b-138">Ausführen linker äußerer Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="33e9b-138">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="33e9b-139">Vorgehensweise: Auffüllen von Objektsammlungen mit Daten aus mehreren Quellen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33e9b-139">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
