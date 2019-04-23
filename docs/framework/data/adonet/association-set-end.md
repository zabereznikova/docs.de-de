---
title: Zuordnungssatzende
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134627"
---
# <a name="association-set-end"></a>Zuordnungssatzende
Ein *zuordnungssatzende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) am Ende einer [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md). Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.  
  
 Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:  
  
-   Einen der Entitätstypen des Zuordnungssatzes. (erforderlich)  
  
-   Die Entitätenmenge für den Entitätstyp im Zuordnungssatz. (erforderlich)  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.  
  
 ![Beispielmodell mit drei Entitätstypen](./media/association-set-end/example-model-three-entity-types.gif)  
  
 Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells. Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`. BI in der `Books` Entitätenmenge stellt eine Instanz von der `Book` Entitätstyp zur Laufzeit. Ebenso Pj repräsentiert eine `Publisher` -Instanz der `Publishers` Entitätenmenge. BiPj stellt eine Instanz von der `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.  
  
 ![Screenshot, ein Beispiel für Gruppen zeigt.](./media/association-set-end/sets-example-association.gif)  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung. Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
