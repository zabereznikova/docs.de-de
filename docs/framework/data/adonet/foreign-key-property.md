---
title: Fremdschlüsseleigenschaft
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: e2f41c2db9aea26c7954a99ebf3f40b03e8df735
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795030"
---
# <a name="foreign-key-property"></a>Fremdschlüsseleigenschaft
Eine *Fremdschlüssel Eigenschaft* im Entity Data Model (EDM) ist eine primitive [Typeigenschaft](property.md) (oder ein Satz primitiver Typeigenschaften) für einen [Entitätstyp](entity-type.md) , der den [Entitäts Schlüssel](entity-key.md) eines anderen Entitäts Typs enthält.  
  
 Eine Fremdschlüsseleigenschaft entspricht einer Fremdschlüsselspalte in einer relationalen Datenbank. Auf dieselbe Weise, wie Fremdschlüssel Spalten in einer relationalen Datenbank verwendet werden, um Beziehungen zwischen Zeilen in Tabellen zu erstellen, werden Fremdschlüssel Eigenschaften in einem konzeptionellen Modell verwendet, um [Zuordnungen](association-type.md) zwischen Entitäts Typen herzustellen. Eine [Einschränkung der referenziellen Integrität](referential-integrity-constraint.md) wird verwendet, um eine Zuordnung zwischen zwei Entitäts Typen zu definieren, wenn einer der Typen über eine Fremdschlüssel Eigenschaft verfügt.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.  
  
 ![Ref-Einschränkung](./media/foreign-key-property/reference-constraint-model.gif "Beispiel eines referenziellen") Einschränkungs Modells  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die folgende CSDL verwendet die Fremdschlüsseleigenschaft `PublisherId`, um eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung zu definieren, die im konzeptionellen Modell oben gezeigt wurde.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
