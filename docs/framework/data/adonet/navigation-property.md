---
title: Navigationseigenschaft
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dc980a2c61be736e2c1d8e52d8f13d0ea5ed09f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="navigation-property"></a><span data-ttu-id="9e189-102">Navigationseigenschaft</span><span class="sxs-lookup"><span data-stu-id="9e189-102">navigation property</span></span>
<span data-ttu-id="9e189-103">Ein *Navigationseigenschaft* ist eine optionale Eigenschaft für ein [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) , mit dessen Hilfe für die Navigation von einem [End](../../../../docs/framework/data/adonet/association-end.md) des ein [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) an das andere Ende.</span><span class="sxs-lookup"><span data-stu-id="9e189-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="9e189-104">Im Gegensatz zu anderen [Eigenschaften](../../../../docs/framework/data/adonet/property.md), keine Navigationseigenschaften Daten.</span><span class="sxs-lookup"><span data-stu-id="9e189-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="9e189-105">Die Definition einer Navigationseigenschaft enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9e189-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="9e189-106">Einen Namen.</span><span class="sxs-lookup"><span data-stu-id="9e189-106">A name.</span></span> <span data-ttu-id="9e189-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="9e189-107">(Required)</span></span>  
  
-   <span data-ttu-id="9e189-108">Die Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="9e189-108">The association that it navigates.</span></span> <span data-ttu-id="9e189-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="9e189-109">(Required)</span></span>  
  
-   <span data-ttu-id="9e189-110">Die Enden der Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="9e189-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="9e189-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="9e189-111">(Required)</span></span>  
  
 <span data-ttu-id="9e189-112">Beachten Sie, dass Navigationseigenschaften für beide Entitätstypen an den Enden einer Zuordnung optional sind.</span><span class="sxs-lookup"><span data-stu-id="9e189-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="9e189-113">Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e189-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="9e189-114">Der Datentyp einer Navigationseigenschaft richtet sich nach der [Multiplizität](../../../../docs/framework/data/adonet/association-end-multiplicity.md) seine Remoteinstanz [Zuordnungsende](../../../../docs/framework/data/adonet/association-end.md).</span><span class="sxs-lookup"><span data-stu-id="9e189-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="9e189-115">Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`.</span><span class="sxs-lookup"><span data-stu-id="9e189-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="9e189-116">Da das Remotezuordnungsende für die Navigationseigenschaft eine Multiplizität von n (*) aufweist, ist sein Datentyp eine Auflistung (von `Order`).</span><span class="sxs-lookup"><span data-stu-id="9e189-116">Because the remote association end for the navigation property has multiplicity of many (*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="9e189-117">Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.</span><span class="sxs-lookup"><span data-stu-id="9e189-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e189-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e189-118">Example</span></span>  
 <span data-ttu-id="9e189-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="9e189-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="9e189-120">Die Navigationseigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="9e189-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="9e189-121">Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="9e189-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="9e189-122">![Modell mit Navigationseigenschaften](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="9e189-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="9e189-123">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9e189-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="9e189-124">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="9e189-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="9e189-125">Beachten Sie, dass XML-Attribute verwendet werden, um die zum Definieren einer Navigationseigenschaft erforderlichen Informationen zu übermitteln: Das Attribut `Name` enthält den Namen der Eigenschaft, `Relationship` enthält den Namen der Zuordnung, in der sie navigiert, und `FromRole` sowie `ToRole` enthalten die Enden der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="9e189-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e189-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e189-126">See Also</span></span>  
 [<span data-ttu-id="9e189-127">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="9e189-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="9e189-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="9e189-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
