---
title: Typdefinitionen (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b890a56daeab1c3a0fbb8c95ec29a81cb7689e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-definitions-entity-sql"></a>Typdefinitionen (Entity SQL)
Eine Typdefinition wird in der Deklarationsanweisung einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Inlinefunktion verwendet.  
  
## <a name="remarks"></a>Hinweise  
 Die deklarationsanweisung für eine Inlinefunktion besteht aus den [Funktion](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) Schlüsselwort, gefolgt von der Bezeichner, der Funktionsname (z. B. "MyAvg") gefolgt von einem Parameterdefinitionsliste in Klammern (für darstellt beispielsweise "Decimal gefolgten.  
  
 Die Parameterdefinitionsliste besteht aus 0 (null) oder mehreren Parameterdefinitionen. Jede Parameterdefinition besteht aus einem von einer Typdefinition (z. B. "Auflistung (Decimal)") gefolgten Bezeichner (der Name des Parameters der Funktion, z. B. "Gebühren").  
  
 Dies sind die zulässigen Typdefinitionen:  
  
-   Der Typ des Bezeichners (z. B. "Int32" oder "AdventureWorks.Order").  
  
-   Das `COLLECTION`-Schlüsselwort, das von einer anderen Typdefinition in Klammern gefolgt wird (z. B. "Collection(AdventureWorks.Order)").  
  
-   Das von einer Liste von Eigenschaftendefinitionen in Klammern (z. B. "Row(x AdventureWorks.Order))" gefolgte ROW-Schlüsselwort. Eigenschaftendefinitionen besitzen ein Format wie z. B. "`identifier type_definition`, `identifier type_definition`,...".  
  
-   Das vom Typ des Bezeichners in Klammern (z. B. "Ref(AdventureWorks.Order)") gefolgte REF-Schlüsselwort. Der REF-Typdefinitionsoperator erfordert einen Entitätstyp als Argument. Sie können keinen primitiven Typ als Argument angeben.  
  
 Sie können Typdefinitionen auch schachteln (z. B., "Collection(Row(x Ref(AdventureWorks.Order)))").  
  
 Die Typdefinitionsoptionen lauten folgendermaßen:  
  
-   `IdentifierName supported_type` oder  
  
-   `IdentifierName` COLLECTION(`type_definition`) oder  
  
-   `IdentifierName` ROW(`property_definition`) oder  
  
-   `IdentifierName` REF(`supported_entity_type`)  
  
 Die Eigenschaftendefinitionsoption ist `IdentifierName type_definition`.  
  
 Unterstützte Typen sind alle Typen im aktuellen Namespace. Diese schließen sowohl primitive Typen als auch Entitätstypen ein.  
  
 Unterstützte Entitätstypen verweisen im aktuellen Namespace nur auf Entitätstypen. Sie schließen keine primitiven Typen ein.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine einfache Typdefinition dargestellt.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 Dies ist ein Beispiel für eine COLLECTION-Typdefinition.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 Dies ist ein Beispiel für eine ROW-Typdefinition.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 Dies ist ein Beispiel für eine REF-Typdefinition.  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
