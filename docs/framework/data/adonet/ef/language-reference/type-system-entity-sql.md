---
title: Typsystem (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: d4c8ba7a9d9b58220455b50ff99960fa132c00c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200991"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="7eca1-102">Typsystem (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7eca1-102">Type System (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="7eca1-103">unterstützt eine Reihe von Typen:</span><span class="sxs-lookup"><span data-stu-id="7eca1-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="7eca1-104">Primitive (einfache) Typen wie `Int32` und `String.`</span><span class="sxs-lookup"><span data-stu-id="7eca1-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="7eca1-105">Nominale Typen, die im Schema definiert sind, z. B. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> und <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="7eca1-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="7eca1-106">Anonyme Typen, die nicht explizit im Schema definiert sind: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> und <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="7eca1-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="7eca1-107">In diesem Abschnitt werden die anonymen Typen erläutert, die nicht explizit im Schema definiert, aber von Entity SQL unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7eca1-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="7eca1-108">Informationen zu primitiven und nominalen Typen finden Sie unter [konzeptionelle Modelltypen (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="7eca1-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="7eca1-109">Zeilen</span><span class="sxs-lookup"><span data-stu-id="7eca1-109">Rows</span></span>  

 <span data-ttu-id="7eca1-110">Die Struktur einer Zeile ist abhängig von der Reihenfolge der typisierten und benannten Member, aus denen die Zeile besteht.</span><span class="sxs-lookup"><span data-stu-id="7eca1-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="7eca1-111">Ein Zeilentyp hat keine Identität und kann nicht vererben.</span><span class="sxs-lookup"><span data-stu-id="7eca1-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="7eca1-112">Instanzen des gleichen Zeilentyps sind äquivalent, wenn die Member entsprechend äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="7eca1-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="7eca1-113">Zeilen weisen kein Verhalten über ihre strukturelle Äquivalenz hinaus auf und haben kein Äquivalent in der CLR.</span><span class="sxs-lookup"><span data-stu-id="7eca1-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="7eca1-114">Abfragen können zu Strukturen führen, die Zeilen oder Auflistungen von Zeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7eca1-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="7eca1-115">Die API-Bindung zwischen den [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen und der Hostsprache definiert die Realisierung von Zeilen in der Abfrage, die das Ergebnis hervorgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="7eca1-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="7eca1-116">Weitere Informationen zum Erstellen einer Zeilen Instanz finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7eca1-116">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="7eca1-117">Auflistungen</span><span class="sxs-lookup"><span data-stu-id="7eca1-117">Collections</span></span>  

 <span data-ttu-id="7eca1-118">Auflistungstypen stellen 0 (null) oder mehr Instanzen anderer Objekte dar.</span><span class="sxs-lookup"><span data-stu-id="7eca1-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="7eca1-119">Weitere Informationen zum Erstellen von Sammlungen finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7eca1-119">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="7eca1-120">References</span><span class="sxs-lookup"><span data-stu-id="7eca1-120">References</span></span>  

 <span data-ttu-id="7eca1-121">Ein Verweis ist ein logischer Zeiger auf eine bestimmte Entität in einer bestimmten Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="7eca1-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="7eca1-122">unterstützt folgende Operatoren zum Erstellen, Löschen und Navigieren von Verweisen:</span><span class="sxs-lookup"><span data-stu-id="7eca1-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="7eca1-123">Atur</span><span class="sxs-lookup"><span data-stu-id="7eca1-123">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="7eca1-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="7eca1-124">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="7eca1-125">KEY</span><span class="sxs-lookup"><span data-stu-id="7eca1-125">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="7eca1-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="7eca1-126">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="7eca1-127">Sie können mit dem Memberzugriffsoperator (Punkt – `.`) durch einen Verweis navigieren.</span><span class="sxs-lookup"><span data-stu-id="7eca1-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="7eca1-128">Der folgende Ausschnitt extrahiert die ID-Eigenschaft (von Reihenfolge) durch Navigation durch die r (Verweis)-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7eca1-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 <span data-ttu-id="7eca1-129">Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht vorhanden ist, hat das Ergebnis den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="7eca1-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eca1-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eca1-130">See also</span></span>

- [<span data-ttu-id="7eca1-131">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7eca1-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="7eca1-132">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="7eca1-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="7eca1-133">CAST</span><span class="sxs-lookup"><span data-stu-id="7eca1-133">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="7eca1-134">CSDL-, SSDL- und MSL-Spezifikationen</span><span class="sxs-lookup"><span data-stu-id="7eca1-134">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
