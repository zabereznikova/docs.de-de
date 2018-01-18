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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5349889017ea23701a17a92947d9750610a52f59
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="association-type"></a><span data-ttu-id="d70b7-102">Zuordnungstyp</span><span class="sxs-lookup"><span data-stu-id="d70b7-102">association type</span></span>
<span data-ttu-id="d70b7-103">Ein *Zuordnungstyp* (auch als Zuordnung bezeichnet) ist der wesentliche Baustein zum Beschreiben von Beziehungen im Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="d70b7-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="d70b7-104">In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) (z. B. `Customer` und `Order`).</span><span class="sxs-lookup"><span data-stu-id="d70b7-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="d70b7-105">In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar (z. B. eine Zuordnung zwischen einer Instanz von `Customer` und einer Instanz von `Order`).</span><span class="sxs-lookup"><span data-stu-id="d70b7-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="d70b7-106">Zuordnungsinstanzen werden logisch gruppiert eine [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="d70b7-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="d70b7-107">Eine Zuordnungsdefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="d70b7-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="d70b7-108">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="d70b7-108">A unique name.</span></span> <span data-ttu-id="d70b7-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="d70b7-109">(Required)</span></span>  
  
-   <span data-ttu-id="d70b7-110">Zwei [Zuordnungsenden](../../../../docs/framework/data/adonet/association-end.md), eine für jeden Entitätstyp in der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="d70b7-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="d70b7-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="d70b7-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d70b7-112">Eine Zuordnung kann keine Beziehung zwischen mehr als zwei Entitätstypen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d70b7-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="d70b7-113">Eine Zuordnung kann jedoch eine Selbstbeziehung definieren, indem der gleichen Entitätstyp für beide Zuordnungsenden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d70b7-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="d70b7-114">Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="d70b7-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="d70b7-115">(Optional)</span><span class="sxs-lookup"><span data-stu-id="d70b7-115">(Optional)</span></span>  
  
 <span data-ttu-id="d70b7-116">Geben Sie jedes Zuordnungsende muss eine [zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , der die Anzahl möglicher Entitätstypinstanzen, die an einem Ende der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="d70b7-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="d70b7-117">Die Multiplizität eines Zuordnungsendes kann über einen Wert von eins (1), null oder eins (0..1) oder n (\*) verfügen.</span><span class="sxs-lookup"><span data-stu-id="d70b7-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span> <span data-ttu-id="d70b7-118">Entitätstypinstanzen an einem Ende einer Zuordnung durch zugegriffen werden können [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) oder den Fremdschlüsseln, wenn sie für einen Entitätstyp verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d70b7-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="d70b7-119">Weitere Informationen finden Sie unter [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="d70b7-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d70b7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d70b7-120">Example</span></span>  
 <span data-ttu-id="d70b7-121">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="d70b7-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="d70b7-122">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="d70b7-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="d70b7-123">Die Multiplizität des `Publisher`-Endes ist eins (1), und die Multiplizität des `Book`-Endes ist n (\*), wodurch angegeben wird, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="d70b7-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="d70b7-124">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="d70b7-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="d70b7-125">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d70b7-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d70b7-126">Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:</span><span class="sxs-lookup"><span data-stu-id="d70b7-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d70b7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d70b7-127">See Also</span></span>  
 [<span data-ttu-id="d70b7-128">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d70b7-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="d70b7-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d70b7-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
