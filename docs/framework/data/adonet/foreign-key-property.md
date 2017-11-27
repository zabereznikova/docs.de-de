---
title: "Fremdschlüsseleigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 626feac70099667e0dc15b12043834bda6d4b20e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="foreign-key-property"></a>Fremdschlüsseleigenschaft
Ein *Fremdschlüsseleigenschaft* im Entity Data Model (EDM) ist ein primitiver Typ [Eigenschaft](../../../../docs/framework/data/adonet/property.md) (oder einen Satz von primitiven Typeigenschaften) auf eine [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) , enthält die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) eines anderen Entitätstyps.  
  
 Eine Fremdschlüsseleigenschaft entspricht einer Fremdschlüsselspalte in einer relationalen Datenbank. Auf die gleiche Weise, dass Fremdschlüsselspalten in einer relationalen Datenbank verwendet werden, um Beziehungen zwischen Zeilen in Tabellen zu erstellen, dienen Fremdschlüsseleigenschaften in einem konzeptionellen Modell herstellen [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md) zwischen Entitätstypen. Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) dient zum Definieren einer Beziehung zwischen zwei Entitätstypen, wenn einer der Typen eine Fremdschlüsseleigenschaft verfügt.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL verwendet die Fremdschlüsseleigenschaft `PublisherId`, um eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung zu definieren, die im konzeptionellen Modell oben gezeigt wurde.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte von Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
