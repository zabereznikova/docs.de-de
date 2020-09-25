---
title: Entitätstyp
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3f99667a06d8aa439232802d4909290dfe9db97c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194777"
---
# <a name="entity-type"></a><span data-ttu-id="f56c0-102">Entitätstyp</span><span class="sxs-lookup"><span data-stu-id="f56c0-102">entity type</span></span>

<span data-ttu-id="f56c0-103">Der *Entitätstyp* ist der grundlegende Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="f56c0-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="f56c0-104">In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen.</span><span class="sxs-lookup"><span data-stu-id="f56c0-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="f56c0-105">Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen.</span><span class="sxs-lookup"><span data-stu-id="f56c0-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="f56c0-106">Jede Vorlage enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="f56c0-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="f56c0-107">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f56c0-107">A unique name.</span></span> <span data-ttu-id="f56c0-108">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="f56c0-108">(Required.)</span></span>  
  
- <span data-ttu-id="f56c0-109">Ein [Entitäts Schlüssel](entity-key.md) , der durch eine oder mehrere Eigenschaften definiert wird.</span><span class="sxs-lookup"><span data-stu-id="f56c0-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="f56c0-110">(Erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="f56c0-110">(Required.)</span></span>  
  
- <span data-ttu-id="f56c0-111">Daten in Form von [Eigenschaften](property.md).</span><span class="sxs-lookup"><span data-stu-id="f56c0-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="f56c0-112">(Optional.)</span><span class="sxs-lookup"><span data-stu-id="f56c0-112">(Optional.)</span></span>  
  
- <span data-ttu-id="f56c0-113">[Navigations Eigenschaften](navigation-property.md) , die die Navigation von einem [Ende](association-end.md) [einer Zuordnung zum anderen](association-type.md) Ende ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f56c0-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="f56c0-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="f56c0-114">(Optional)</span></span>  
  
 <span data-ttu-id="f56c0-115">In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung.</span><span class="sxs-lookup"><span data-stu-id="f56c0-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="f56c0-116">Jede Instanz eines Entitäts Typs muss über einen eindeutigen [Entitäts Schlüssel](entity-key.md) innerhalb einer [Entitätenmenge](entity-set.md)verfügen.</span><span class="sxs-lookup"><span data-stu-id="f56c0-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="f56c0-117">Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f56c0-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f56c0-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f56c0-118">Example</span></span>  

 <span data-ttu-id="f56c0-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:</span><span class="sxs-lookup"><span data-stu-id="f56c0-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="f56c0-121">Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "(Schlüssel)" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f56c0-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="f56c0-122">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f56c0-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="f56c0-123">Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:</span><span class="sxs-lookup"><span data-stu-id="f56c0-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="f56c0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f56c0-124">See also</span></span>

- [<span data-ttu-id="f56c0-125">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f56c0-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="f56c0-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f56c0-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="f56c0-127">facet</span><span class="sxs-lookup"><span data-stu-id="f56c0-127">facet</span></span>](facet.md)
