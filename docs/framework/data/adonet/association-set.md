---
title: Zuordnungssatz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db293cbc636d0ae4e532f24b2852444395f603c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="association-set"></a><span data-ttu-id="ece78-102">Zuordnungssatz</span><span class="sxs-lookup"><span data-stu-id="ece78-102">association set</span></span>
<span data-ttu-id="ece78-103">Ein *Zuordnungssatz* ist ein logischer Container für [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) Instanzen des gleichen Typs.</span><span class="sxs-lookup"><span data-stu-id="ece78-103">An *association set* is a logical container for [association](../../../../docs/framework/data/adonet/association-type.md) instances of the same type.</span></span> <span data-ttu-id="ece78-104">Ein Zuordnungssatz ist keine Datenmodellkonstruktion; das heißt, er beschreibt nicht die Struktur von Daten oder Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="ece78-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="ece78-105">Vielmehr stellt ein Zuordnungssatz eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Zuordnungsinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="ece78-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="ece78-106">Ein Zuordnungssatz wird innerhalb von definiert ein [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md), dies ist eine logische Gruppierung von [Entitätenmengen](../../../../docs/framework/data/adonet/entity-set.md) und Zuordnungssätzen.</span><span class="sxs-lookup"><span data-stu-id="ece78-106">An association set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="ece78-107">Eine Definition für einen Zuordnungssatz enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="ece78-107">A definition for an association set contains the following information:</span></span>  
  
-   <span data-ttu-id="ece78-108">Den Namen des Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="ece78-108">The association set name.</span></span> <span data-ttu-id="ece78-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="ece78-109">(Required)</span></span>  
  
-   <span data-ttu-id="ece78-110">Die Zuordnung, von der er Instanzen enthält.</span><span class="sxs-lookup"><span data-stu-id="ece78-110">The association of which it will contain instances.</span></span> <span data-ttu-id="ece78-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="ece78-111">(Required)</span></span>  
  
-   <span data-ttu-id="ece78-112">Zwei [zuordnungssatzenden](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="ece78-112">Two [association set ends](../../../../docs/framework/data/adonet/association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ece78-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ece78-113">Example</span></span>  
 <span data-ttu-id="ece78-114">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="ece78-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="ece78-115">Obwohl die Abbildung keine Informationen zu Zuordnungssätzen bereitstellt, zeigt die nächste Abbildung ein Beispiel für Zuordnungssätze und Entitätenmengen auf Grundlage dieses Modells.</span><span class="sxs-lookup"><span data-stu-id="ece78-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 <span data-ttu-id="ece78-116">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="ece78-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="ece78-117">Das folgende Beispiel zeigt einen Zuordnungssatz (`PublishedBy`) und zwei Entitätenmengen (`Books` und `Publishers`), basierend auf dem oben gezeigten Modell.</span><span class="sxs-lookup"><span data-stu-id="ece78-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="ece78-118">BI in der `Books` Entitätenmenge stellt eine Instanz der dem `Book` Entitätstyp zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="ece78-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="ece78-119">Auf ähnliche Weise Pj stellt eine `Publisher` -Instanz in der `Publishers` Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="ece78-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="ece78-120">BiPj stellt eine Instanz der dem `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="ece78-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="ece78-121">![Beispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="ece78-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="ece78-122">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ece78-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="ece78-123">Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.</span><span class="sxs-lookup"><span data-stu-id="ece78-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="ece78-124">Beachten Sie, dass der Name und die Zuordnung für jeden Zuordnungssatz mit XML-Attributen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ece78-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="ece78-125">Es ist möglich, mehrere Zuordnungssätze pro Zuordnung, solange keine Teilen zwei Zuordnungssätze definieren eine [zuordnungssatzende](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="ece78-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](../../../../docs/framework/data/adonet/association-set-end.md).</span></span> <span data-ttu-id="ece78-126">Die folgende CSDL definiert einen Entitätscontainer mit zwei Zuordnungssätzen für die `WrittenBy`-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ece78-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="ece78-127">Beachten Sie, dass mehrere Entitätssätze für die Entitätstypen `Book` und `Author` definiert wurden, und dass sich kein Zuordnungssatz ein Zuordnungssatzende teilt.</span><span class="sxs-lookup"><span data-stu-id="ece78-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="ece78-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ece78-128">See Also</span></span>  
 [<span data-ttu-id="ece78-129">Schlüsselkonzepte von Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ece78-129">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="ece78-130">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ece78-130">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="ece78-131">Fremdschlüsseleigenschaft</span><span class="sxs-lookup"><span data-stu-id="ece78-131">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)
