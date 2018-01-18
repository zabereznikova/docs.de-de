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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 85b4bd732d9de987676bae70f7749a1dd9dc76c5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="association-set-end"></a><span data-ttu-id="01c22-102">Zuordnungssatzende</span><span class="sxs-lookup"><span data-stu-id="01c22-102">association set end</span></span>
<span data-ttu-id="01c22-103">Ein *zuordnungssatzende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und die [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) am Ende einer [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="01c22-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="01c22-104">Zuordnungssatzenden werden als Teil eines Zuordnungssatzes definiert. Ein Zuordnungssatz muss genau zwei Zuordnungssatzenden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="01c22-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="01c22-105">Die Definition eines Zuordnungssatzendes enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="01c22-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="01c22-106">Einen der Entitätstypen des Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="01c22-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="01c22-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="01c22-107">(Required)</span></span>  
  
-   <span data-ttu-id="01c22-108">Die Entitätenmenge für den Entitätstyp im Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="01c22-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="01c22-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="01c22-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="01c22-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01c22-110">Example</span></span>  
 <span data-ttu-id="01c22-111">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="01c22-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="01c22-112">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="01c22-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="01c22-113">Die folgende Abbildung zeigt einen Zuordnungssatz (`PublishedBy`) sowie zwei Entitätenmengen (`Books` und `Publishers`) auf Grundlage des oben gezeigten konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="01c22-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="01c22-114">Die Zuordnungssatzenden sind die Entitätenmengen `Books` und `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="01c22-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="01c22-115">BI in der `Books` Entitätenmenge stellt eine Instanz der dem `Book` Entitätstyp zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="01c22-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="01c22-116">Auf ähnliche Weise Pj stellt eine `Publisher` -Instanz in der `Publishers` Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="01c22-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="01c22-117">BiPj stellt eine Instanz der dem `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="01c22-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="01c22-118">![Beispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="01c22-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="01c22-119">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine DSL mit der Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="01c22-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="01c22-120">Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.</span><span class="sxs-lookup"><span data-stu-id="01c22-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="01c22-121">Beachten Sie, dass Zuordnungssatzenden als Teil jeder Zuordnungssatzdefinition definiert werden.</span><span class="sxs-lookup"><span data-stu-id="01c22-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="01c22-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01c22-122">See Also</span></span>  
 [<span data-ttu-id="01c22-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="01c22-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="01c22-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="01c22-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
