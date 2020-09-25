---
title: property
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 6aeb29c5aa608987466ec858416a4ac141ff1da3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180919"
---
# <a name="property"></a><span data-ttu-id="190cf-102">property</span><span class="sxs-lookup"><span data-stu-id="190cf-102">property</span></span>

<span data-ttu-id="190cf-103">*Eigenschaften* sind die grundlegenden Bausteine von [Entitäts Typen](entity-type.md) und [komplexen Typen](complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="190cf-103">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="190cf-104">Eigenschaften definieren die Form und die Eigenschaften der Daten, die eine Entitätstypinstanz oder komplexe Typinstanz enthält.</span><span class="sxs-lookup"><span data-stu-id="190cf-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="190cf-105">Eigenschaften in einem konzeptionellen Modell sind analog zu den für eine Klasse definierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="190cf-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="190cf-106">So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.</span><span class="sxs-lookup"><span data-stu-id="190cf-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="190cf-107">Eigenschaften, wie in diesem Thema beschrieben, unterscheiden sich von Navigationseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="190cf-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="190cf-108">Weitere Informationen finden Sie unter [Navigations Eigenschaften](navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="190cf-108">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="190cf-109">Eine Eigenschaftendefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="190cf-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="190cf-110">Ein Eigenschaftsname.</span><span class="sxs-lookup"><span data-stu-id="190cf-110">A property name.</span></span> <span data-ttu-id="190cf-111">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="190cf-111">(Required)</span></span>  
  
- <span data-ttu-id="190cf-112">Einen Eigenschaftentyp.</span><span class="sxs-lookup"><span data-stu-id="190cf-112">A property type.</span></span> <span data-ttu-id="190cf-113">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="190cf-113">(Required)</span></span>  
  
- <span data-ttu-id="190cf-114">Ein Satz von [Facetten](facet.md).</span><span class="sxs-lookup"><span data-stu-id="190cf-114">A set of [facets](facet.md).</span></span> <span data-ttu-id="190cf-115">(Optional)</span><span class="sxs-lookup"><span data-stu-id="190cf-115">(Optional)</span></span>  
  
 <span data-ttu-id="190cf-116">Eine Eigenschaft kann primitive Daten (z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert) oder strukturierte Daten (z. B. einen komplexen Typ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="190cf-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="190cf-117">Eigenschaften primitiven Typs werden auch als skalare Eigenschaften bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="190cf-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="190cf-118">Weitere Informationen finden Sie unter [Entity Data Model: primitive Datentypen](entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="190cf-118">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="190cf-119">Ein komplexer Typ selbst kann über Eigenschaften, die komplexe Typen sind, verfügen.</span><span class="sxs-lookup"><span data-stu-id="190cf-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="190cf-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="190cf-120">Example</span></span>  

 <span data-ttu-id="190cf-121">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="190cf-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="190cf-122">Jeder Entitätstyp verfügt über mehrere Eigenschaften, obwohl keine Typinformationen für jede Eigenschaft in der Abbildung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="190cf-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="190cf-123">Eigenschaften, bei denen es sich um [Entitäts Schlüssel](entity-key.md) handelt, werden mit (Key) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="190cf-123">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="190cf-125">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="190cf-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="190cf-126">Die folgende CSDL definiert den `Book`-Entitätstyp (wie oben in der Abbildung gezeigt) und gibt Typ und Namen jeder Eigenschaft mit XML-Attributen an.</span><span class="sxs-lookup"><span data-stu-id="190cf-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="190cf-127">Ein optionales Facet, `Nullable`, wird auch mit einem XML-Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="190cf-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="190cf-128">Es ist möglich, dass eine der in der Abbildung gezeigten Eigenschaften eine komplexe Typeigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="190cf-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="190cf-129">Die `Address`-Eigenschaft für den `Publisher`-Entitätstyp könnte z. B. eine aus mehreren skalaren Eigenschaften bestehende komplexe Typeigenschaft sein, wie `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="190cf-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="190cf-130">Die CSDL-Darstellung eines entsprechenden komplexen Typs würde wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="190cf-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="190cf-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="190cf-131">See also</span></span>

- [<span data-ttu-id="190cf-132">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="190cf-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="190cf-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="190cf-133">Entity Data Model</span></span>](entity-data-model.md)
