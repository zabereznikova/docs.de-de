---
title: Zuordnungssatzende
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 20810eddda98403d244f6104807504489dde71cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="association-set-end"></a>Zuordnungssatzende
Ein *zuordnungssatzende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und die [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) am Ende einer [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md). Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.  
  
 Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:  
  
-   Einen der Entitätstypen des Zuordnungssatzes. (erforderlich)  
  
-   Die Entitätenmenge für den Entitätstyp im Zuordnungssatz. (erforderlich)  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells. Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`. BI in der `Books` Entitätenmenge stellt eine Instanz der dem `Book` Entitätstyp zur Laufzeit. Auf ähnliche Weise Pj stellt eine `Publisher` -Instanz in der `Publishers` Entitätenmenge. BiPj stellt eine Instanz der dem `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.  
  
 ![Beispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung. Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte von Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
