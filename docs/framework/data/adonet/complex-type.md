---
title: Komplexer Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 50b29e5ae0df37238a16ba08898d307918f0b439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="complex-type"></a>Komplexer Typ
Ein *komplexen Typ* ist eine Vorlage zum Definieren von umfangreichen, strukturierter Eigenschaften für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) oder andere komplexe Typen. Jede Vorlage enthält Folgendes:  
  
-   Eine eindeutige Bezeichnung. (erforderlich)  
  
    > [!NOTE]
    >  Der Name eines komplexen Typs darf nicht mit dem Namen eines Entitätstyps innerhalb des gleichen Namespace übereinstimmen.  
  
-   Daten in Form einer oder mehrerer [Eigenschaften](../../../../docs/framework/data/adonet/property.md). (Optional)  
  
    > [!NOTE]
    >  Eine Eigenschaft eines komplexen Typs kann ein anderer komplexer Typ sein.  
  
 Ein komplexer Typ ähnelt insofern einem Entitätstyp, als ein komplexer Typ eine Datennutzlast in Form von primitiven Typeigenschaften oder anderen komplexen Typen enthalten kann. Es gibt jedoch einige Hauptunterschiede zwischen komplexen Typen und Entitätstypen:  
  
-   Komplexe Typen weisen keine Identitäten auf und können daher nicht unabhängig sein. Komplexe Typen können nur Eigenschaften von Entitätstypen oder anderen komplexen Typen sein.  
  
-   Komplexe Typen können nicht beteiligt [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md). Enden einer Zuordnung kann ein komplexer Typ sein und daher [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) kann nicht für complex-Typen definiert werden.  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen komplexen Typ, Adress, mit den primitiven Typeigenschaften `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Deklarieren Sie den Eigenschaftentyp in der Entitätstypdefinition, um den komplexen Typ `Address` (oben) als Eigenschaft für einen Entitätstyp zu definieren. Die folgende CSDL deklariert die `Address`-Eigenschaft als komplexen Typ für einen Entitätstyp (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
