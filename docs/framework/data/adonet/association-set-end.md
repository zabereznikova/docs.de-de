---
title: Zuordnungssatzende
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: bd104ffb46cbd02a886ce87822ddc37159961174
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198794"
---
# <a name="association-set-end"></a>Zuordnungssatzende

Ein Zuordnungs *Satz Ende* identifiziert den [Entitätstyp](entity-type.md) und die [Entitätenmenge](entity-set.md) am Ende eines Zuordnungs [Satzes](association-set.md). Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.  
  
 Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:  
  
- Einen der Entitätstypen des Zuordnungssatzes. (Erforderlich)  
  
- Die Entitätenmenge für den Entitätstyp im Zuordnungssatz. (Erforderlich)  
  
## <a name="example"></a>Beispiel  

 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-set-end/example-model-three-entity-types.gif)  
  
 Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells. Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`. BI in der `Books` Entitätenmenge stellt zur Laufzeit eine Instanz des `Book` Entitäts Typs dar. Ebenso stellt PJ eine- `Publisher` Instanz in der `Publishers` Entitätenmenge dar. Bipj stellt eine Instanz der Zuordnung `PublishedBy` im Zuordnungs `PublishedBy` Satz dar.  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/association-set-end/sets-example-association.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine DSL namens konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung. Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
