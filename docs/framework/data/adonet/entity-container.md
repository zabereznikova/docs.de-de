---
title: Entitätscontainer
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 4a629a800df63c67dc17d3fc1531a9862861e9c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144065"
---
# <a name="entity-container"></a>Entitätscontainer
Ein *Entitätscontainer* ist eine logische Gruppierung von [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md), [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md), und [funktionieren-Importe](../../../../docs/framework/data/adonet/model-declared-function.md).  
  
 Die folgenden Voraussetzungen müssen für einen in einem konzeptionellen Modell definierten Entitätscontainer erfüllt werden:  
  
-   Mindestens ein Entitätscontainer muss in jedem konzeptionellen Modell definiert sein.  
  
-   Der Entitätscontainer muss einen eindeutigen Namen innerhalb jedes konzeptionellen Modells aufweisen.  
  
 Ein Entitätscontainer kann Entitätenmengen oder Zuordnungssätze definieren, die in einem oder mehreren Namespaces definierte Entitätstypen oder Zuordnungen verwenden. Weitere Informationen finden Sie unter [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  Weitere Informationen finden Sie im nächsten Beispiel.  
  
 ![Beispielmodell mit drei Entitätstypen](./media/entity-container/example-model-three-entity-types.gif)  
  
 Obwohl die Abbildung keine Entitätscontainerinformationen bereitstellt, muss das konzeptionelle Modell einen Entitätscontainer definieren. Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer für das in der Abbildung oben gezeigte konzeptionelle Modell. Beachten Sie, dass der Name des Entitätscontainers in einem XML-Attribut definiert wird.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
