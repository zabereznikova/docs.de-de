---
title: Typsystem (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: f99d63bd526981c4a9f079c25851dc9bbd89cf7c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738466"
---
# <a name="type-system-entity-sql"></a>Typsystem (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt eine Reihe von Typen:  
  
- Primitive (einfache) Typen wie `Int32` und `String.`  
  
- Nominale Typen, die im Schema definiert sind, z. B. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> und <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
- Anonyme Typen, die nicht explizit im Schema definiert sind: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> und <xref:System.Data.Metadata.Edm.RefType>.  
  
 In diesem Abschnitt werden die anonymen Typen erläutert, die nicht explizit im Schema definiert, aber von Entity SQL unterstützt werden. Informationen zu primitiven und nominalen Typen finden Sie unter [konzeptionelle Modelltypen (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).  
  
## <a name="rows"></a>Zeilen  
 Die Struktur einer Zeile ist abhängig von der Reihenfolge der typisierten und benannten Member, aus denen die Zeile besteht. Ein Zeilentyp hat keine Identität und kann nicht vererben. Instanzen des gleichen Zeilentyps sind äquivalent, wenn die Member entsprechend äquivalent sind. Zeilen weisen kein Verhalten über ihre strukturelle Äquivalenz hinaus auf und haben kein Äquivalent in der CLR. Abfragen können zu Strukturen führen, die Zeilen oder Auflistungen von Zeilen enthalten. Die API-Bindung zwischen den [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen und der Hostsprache definiert die Realisierung von Zeilen in der Abfrage, die das Ergebnis hervorgerufen hat. Weitere Informationen zum Erstellen einer Zeilen Instanz finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).  
  
## <a name="collections"></a>Auflistungen  
 Auflistungstypen stellen 0 (null) oder mehr Instanzen anderer Objekte dar. Weitere Informationen zum Erstellen von Sammlungen finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).  
  
## <a name="references"></a>Verweise  
 Ein Verweis ist ein logischer Zeiger auf eine bestimmte Entität in einer bestimmten Entitätenmenge.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt folgende Operatoren zum Erstellen, Löschen und Navigieren von Verweisen:  
  
- [REF](ref-entity-sql.md)  
  
- [CREATEREF](createref-entity-sql.md)  
  
- [KEY](key-entity-sql.md)  
  
- [DEREF](deref-entity-sql.md)  
  
 Sie können mit dem Memberzugriffsoperator (Punkt – `.`) durch einen Verweis navigieren. Der folgende Ausschnitt extrahiert die ID-Eigenschaft (von Reihenfolge) durch Navigation durch die r (Verweis)-Eigenschaft.  
  
```sql  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht vorhanden ist, hat das Ergebnis den Wert NULL.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
- [CAST](cast-entity-sql.md)
- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
