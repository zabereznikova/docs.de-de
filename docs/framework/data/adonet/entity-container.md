---
title: Entitätscontainer
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 0c194d86e6276c948a545f830e569cbc68f86a14
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737872"
---
# <a name="entity-container"></a><span data-ttu-id="1571d-102">Entitätscontainer</span><span class="sxs-lookup"><span data-stu-id="1571d-102">entity container</span></span>
<span data-ttu-id="1571d-103">Ein *Entitätencontainer* ist eine logische Gruppierung von [Entitätenmengen](entity-set.md), Zuordnungs [Sätzen](association-set.md)und [Funktions Importen](model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="1571d-103">An *entity container* is a logical grouping of [entity sets](entity-set.md), [association sets](association-set.md), and [function imports](model-declared-function.md).</span></span>  
  
 <span data-ttu-id="1571d-104">Die folgenden Voraussetzungen müssen für einen in einem konzeptionellen Modell definierten Entitätscontainer erfüllt werden:</span><span class="sxs-lookup"><span data-stu-id="1571d-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="1571d-105">Mindestens ein Entitätscontainer muss in jedem konzeptionellen Modell definiert sein.</span><span class="sxs-lookup"><span data-stu-id="1571d-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="1571d-106">Der Entitätscontainer muss einen eindeutigen Namen innerhalb jedes konzeptionellen Modells aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1571d-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="1571d-107">Ein Entitätscontainer kann Entitätenmengen oder Zuordnungssätze definieren, die in einem oder mehreren Namespaces definierte Entitätstypen oder Zuordnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1571d-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="1571d-108">Weitere Informationen finden Sie unter [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="1571d-108">For more information, see [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1571d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1571d-109">Example</span></span>  
 <span data-ttu-id="1571d-110">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="1571d-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="1571d-111">Weitere Informationen finden Sie im nächsten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1571d-111">See the next example for more information.</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="1571d-113">Obwohl die Abbildung keine Entitätscontainerinformationen bereitstellt, muss das konzeptionelle Modell einen Entitätscontainer definieren.</span><span class="sxs-lookup"><span data-stu-id="1571d-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="1571d-114">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine DSL namens konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1571d-114">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="1571d-115">Die folgende CSDL definiert einen Entitätscontainer für das in der Abbildung oben gezeigte konzeptionelle Modell.</span><span class="sxs-lookup"><span data-stu-id="1571d-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="1571d-116">Beachten Sie, dass der Name des Entitätscontainers in einem XML-Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="1571d-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1571d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1571d-117">See also</span></span>

- [<span data-ttu-id="1571d-118">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1571d-118">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="1571d-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1571d-119">Entity Data Model</span></span>](entity-data-model.md)
