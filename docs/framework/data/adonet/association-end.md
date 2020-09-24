---
title: Zuordnungsende
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 00e3a7d855957ae539ea652dc8cde3ed8841dda5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153442"
---
# <a name="association-end"></a><span data-ttu-id="06403-102">Zuordnungsende</span><span class="sxs-lookup"><span data-stu-id="06403-102">association end</span></span>

<span data-ttu-id="06403-103">Ein *Assoziationsende* identifiziert den [Entitätstyp](entity-type.md) an einem [Ende einer Zuordnung und die](association-type.md) Anzahl der Entitätstyp Instanzen, die an diesem Ende einer Zuordnung vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="06403-103">An *association end* identifies the [entity type](entity-type.md) on one end of an [association](association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="06403-104">Zuordnungsenden werden als Teil einer Zuordnung definiert. Eine Zuordnung muss genau zwei Zuordnungsenden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="06403-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="06403-105">[Navigations Eigenschaften](navigation-property.md) ermöglichen die Navigation von einem Zuordnungs Ende zum anderen.</span><span class="sxs-lookup"><span data-stu-id="06403-105">[Navigation properties](navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="06403-106">Eine Zuordnungsendedefinition enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="06403-106">An association end definition contains the following information:</span></span>  
  
- <span data-ttu-id="06403-107">Einen der Entitätstypen der Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="06403-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="06403-108">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="06403-108">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="06403-109">Für eine bestimmte Zuordnung kann der für jedes Zuordnungsende angegebene Entitätstyp gleich sein.</span><span class="sxs-lookup"><span data-stu-id="06403-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="06403-110">Dadurch wird eine Selbstzuordnung erstellt.</span><span class="sxs-lookup"><span data-stu-id="06403-110">This creates a self-association.</span></span>  
  
- <span data-ttu-id="06403-111">Eine Multiplizität des Zuordnungs [Endes](association-end-multiplicity.md) , die die Anzahl von Entitätstyp Instanzen angibt, die an einem Ende der Zuordnung liegen können.</span><span class="sxs-lookup"><span data-stu-id="06403-111">An [association end multiplicity](association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="06403-112">Die Multiplizität eines Zuordnungs Endes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele ( \* ) haben.</span><span class="sxs-lookup"><span data-stu-id="06403-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
- <span data-ttu-id="06403-113">Der Name für das Zuordnungsende.</span><span class="sxs-lookup"><span data-stu-id="06403-113">A name for the association end.</span></span> <span data-ttu-id="06403-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="06403-114">(Optional)</span></span>  
  
- <span data-ttu-id="06403-115">Informationen zu Vorgängen, die für das Zuordnungsende ausgeführt werden, z. B. ON DELETE CASCADE.</span><span class="sxs-lookup"><span data-stu-id="06403-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="06403-116">(Optional)</span><span class="sxs-lookup"><span data-stu-id="06403-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="06403-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06403-117">Example</span></span>  

 <span data-ttu-id="06403-118">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="06403-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="06403-119">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="06403-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="06403-120">Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität des `Book` Endes ist "Many ( \* )", was bedeutet, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="06403-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="06403-122">Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="06403-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="06403-123">Die nachfolgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="06403-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="06403-124">Beachten Sie, dass Typ, Name und Multiplizität jedes Zuordnungsendes von XML-Attributen (den Attribute `Type`, `Role` bzw. `Multiplicity`) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06403-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="06403-125">Optionale Informationen zu für ein Ende ausgeführten Vorgängen werden in einem XML-Element (dem `OnDelete`-Element) angegeben.</span><span class="sxs-lookup"><span data-stu-id="06403-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="06403-126">In diesem Fall werden beim Löschen eines Verlegers auch alle zugeordneten Bücher gelöscht.</span><span class="sxs-lookup"><span data-stu-id="06403-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="06403-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06403-127">See also</span></span>

- [<span data-ttu-id="06403-128">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="06403-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="06403-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="06403-129">Entity Data Model</span></span>](entity-data-model.md)
