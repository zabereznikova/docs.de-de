---
title: Entitätscontainer
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: ed2123629c61b179e07e86effa0c39d9a3222b62
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764040"
---
# <a name="entity-container"></a>Entitätscontainer
Ein *Entitätscontainer* ist eine logische Gruppierung von [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md), [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md), und [Funktion Importe](../../../../docs/framework/data/adonet/model-declared-function.md).  
  
 Die folgenden Voraussetzungen müssen für einen in einem konzeptionellen Modell definierten Entitätscontainer erfüllt werden:  
  
-   Mindestens ein Entitätscontainer muss in jedem konzeptionellen Modell definiert sein.  
  
-   Der Entitätscontainer muss einen eindeutigen Namen innerhalb jedes konzeptionellen Modells aufweisen.  
  
 Ein Entitätscontainer kann Entitätenmengen oder Zuordnungssätze definieren, die in einem oder mehreren Namespaces definierte Entitätstypen oder Zuordnungen verwenden. Weitere Informationen finden Sie unter [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  Weitere Informationen finden Sie im nächsten Beispiel.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Obwohl die Abbildung keine Entitätscontainerinformationen bereitstellt, muss das konzeptionelle Modell einen Entitätscontainer definieren. Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer für das in der Abbildung oben gezeigte konzeptionelle Modell. Beachten Sie, dass der Name des Entitätscontainers in einem XML-Attribut definiert wird.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
