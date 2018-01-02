---
title: Zuordnungsende
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 53e52a09533f3e1ead240ec3284371603c82ce53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="association-end"></a><span data-ttu-id="56f33-102">Zuordnungsende</span><span class="sxs-lookup"><span data-stu-id="56f33-102">association end</span></span>
<span data-ttu-id="56f33-103">Ein *Zuordnungsende* identifiziert die [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) an einem Ende einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) und die Anzahl von Entitätstypinstanzen Instanzen, die vorhanden sind, können an diesem Ende einer Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="56f33-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="56f33-104">Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="56f33-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="56f33-105">[Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) ermöglichen die Navigation von Zuordnungsenden zum anderen.</span><span class="sxs-lookup"><span data-stu-id="56f33-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="56f33-106">Eine Zuordnungsendedefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="56f33-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="56f33-107">Einen der Entitätstypen der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="56f33-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="56f33-108">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="56f33-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56f33-109">Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein.</span><span class="sxs-lookup"><span data-stu-id="56f33-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="56f33-110">Dadurch wird eine Selbstzuordnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="56f33-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="56f33-111">Ein [zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , der die Anzahl möglicher Entitätstypinstanzen, die an einem Ende der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="56f33-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="56f33-112">Die Multiplizität eines Zuordnungsendes kann über einen Wert von eins (1), null oder eins (0..1) oder n (*) verfügen.</span><span class="sxs-lookup"><span data-stu-id="56f33-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span>  
  
-   <span data-ttu-id="56f33-113">Der Name für das Zuordnungsende.</span><span class="sxs-lookup"><span data-stu-id="56f33-113">A name for the association end.</span></span> <span data-ttu-id="56f33-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="56f33-114">(Optional)</span></span>  
  
-   <span data-ttu-id="56f33-115">Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE.</span><span class="sxs-lookup"><span data-stu-id="56f33-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="56f33-116">(Optional)</span><span class="sxs-lookup"><span data-stu-id="56f33-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f33-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56f33-117">Example</span></span>  
 <span data-ttu-id="56f33-118">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="56f33-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="56f33-119">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="56f33-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="56f33-120">Die Multiplizität des `Publisher`-Endes ist eins (1), und die Multiplizität des `Book`-Endes ist n (*), wodurch angegeben wird, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="56f33-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="56f33-121">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="56f33-121">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="56f33-122">Das ADO.NET Entity Framework verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="56f33-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="56f33-123">Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="56f33-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="56f33-124">Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML-Attributen (den Attribute `Type`, `Role` bzw. `Multiplicity`) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="56f33-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="56f33-125">Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML-Element (dem `OnDelete`-Element) angegeben.</span><span class="sxs-lookup"><span data-stu-id="56f33-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="56f33-126">In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.</span><span class="sxs-lookup"><span data-stu-id="56f33-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="56f33-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56f33-127">See Also</span></span>  
 [<span data-ttu-id="56f33-128">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="56f33-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="56f33-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="56f33-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
