---
title: Entitätscontainer
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95fb59c86f951e75f0988f45219fd07cbb003c01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200822"
---
# <a name="entity-container"></a>Entitätscontainer

Ein *Entitätencontainer* ist eine logische Gruppierung von [Entitätenmengen](entity-set.md), Zuordnungs [Sätzen](association-set.md)und [Funktions Importen](model-declared-function.md).  
  
 Die folgenden Voraussetzungen müssen für einen in einem konzeptionellen Modell definierten Entitätscontainer erfüllt werden:  
  
- Mindestens ein Entitätscontainer muss in jedem konzeptionellen Modell definiert sein.  
  
- Der Entitätscontainer muss einen eindeutigen Namen innerhalb jedes konzeptionellen Modells aufweisen.  
  
 Ein Entitätscontainer kann Entitätenmengen oder Zuordnungssätze definieren, die in einem oder mehreren Namespaces definierte Entitätstypen oder Zuordnungen verwenden. Weitere Informationen finden Sie unter [Entity Data Model: Namespaces](entity-data-model-namespaces.md).  
  
## <a name="example"></a>Beispiel  

 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.  Weitere Informationen finden Sie im nächsten Beispiel.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-container/example-model-three-entity-types.gif)  
  
 Obwohl die Abbildung keine Entitätscontainerinformationen bereitstellt, muss das konzeptionelle Modell einen Entitätscontainer definieren. Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine DSL namens konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer für das in der Abbildung oben gezeigte konzeptionelle Modell. Beachten Sie, dass der Name des Entitätscontainers in einem XML-Attribut definiert wird.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
