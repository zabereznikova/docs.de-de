---
title: Entitätenmenge
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 6286d3707a8506e7a389359a5aa361c152e75212
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194791"
---
# <a name="entity-set"></a><span data-ttu-id="d397f-102">Entitätenmenge</span><span class="sxs-lookup"><span data-stu-id="d397f-102">entity set</span></span>

<span data-ttu-id="d397f-103">Eine *Entitätenmenge* ist ein logischer Container für Instanzen eines [Entitäts Typs](entity-type.md) und Instanzen eines beliebigen Typs, der von diesem Entitätstyp abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d397f-103">An *entity set* is a logical container for instances of an [entity type](entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="d397f-104">(Informationen zu abgeleiteten Typen finden Sie unter [Entity Data Model: Vererbung](entity-data-model-inheritance.md).) Die Beziehung zwischen einem Entitätstyp und einer Entitätenmenge entspricht der Beziehung zwischen einer Zeile und einer Tabelle in einer relationalen Datenbank: wie eine Zeile beschreibt ein Entitätstyp die Datenstruktur, und wie eine Tabelle enthält eine Entitätenmenge Instanzen einer bestimmten Struktur.</span><span class="sxs-lookup"><span data-stu-id="d397f-104">(For information about derived types, see [Entity Data Model: Inheritance](entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="d397f-105">Eine Entitätenmenge ist keine Datenmodellkonstruktion, sie beschreibt keine Datenstruktur.</span><span class="sxs-lookup"><span data-stu-id="d397f-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="d397f-106">Vielmehr stellt eine Entitätenmenge eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Entitätstypinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="d397f-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="d397f-107">Eine Entitätenmenge wird innerhalb eines [Entitätencontainers](entity-container.md)definiert, einer logischen Gruppierung von Entitätenmengen und Zuordnungs [Sätzen](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="d397f-107">An entity set is defined within an [entity container](entity-container.md), which is a logical grouping of entity sets and [association sets](association-set.md).</span></span>  
  
 <span data-ttu-id="d397f-108">Die folgenden Voraussetzungen müssen erfüllt sein, damit eine Entitätstypinstanz in einer Entitätenmenge existiert:</span><span class="sxs-lookup"><span data-stu-id="d397f-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
- <span data-ttu-id="d397f-109">Der Typ der Instanz stimmt entweder mit dem Entitätstyp überein, auf dem die Entitätenmenge basiert, oder der Typ der Instanz ist ein Untertyp des Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="d397f-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
- <span data-ttu-id="d397f-110">Der [Entitäts Schlüssel](entity-key.md) für die-Instanz ist innerhalb der Entitätenmenge eindeutig.</span><span class="sxs-lookup"><span data-stu-id="d397f-110">The [entity key](entity-key.md) for the instance is unique within the entity set.</span></span>  
  
- <span data-ttu-id="d397f-111">Die Instanz ist in keiner anderen Entitätenmenge vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d397f-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d397f-112">Mehrere Entitätenmengen können mit dem gleichen Entitätstyp definiert werden, aber eine Instanz eines bestimmten Entitätstyps kann nur in einer Entitätenmenge vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d397f-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="d397f-113">Sie müssen nicht für jeden Entitätstyp in einem konzeptionellen Modell eine Entitätenmenge definieren.</span><span class="sxs-lookup"><span data-stu-id="d397f-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d397f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d397f-114">Example</span></span>  

 <span data-ttu-id="d397f-115">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="d397f-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="d397f-117">Die folgende Abbildung zeigt zwei Entitätenmengen (`Books` und `Publishers`) und einen Zuordnungssatz (`PublishedBy`) auf Grundlage des oben gezeigten konzeptionellen Modells.</span><span class="sxs-lookup"><span data-stu-id="d397f-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="d397f-118">BI in der `Books` Entitätenmenge stellt zur Laufzeit eine Instanz des `Book` Entitäts Typs dar.</span><span class="sxs-lookup"><span data-stu-id="d397f-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="d397f-119">Ebenso stellt PJ eine- `Publisher` Instanz in der `Publishers` Entitätenmenge dar.</span><span class="sxs-lookup"><span data-stu-id="d397f-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="d397f-120">Bipj stellt eine Instanz der Zuordnung `PublishedBy` im Zuordnungs `PublishedBy` Satz dar.</span><span class="sxs-lookup"><span data-stu-id="d397f-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/entity-set/sets-example-association.gif)  
  
 <span data-ttu-id="d397f-122">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d397f-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="d397f-123">Die folgende CSDL definiert einen Entitätscontainer mit einer Entitätenmenge für jeden Entitätstyp im oben gezeigten konzeptionellen Modell.</span><span class="sxs-lookup"><span data-stu-id="d397f-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="d397f-124">Beachten Sie, dass der Name und der Entitätstyp für jede Entitätenmenge mit XML-Attributen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d397f-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="d397f-125">Pro Typ (MEST) können mehrere Entitätssätze definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d397f-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="d397f-126">Die folgende CSDL definiert einen Entitätscontainer mit zwei Entitätenmengen für den `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="d397f-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d397f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d397f-127">See also</span></span>

- [<span data-ttu-id="d397f-128">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d397f-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="d397f-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d397f-129">Entity Data Model</span></span>](entity-data-model.md)
