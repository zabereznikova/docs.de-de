---
title: property
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 50cd2f2678d304af8b898380645424e0635891d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="property"></a><span data-ttu-id="af9ba-102">property</span><span class="sxs-lookup"><span data-stu-id="af9ba-102">property</span></span>
<span data-ttu-id="af9ba-103">*Eigenschaften* sind die grundlegenden Bausteine von [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) und [komplexe Typen](../../../../docs/framework/data/adonet/complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="af9ba-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="af9ba-104">Eigenschaften definieren die Form und die Eigenschaften der Daten, die eine Entitätstypinstanz oder komplexe Typinstanz enthält.</span><span class="sxs-lookup"><span data-stu-id="af9ba-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="af9ba-105">Eigenschaften in einem konzeptionellen Modell sind analog zu den für eine Klasse definierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="af9ba-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="af9ba-106">So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.</span><span class="sxs-lookup"><span data-stu-id="af9ba-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9ba-107">Eigenschaften, wie in diesem Thema beschrieben, unterscheiden sich von Navigationseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="af9ba-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="af9ba-108">Weitere Informationen finden Sie unter [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="af9ba-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="af9ba-109">Eine Eigenschaftendefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="af9ba-109">A property definition contains the following information:</span></span>  
  
-   <span data-ttu-id="af9ba-110">Einen Eigenschaftennamen.</span><span class="sxs-lookup"><span data-stu-id="af9ba-110">A property name.</span></span> <span data-ttu-id="af9ba-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="af9ba-111">(Required)</span></span>  
  
-   <span data-ttu-id="af9ba-112">Einen Eigenschaftentyp.</span><span class="sxs-lookup"><span data-stu-id="af9ba-112">A property type.</span></span> <span data-ttu-id="af9ba-113">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="af9ba-113">(Required)</span></span>  
  
-   <span data-ttu-id="af9ba-114">Eine Reihe von [Facets](../../../../docs/framework/data/adonet/facet.md).</span><span class="sxs-lookup"><span data-stu-id="af9ba-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="af9ba-115">(Optional)</span><span class="sxs-lookup"><span data-stu-id="af9ba-115">(Optional)</span></span>  
  
 <span data-ttu-id="af9ba-116">Eine Eigenschaft kann primitive Daten (z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert) oder strukturierte Daten (z. B. einen komplexen Typ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="af9ba-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="af9ba-117">Eigenschaften primitiven Typs werden auch als skalare Eigenschaften bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="af9ba-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="af9ba-118">Weitere Informationen finden Sie unter [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="af9ba-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af9ba-119">Ein komplexer Typ selbst kann über Eigenschaften, die komplexe Typen sind, verfügen.</span><span class="sxs-lookup"><span data-stu-id="af9ba-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af9ba-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af9ba-120">Example</span></span>  
 <span data-ttu-id="af9ba-121">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="af9ba-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="af9ba-122">Jeder Entitätstyp verfügt über mehrere Eigenschaften, obwohl keine Typinformationen für jede Eigenschaft in der Abbildung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="af9ba-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="af9ba-123">Eigenschaften, die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) mit (Schlüssel) gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="af9ba-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 <span data-ttu-id="af9ba-124">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="af9ba-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="af9ba-125">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="af9ba-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="af9ba-126">Die folgende CSDL definiert den `Book`-Entitätstyp (wie oben in der Abbildung gezeigt) und gibt Typ und Namen jeder Eigenschaft mit XML-Attributen an.</span><span class="sxs-lookup"><span data-stu-id="af9ba-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="af9ba-127">Ein optionales Facet, `Nullable`, wird auch mit einem XML-Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="af9ba-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="af9ba-128">Es ist möglich, dass eine der in der Abbildung gezeigten Eigenschaften eine komplexe Typeigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="af9ba-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="af9ba-129">Die `Address`-Eigenschaft für den `Publisher`-Entitätstyp könnte z. B. eine aus mehreren skalaren Eigenschaften bestehende komplexe Typeigenschaft sein, wie `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="af9ba-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="af9ba-130">Die CSDL-Darstellung eines entsprechenden komplexen Typs würde wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="af9ba-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="af9ba-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af9ba-131">See Also</span></span>  
 [<span data-ttu-id="af9ba-132">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="af9ba-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="af9ba-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="af9ba-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
