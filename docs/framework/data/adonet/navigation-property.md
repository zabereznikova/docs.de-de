---
title: Navigationseigenschaft – ADO.NET
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b57ecf9329aa9ea8afc07507613c9e3961bfd0a9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836597"
---
# <a name="navigation-property"></a><span data-ttu-id="a1e79-102">Navigationseigenschaft</span><span class="sxs-lookup"><span data-stu-id="a1e79-102">Navigation property</span></span>

<span data-ttu-id="a1e79-103">Ein *Navigationseigenschaft* ist eine optionale Eigenschaft auf eine [Entitätstyp](entity-type.md) ermöglicht, die die Navigation von einer [End](association-end.md) von einer [Zuordnung](association-type.md) auf das andere Ende.</span><span class="sxs-lookup"><span data-stu-id="a1e79-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="a1e79-104">Im Gegensatz zu anderen [Eigenschaften](property.md), Navigationseigenschaften werden keine Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a1e79-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="a1e79-105">Die Definition einer Navigationseigenschaft enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a1e79-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="a1e79-106">Einen Namen.</span><span class="sxs-lookup"><span data-stu-id="a1e79-106">A name.</span></span> <span data-ttu-id="a1e79-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a1e79-107">(Required)</span></span>

- <span data-ttu-id="a1e79-108">Die Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="a1e79-108">The association that it navigates.</span></span> <span data-ttu-id="a1e79-109">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a1e79-109">(Required)</span></span>

- <span data-ttu-id="a1e79-110">Die Enden der Zuordnung, in der sie navigiert.</span><span class="sxs-lookup"><span data-stu-id="a1e79-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="a1e79-111">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="a1e79-111">(Required)</span></span>

<span data-ttu-id="a1e79-112">Beachten Sie, dass Navigationseigenschaften für beide Entitätstypen an den Enden einer Zuordnung optional sind.</span><span class="sxs-lookup"><span data-stu-id="a1e79-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="a1e79-113">Wenn Sie für einen Entitätstyp am Ende einer Zuordnung eine Navigationseigenschaft definieren, muss keine Navigationseigenschaft für den Entitätstyp am anderen Ende der Zuordnung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a1e79-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="a1e79-114">Der Datentyp einer Navigationseigenschaft richtet sich nach der [Multiplizität](association-end-multiplicity.md) von dessen Remote [Zuordnungsende](association-end.md).</span><span class="sxs-lookup"><span data-stu-id="a1e79-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="a1e79-115">Angenommen, eine Navigationseigenschaft, `OrdersNavProp`, ist für einen `Customer`-Entitätstyp vorhanden und navigiert eine 1:n-Zuordnung zwischen `Customer` und `Order`.</span><span class="sxs-lookup"><span data-stu-id="a1e79-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="a1e79-116">Da das remotezuordnungsende für die Navigationseigenschaft eine Multiplizität von vielen aufweist (\*), der Datentyp ist eine Sammlung (der `Order`).</span><span class="sxs-lookup"><span data-stu-id="a1e79-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="a1e79-117">Ist eine Navigationseigenschaft, `CustomerNavProp`, für den `Order`-Entitätstyp vorhanden, wäre sein Datentyp dementsprechend `Customer`, da die Multiplizität des Remoteendes "eins" (1) beträgt.</span><span class="sxs-lookup"><span data-stu-id="a1e79-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="a1e79-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1e79-118">Example</span></span>

<span data-ttu-id="a1e79-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="a1e79-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="a1e79-120">Die Navigationseigenschaften `Publisher` und `Authors` werden für den Book-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="a1e79-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="a1e79-121">Die Navigationseigenschaft `Books` wird sowohl für den Publisher-Entitätstyp als auch den `Author`-Entitätstyp definiert.</span><span class="sxs-lookup"><span data-stu-id="a1e79-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

 ![Das Diagramm zeigt ein konzeptionelles Modell mit drei Entitätstypen.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="a1e79-123">Die [ADO.NET Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](./ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a1e79-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a1e79-124">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="a1e79-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="a1e79-125">Beachten Sie, dass XML-Attribute verwendet werden, um die erforderlichen Informationen zum Definieren einer Navigationseigenschaft zu kommunizieren: Das Attribut `Name` enthält den Namen der Eigenschaft, die `Relationship` enthält den Namen der sie navigiert, Zuordnung und `FromRole` und `ToRole` enthalten die Enden der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="a1e79-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1e79-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1e79-126">See also</span></span>

- [<span data-ttu-id="a1e79-127">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a1e79-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a1e79-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="a1e79-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="a1e79-129">Beziehungen, Navigationseigenschaften und Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="a1e79-129">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
