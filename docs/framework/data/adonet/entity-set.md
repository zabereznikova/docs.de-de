---
title: "Entitätenmenge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6b28be2b3bdddd9457874881e930ea978ef5c2b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="entity-set"></a><span data-ttu-id="3ae9d-102">Entitätenmenge</span><span class="sxs-lookup"><span data-stu-id="3ae9d-102">entity set</span></span>
<span data-ttu-id="3ae9d-103">Ein *Entitätenmenge* ist ein logischer Container für Instanzen von einem [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) und Instanzen eines beliebigen Typs abgeleitet aus diesem Entitätstyp.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-103">An *entity set* is a logical container for instances of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="3ae9d-104">(Informationen über abgeleitete Typen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) Die Beziehung zwischen einem Entitätstyp und einer Entitätenmenge entspricht der Beziehung zwischen einer Zeile und einer Tabelle in einer relationalen Datenbank: Wie eine Zeile beschreibt ein Entitätstyp Datenstruktur, und eine Entitätenmenge enthält wie eine Tabelle Instanzen einer bestimmten Struktur.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-104">(For information about derived types, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="3ae9d-105">Eine Entitätenmenge ist keine Datenmodellkonstruktion, sie beschreibt keine Datenstruktur.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="3ae9d-106">Vielmehr stellt eine Entitätenmenge eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Entitätstypinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="3ae9d-107">Eine Entitätenmenge wird definiert, in eine [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md), dies ist eine logische Gruppierung von Entitätenmengen und [Zuordnungssätze](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="3ae9d-107">An entity set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of entity sets and [association sets](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="3ae9d-108">Die folgenden Voraussetzungen müssen erfüllt sein, damit eine Entitätstypinstanz in einer Entitätenmenge existiert:</span><span class="sxs-lookup"><span data-stu-id="3ae9d-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
-   <span data-ttu-id="3ae9d-109">Der Typ der Instanz stimmt entweder mit dem Entitätstyp überein, auf dem die Entitätenmenge basiert, oder der Typ der Instanz ist ein Untertyp des Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
-   <span data-ttu-id="3ae9d-110">Die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) für die Instanz innerhalb der Entitätenmenge eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-110">The [entity key](../../../../docs/framework/data/adonet/entity-key.md) for the instance is unique within the entity set.</span></span>  
  
-   <span data-ttu-id="3ae9d-111">Die Instanz ist in keiner anderen Entitätenmenge vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3ae9d-112">Mehrere Entitätenmengen können mit dem gleichen Entitätstyp definiert werden, aber eine Instanz eines bestimmten Entitätstyps kann nur in einer Entitätenmenge vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="3ae9d-113">Sie müssen nicht für jeden Entitätstyp in einem konzeptionellen Modell eine Entitätenmenge definieren.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae9d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ae9d-114">Example</span></span>  
 <span data-ttu-id="3ae9d-115">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="3ae9d-116">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="3ae9d-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="3ae9d-117">Die folgende Abbildung zeigt zwei Entitätenmengen (`Books` und `Publishers`) und einen Zuordnungssatz (`PublishedBy`) auf Grundlage des oben gezeigten konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="3ae9d-118">BI in der `Books` Entitätenmenge stellt eine Instanz der dem `Book` Entitätstyp zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="3ae9d-119">Auf ähnliche Weise Pj darstellen einer `Publisher` Instanz die `Publishers` Entitätenmenge.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="3ae9d-120">BiPj stellt eine Instanz der dem `PublishedBy` Zuordnung in der `PublishedBy` Zuordnungssatz.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="3ae9d-121">![Beispiel](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="3ae9d-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="3ae9d-122">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="3ae9d-123">Die folgende CSDL definiert einen Entitätscontainer mit einer Entitätenmenge für jeden Entitätstyp im oben gezeigten konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="3ae9d-124">Beachten Sie, dass der Name und der Entitätstyp für jede Entitätenmenge mit XML-Attributen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="3ae9d-125">Pro Typ (MEST) können mehrere Entitätssätze definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ae9d-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="3ae9d-126">Die folgende CSDL definiert einen Entitätscontainer mit zwei Entitätenmengen für den `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="3ae9d-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="3ae9d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ae9d-127">See Also</span></span>  
 [<span data-ttu-id="3ae9d-128">Schlüsselkonzepte von Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3ae9d-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="3ae9d-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3ae9d-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
