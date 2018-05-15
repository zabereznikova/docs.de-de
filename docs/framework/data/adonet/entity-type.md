---
title: Entitätstyp
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: c694f29d36988ea52aeca650cf2bba2c50c91e89
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="entity-type"></a><span data-ttu-id="b7faf-102">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="b7faf-102">entity type</span></span>
<span data-ttu-id="b7faf-103">Die *Entitätstyp* ist der wesentliche Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="b7faf-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="b7faf-104">In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="b7faf-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="b7faf-105">Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen.</span><span class="sxs-lookup"><span data-stu-id="b7faf-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="b7faf-106">Jede Vorlage enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="b7faf-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="b7faf-107">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b7faf-107">A unique name.</span></span> <span data-ttu-id="b7faf-108">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="b7faf-108">(Required.)</span></span>  
  
-   <span data-ttu-id="b7faf-109">Ein [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) von einer oder mehreren Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="b7faf-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="b7faf-110">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="b7faf-110">(Required.)</span></span>  
  
-   <span data-ttu-id="b7faf-111">Daten in Form von [Eigenschaften](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="b7faf-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="b7faf-112">(Optional)</span><span class="sxs-lookup"><span data-stu-id="b7faf-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="b7faf-113">[Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) , mit denen für die Navigation von einem [End](../../../../docs/framework/data/adonet/association-end.md) von einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zum anderen Ende.</span><span class="sxs-lookup"><span data-stu-id="b7faf-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="b7faf-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="b7faf-114">(Optional)</span></span>  
  
 <span data-ttu-id="b7faf-115">In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung.</span><span class="sxs-lookup"><span data-stu-id="b7faf-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="b7faf-116">Jede Instanz eines Entitätstyps muss eine eindeutige haben [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="b7faf-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="b7faf-117">Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b7faf-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7faf-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7faf-118">Example</span></span>  
 <span data-ttu-id="b7faf-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:</span><span class="sxs-lookup"><span data-stu-id="b7faf-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="b7faf-120">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="b7faf-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="b7faf-121">Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "(Schlüssel)" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b7faf-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="b7faf-122">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b7faf-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="b7faf-123">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="b7faf-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b7faf-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7faf-124">See Also</span></span>  
 [<span data-ttu-id="b7faf-125">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b7faf-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="b7faf-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b7faf-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="b7faf-127">facet</span><span class="sxs-lookup"><span data-stu-id="b7faf-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
