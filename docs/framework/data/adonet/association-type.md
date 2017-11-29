---
title: Zuordnungstyp
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 476a92979ff0dc6292e64ce5514cc600a9dee50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="association-type"></a><span data-ttu-id="fddb3-102">Zuordnungstyp</span><span class="sxs-lookup"><span data-stu-id="fddb3-102">association type</span></span>
<span data-ttu-id="fddb3-103">Ein *Zuordnungstyp* (auch als Zuordnung bezeichnet) ist der wesentliche Baustein zum Beschreiben von Beziehungen im Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="fddb3-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="fddb3-104">In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) (z. B. `Customer` und `Order`).</span><span class="sxs-lookup"><span data-stu-id="fddb3-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="fddb3-105">In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar (z. B. eine Zuordnung zwischen einer Instanz von `Customer` und einer Instanz von `Order`).</span><span class="sxs-lookup"><span data-stu-id="fddb3-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="fddb3-106">Zuordnungsinstanzen werden logisch gruppiert eine [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="fddb3-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="fddb3-107">Eine Zuordnungsdefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="fddb3-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="fddb3-108">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="fddb3-108">A unique name.</span></span> <span data-ttu-id="fddb3-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="fddb3-109">(Required)</span></span>  
  
-   <span data-ttu-id="fddb3-110">Zwei [Zuordnungsenden](../../../../docs/framework/data/adonet/association-end.md), eine für jeden Entitätstyp in der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="fddb3-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="fddb3-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="fddb3-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fddb3-112">Eine Zuordnung kann keine Beziehung zwischen mehr als zwei Entitätstypen darstellen.</span><span class="sxs-lookup"><span data-stu-id="fddb3-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="fddb3-113">Eine Zuordnung kann jedoch eine Selbstbeziehung definieren, indem der gleichen Entitätstyp für beide Zuordnungsenden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fddb3-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="fddb3-114">Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="fddb3-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="fddb3-115">(Optional)</span><span class="sxs-lookup"><span data-stu-id="fddb3-115">(Optional)</span></span>  
  
 <span data-ttu-id="fddb3-116">Geben Sie jedes Zuordnungsende muss eine [zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , der die Anzahl möglicher Entitätstypinstanzen, die an einem Ende der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="fddb3-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="fddb3-117">Die Multiplizität eines Zuordnungsendes kann über einen Wert von eins (1), null oder eins (0..1) oder n (*) verfügen.</span><span class="sxs-lookup"><span data-stu-id="fddb3-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span> <span data-ttu-id="fddb3-118">Entitätstypinstanzen an einem Ende einer Zuordnung durch zugegriffen werden können [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) oder den Fremdschlüsseln, wenn sie für einen Entitätstyp verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="fddb3-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="fddb3-119">Weitere Informationen finden Sie unter [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="fddb3-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fddb3-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fddb3-120">Example</span></span>  
 <span data-ttu-id="fddb3-121">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="fddb3-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="fddb3-122">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="fddb3-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="fddb3-123">Die Multiplizität des `Publisher`-Endes ist eins (1), und die Multiplizität des `Book`-Endes ist n (*), wodurch angegeben wird, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="fddb3-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="fddb3-124">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="fddb3-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="fddb3-125">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="fddb3-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="fddb3-126">Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:</span><span class="sxs-lookup"><span data-stu-id="fddb3-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="fddb3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fddb3-127">See Also</span></span>  
 [<span data-ttu-id="fddb3-128">Schlüsselkonzepte von Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fddb3-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="fddb3-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fddb3-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
