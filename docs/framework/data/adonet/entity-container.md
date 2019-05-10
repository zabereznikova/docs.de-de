---
title: Entitätscontainer
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 58642c6cc794f931387ac7a76dd64d368957f14b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586960"
---
# <a name="entity-container"></a><span data-ttu-id="ca02a-102">Entitätscontainer</span><span class="sxs-lookup"><span data-stu-id="ca02a-102">entity container</span></span>
<span data-ttu-id="ca02a-103">Ein *Entitätscontainer* ist eine logische Gruppierung von [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md), [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md), und [funktionieren-Importe](../../../../docs/framework/data/adonet/model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="ca02a-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="ca02a-104">Die folgenden Voraussetzungen müssen für einen in einem konzeptionellen Modell definierten Entitätscontainer erfüllt werden:</span><span class="sxs-lookup"><span data-stu-id="ca02a-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="ca02a-105">Mindestens ein Entitätscontainer muss in jedem konzeptionellen Modell definiert sein.</span><span class="sxs-lookup"><span data-stu-id="ca02a-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="ca02a-106">Der Entitätscontainer muss einen eindeutigen Namen innerhalb jedes konzeptionellen Modells aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ca02a-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="ca02a-107">Ein Entitätscontainer kann Entitätenmengen oder Zuordnungssätze definieren, die in einem oder mehreren Namespaces definierte Entitätstypen oder Zuordnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca02a-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="ca02a-108">Weitere Informationen finden Sie unter [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="ca02a-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca02a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca02a-109">Example</span></span>  
 <span data-ttu-id="ca02a-110">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="ca02a-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="ca02a-111">Weitere Informationen finden Sie im nächsten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ca02a-111">See the next example for more information.</span></span>  
  
 ![Beispielmodell mit drei Entitätstypen](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="ca02a-113">Obwohl die Abbildung keine Entitätscontainerinformationen bereitstellt, muss das konzeptionelle Modell einen Entitätscontainer definieren.</span><span class="sxs-lookup"><span data-stu-id="ca02a-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="ca02a-114">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ca02a-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="ca02a-115">Die folgende CSDL definiert einen Entitätscontainer für das in der Abbildung oben gezeigte konzeptionelle Modell.</span><span class="sxs-lookup"><span data-stu-id="ca02a-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="ca02a-116">Beachten Sie, dass der Name des Entitätscontainers in einem XML-Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ca02a-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="ca02a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca02a-117">See also</span></span>

- [<span data-ttu-id="ca02a-118">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ca02a-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="ca02a-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ca02a-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
