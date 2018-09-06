---
title: Typsystem (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: 270b0981214e674d220025ad52c7c94ee3a66224
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878220"
---
# <a name="type-system-entity-sql"></a>Typsystem (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt eine Reihe von Typen:  
  
-   Primitive (einfache) Typen wie `Int32` und `String.`  
  
-   Nominale Typen, die im Schema definiert sind, z. B. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> und <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
-   Anonyme Typen, die nicht explizit im Schema definiert sind: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> und <xref:System.Data.Metadata.Edm.RefType>.  
  
 In diesem Abschnitt werden die anonymen Typen behandelt, die nicht explizit im Schema definiert, jedoch von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt werden. Weitere Informationen zu primitiven und nominalen Typen finden Sie unter [konzeptionelle Modelltypen (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4).  
  
## <a name="rows"></a>Zeilen  
 Die Struktur einer Zeile ist abhängig von der Reihenfolge der typisierten und benannten Member, aus denen die Zeile besteht. Ein Zeilentyp hat keine Identität und kann nicht vererben. Instanzen des gleichen Zeilentyps sind äquivalent, wenn die Member entsprechend äquivalent sind. Zeilen weisen kein Verhalten über ihre strukturelle Äquivalenz hinaus auf und haben kein Äquivalent in der CLR. Abfragen können zu Strukturen führen, die Zeilen oder Auflistungen von Zeilen enthalten. Die API-Bindung zwischen den [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen und der Hostsprache definiert die Realisierung von Zeilen in der Abfrage, die das Ergebnis hervorgerufen hat. Informationen zum Erstellen einer Zeileninstanz finden Sie unter [Typen erstellen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="collections"></a>Auflistungen  
 Auflistungstypen stellen 0 (null) oder mehr Instanzen anderer Objekte dar. Informationen zum Erstellen von Auflistungen finden Sie unter [Typen erstellen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="references"></a>Verweise  
 Ein Verweis ist ein logischer Zeiger auf eine bestimmte Entität in einer bestimmten Entitätenmenge.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt folgende Operatoren zum Erstellen, Löschen und Navigieren von Verweisen:  
  
-   [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 Sie können mit dem Memberzugriffsoperator (Punkt – `.`) durch einen Verweis navigieren. Der folgende Ausschnitt extrahiert die ID-Eigenschaft (von Reihenfolge) durch Navigation durch die r (Verweis)-Eigenschaft.  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 Wenn der Verweiswert NULL ist oder das Ziel des Verweises nicht vorhanden ist, hat das Ergebnis den Wert NULL.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)  
 [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
