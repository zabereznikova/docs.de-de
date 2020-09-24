---
title: Zuordnungssatz
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: 58d8794a21cc37ab84386c820b192fb29946095c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153429"
---
# <a name="association-set"></a><span data-ttu-id="3e039-102">Zuordnungssatz</span><span class="sxs-lookup"><span data-stu-id="3e039-102">association set</span></span>

<span data-ttu-id="3e039-103">Ein Zuordnungs *Satz* ist ein logischer Container [für](association-type.md) Zuordnungs Instanzen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="3e039-103">An *association set* is a logical container for [association](association-type.md) instances of the same type.</span></span> <span data-ttu-id="3e039-104">Ein Zuordnungssatz ist keine Datenmodellkonstruktion; das heißt, er beschreibt nicht die Struktur von Daten oder Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="3e039-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="3e039-105">Vielmehr stellt ein Zuordnungssatz eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Zuordnungsinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="3e039-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="3e039-106">Ein Zuordnungs Satz ist innerhalb eines [Entitäts Containers](entity-container.md)definiert, einer logischen Gruppierung von [Entitätenmengen](entity-set.md) und Zuordnungs Sätzen.</span><span class="sxs-lookup"><span data-stu-id="3e039-106">An association set is defined within an [entity container](entity-container.md), which is a logical grouping of [entity sets](entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="3e039-107">Eine Definition für einen Zuordnungssatz enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="3e039-107">A definition for an association set contains the following information:</span></span>  
  
- <span data-ttu-id="3e039-108">Den Namen des Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="3e039-108">The association set name.</span></span> <span data-ttu-id="3e039-109">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="3e039-109">(Required)</span></span>  
  
- <span data-ttu-id="3e039-110">Die Zuordnung, von der er Instanzen enthält.</span><span class="sxs-lookup"><span data-stu-id="3e039-110">The association of which it will contain instances.</span></span> <span data-ttu-id="3e039-111">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="3e039-111">(Required)</span></span>  
  
- <span data-ttu-id="3e039-112">Zwei Zuordnungs [Sätze enden](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="3e039-112">Two [association set ends](association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e039-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e039-113">Example</span></span>  

 <span data-ttu-id="3e039-114">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="3e039-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="3e039-115">Obwohl die Abbildung keine Informationen zu Zuordnungssätzen bereitstellt, zeigt die nächste Abbildung ein Beispiel für Zuordnungssätze und Entitätenmengen auf Grundlage dieses Modells.</span><span class="sxs-lookup"><span data-stu-id="3e039-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="3e039-117">Das folgende Beispiel zeigt einen Zuordnungssatz (`PublishedBy`) und zwei Entitätenmengen (`Books` und `Publishers`), basierend auf dem oben gezeigten Modell.</span><span class="sxs-lookup"><span data-stu-id="3e039-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="3e039-118">BI in der `Books` Entitätenmenge stellt zur Laufzeit eine Instanz des `Book` Entitäts Typs dar.</span><span class="sxs-lookup"><span data-stu-id="3e039-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="3e039-119">Ebenso stellt PJ eine- `Publisher` Instanz in der `Publishers` Entitätenmenge dar.</span><span class="sxs-lookup"><span data-stu-id="3e039-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="3e039-120">Bipj stellt eine Instanz der Zuordnung `PublishedBy` im Zuordnungs `PublishedBy` Satz dar.</span><span class="sxs-lookup"><span data-stu-id="3e039-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/association-set/sets-example-association.gif)  
  
 <span data-ttu-id="3e039-122">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3e039-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="3e039-123">Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung.</span><span class="sxs-lookup"><span data-stu-id="3e039-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="3e039-124">Beachten Sie, dass der Name und die Zuordnung für jeden Zuordnungssatz mit XML-Attributen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="3e039-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="3e039-125">Es ist möglich, mehrere Zuordnungs Sätze pro Zuordnung zu definieren, solange keine zwei Zuordnungs Sätze ein Zuordnungs [Satz-Ende](association-set-end.md)gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e039-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](association-set-end.md).</span></span> <span data-ttu-id="3e039-126">Die folgende CSDL definiert einen Entitätscontainer mit zwei Zuordnungssätzen für die `WrittenBy`-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="3e039-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="3e039-127">Beachten Sie, dass mehrere Entitätssätze für die Entitätstypen `Book` und `Author` definiert wurden, und dass sich kein Zuordnungssatz ein Zuordnungssatzende teilt.</span><span class="sxs-lookup"><span data-stu-id="3e039-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="3e039-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e039-128">See also</span></span>

- [<span data-ttu-id="3e039-129">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3e039-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="3e039-130">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="3e039-130">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="3e039-131">Fremdschlüsseleigenschaft</span><span class="sxs-lookup"><span data-stu-id="3e039-131">foreign key property</span></span>](foreign-key-property.md)
