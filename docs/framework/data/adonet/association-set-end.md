---
title: Zuordnungssatzende
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134627"
---
# <a name="association-set-end"></a><span data-ttu-id="52639-102">Zuordnungssatzende</span><span class="sxs-lookup"><span data-stu-id="52639-102">association set end</span></span>
<span data-ttu-id="52639-103">Ein *zuordnungssatzende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) am Ende einer [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="52639-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="52639-104">Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="52639-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="52639-105">Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="52639-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="52639-106">Einen der Entitätstypen des Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="52639-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="52639-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="52639-107">(Required)</span></span>  
  
-   <span data-ttu-id="52639-108">Die Entitätenmenge für den Entitätstyp im Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="52639-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="52639-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="52639-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="52639-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52639-110">Example</span></span>  
 <span data-ttu-id="52639-111">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="52639-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Beispielmodell mit drei Entitätstypen](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="52639-113">Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="52639-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="52639-114">Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="52639-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="52639-115">BI in der `Books` Entitätenmenge stellt eine Instanz von der `Book` Entitätstyp zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="52639-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="52639-116">Ebenso Pj repräsentiert eine `Publisher` -Instanz der `Publishers` Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="52639-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="52639-117">BiPj stellt eine Instanz von der `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="52639-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot, ein Beispiel für Gruppen zeigt.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="52639-119">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="52639-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="52639-120">Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.</span><span class="sxs-lookup"><span data-stu-id="52639-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="52639-121">Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.</span><span class="sxs-lookup"><span data-stu-id="52639-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="52639-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52639-122">See also</span></span>

- [<span data-ttu-id="52639-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="52639-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="52639-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="52639-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
