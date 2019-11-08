---
title: Zuordnungssatzende
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: f7ec1ca6fcdf299b9fcfc78f299ea4c6c5267cd3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738616"
---
# <a name="association-set-end"></a><span data-ttu-id="79e6b-102">Zuordnungssatzende</span><span class="sxs-lookup"><span data-stu-id="79e6b-102">association set end</span></span>
<span data-ttu-id="79e6b-103">Ein Zuordnungs *Satz Ende* identifiziert den [Entitätstyp](entity-type.md) und die [Entitätenmenge](entity-set.md) am Ende eines Zuordnungs [Satzes](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="79e6b-103">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="79e6b-104">Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="79e6b-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="79e6b-105">Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="79e6b-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="79e6b-106">Einen der Entitätstypen des Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="79e6b-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="79e6b-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="79e6b-107">(Required)</span></span>  
  
- <span data-ttu-id="79e6b-108">Die Entitätenmenge für den Entitätstyp im Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="79e6b-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="79e6b-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="79e6b-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e6b-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79e6b-110">Example</span></span>  
 <span data-ttu-id="79e6b-111">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="79e6b-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="79e6b-113">Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="79e6b-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="79e6b-114">Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="79e6b-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="79e6b-115">BI in der `Books` Entitätenmenge stellt eine Instanz des `Book` Entitäts Typs zur Laufzeit dar.</span><span class="sxs-lookup"><span data-stu-id="79e6b-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="79e6b-116">Ebenso stellt PJ eine `Publisher` Instanz in der `Publishers` Entitätenmenge dar.</span><span class="sxs-lookup"><span data-stu-id="79e6b-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="79e6b-117">Bipj stellt eine Instanz der `PublishedBy` Zuordnung im `PublishedBy` Zuordnungs Satz dar.</span><span class="sxs-lookup"><span data-stu-id="79e6b-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="79e6b-119">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine DSL namens konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="79e6b-119">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="79e6b-120">Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.</span><span class="sxs-lookup"><span data-stu-id="79e6b-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="79e6b-121">Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.</span><span class="sxs-lookup"><span data-stu-id="79e6b-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="79e6b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e6b-122">See also</span></span>

- [<span data-ttu-id="79e6b-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="79e6b-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="79e6b-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="79e6b-124">Entity Data Model</span></span>](entity-data-model.md)
