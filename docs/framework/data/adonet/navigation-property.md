---
title: Navigationseigenschaft
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: eaf22ad4dd24b4bf046f14ccabd435a9ecd1776f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094383"
---
# <a name="navigation-property"></a><span data-ttu-id="46e45-102">Navigationseigenschaft</span><span class="sxs-lookup"><span data-stu-id="46e45-102">Navigation property</span></span>

<span data-ttu-id="46e45-103">Eine *Navigations Eigenschaft* ist eine optionale Eigenschaft für einen [Entitätstyp](entity-type.md) , der die Navigation von einem [Ende](association-end.md) einer [Zuordnung zum anderen](association-type.md) Ende ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="46e45-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="46e45-104">Im Gegensatz zu anderen [Eigenschaften](property.md)werden von Navigations Eigenschaften keine Daten übertragen.</span><span class="sxs-lookup"><span data-stu-id="46e45-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="46e45-105">Die Definition einer Navigationseigenschaft enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="46e45-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="46e45-106">Einen Namen</span><span class="sxs-lookup"><span data-stu-id="46e45-106">A name.</span></span> <span data-ttu-id="46e45-107">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="46e45-107">(Required)</span></span>

- <span data-ttu-id="46e45-108">Die Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="46e45-108">The association that it navigates.</span></span> <span data-ttu-id="46e45-109">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="46e45-109">(Required)</span></span>

- <span data-ttu-id="46e45-110">Die Enden der Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="46e45-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="46e45-111">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="46e45-111">(Required)</span></span>

<span data-ttu-id="46e45-112">Navigations Eigenschaften sind bei beiden Entitäts Typen an den Enden einer Zuordnung optional.</span><span class="sxs-lookup"><span data-stu-id="46e45-112">Navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="46e45-113">Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="46e45-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="46e45-114">Der Datentyp einer Navigations Eigenschaft wird von der Multiplizität [des Remote](association-end-multiplicity.md) Zuordnungs [Endes](association-end.md)bestimmt.</span><span class="sxs-lookup"><span data-stu-id="46e45-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="46e45-115">Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`.</span><span class="sxs-lookup"><span data-stu-id="46e45-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="46e45-116">Da das Remote Zuordnungs Ende für die Navigations Eigenschaft eine Multiplizität von vielen (\*) aufweist, ist sein Datentyp eine Auflistung (of `Order`).</span><span class="sxs-lookup"><span data-stu-id="46e45-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="46e45-117">Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.</span><span class="sxs-lookup"><span data-stu-id="46e45-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="46e45-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46e45-118">Example</span></span>

<span data-ttu-id="46e45-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="46e45-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="46e45-120">Die Navigations Eigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="46e45-120">The navigation properties `Publisher` and `Authors` are defined on the Book entity type.</span></span> <span data-ttu-id="46e45-121">Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="46e45-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitäts Typen.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="46e45-123">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="46e45-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="46e45-124">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="46e45-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="46e45-125">XML-Attribute werden verwendet, um die zum Definieren einer Navigations Eigenschaft erforderlichen Informationen zu übermitteln: das Attribut `Name` das den Namen der Eigenschaft enthält, `Relationship` den Namen der Zuordnung enthält, die er navigiert, und `FromRole` und `ToRole` die Enden der Zuordnung enthalten.</span><span class="sxs-lookup"><span data-stu-id="46e45-125">XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="46e45-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46e45-126">See also</span></span>

- [<span data-ttu-id="46e45-127">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="46e45-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="46e45-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="46e45-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="46e45-129">Beziehungen, Navigations Eigenschaften und Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="46e45-129">Relationships, navigation properties, and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
