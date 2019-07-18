---
title: Fremdschlüsseleigenschaft
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879078"
---
# <a name="foreign-key-property"></a>Fremdschlüsseleigenschaft
Ein *Fremdschlüsseleigenschaft* im Entity Data Model (EDM) ist ein primitiver Typ [Eigenschaft](../../../../docs/framework/data/adonet/property.md) (oder einen Satz von primitiven Typeigenschaften) auf eine [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) , enthält die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) eines anderen Entitätstyps.  
  
 Eine Fremdschlüsseleigenschaft entspricht einer Fremdschlüsselspalte in einer relationalen Datenbank. Auf die gleiche Weise, dass foreign Key-Spalten in einer relationalen Datenbank verwendet werden, um Beziehungen zwischen Zeilen in Tabellen zu erstellen, werden Fremdschlüsseleigenschaften in einem konzeptionellen Modell herstellen verwendet [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md) zwischen Entitätstypen. Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) dient zum Definieren einer Beziehung zwischen zwei Entitätstypen, wenn einer der Typen eine Fremdschlüsseleigenschaft verfügt.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Beispiel für eine referenzielle Einschränkung-Modell")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL verwendet die Fremdschlüsseleigenschaft `PublisherId`, um eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung zu definieren, die im konzeptionellen Modell oben gezeigt wurde.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
