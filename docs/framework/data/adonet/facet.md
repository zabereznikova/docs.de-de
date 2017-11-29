---
title: Facet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e72ecd610951a42ceb5c3aa581bf70f255e5e2f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="facet"></a><span data-ttu-id="76435-102">Facet</span><span class="sxs-lookup"><span data-stu-id="76435-102">facet</span></span>
<span data-ttu-id="76435-103">Ein *Facet* wird verwendet, um einer primitiven typeigenschaftendefinition Details hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="76435-103">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="76435-104">Ein [Eigenschaft](../../../../docs/framework/data/adonet/property.md) Definition enthält Informationen zum Eigenschaftentyp, oft ausführlicher ist jedoch erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76435-104">A [property](../../../../docs/framework/data/adonet/property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="76435-105">Ein Entitätstyp in einem konzeptionellen Modell könnte z. B. über eine Eigenschaft vom Typ `String` verfügen, deren Wert nicht auf NULL festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="76435-105">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="76435-106">Mit Facets können Sie diese Detailebene angeben.</span><span class="sxs-lookup"><span data-stu-id="76435-106">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="76435-107">In der nachfolgenden Tabelle werden die im EDM unterstützten Facets beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76435-107">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76435-108">Die genauen Werte und Verhalten von Facets werden von der Laufzeitumgebung bestimmt, die eine EDM-Implementierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="76435-108">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="76435-109">Facet</span><span class="sxs-lookup"><span data-stu-id="76435-109">Facet</span></span>|<span data-ttu-id="76435-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76435-110">Description</span></span>|<span data-ttu-id="76435-111">Betrifft</span><span class="sxs-lookup"><span data-stu-id="76435-111">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="76435-112">Gibt die bei Vergleich- und Sortiervorgängen zu verwendende Sortierreihenfolge für die Werte der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="76435-112">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="76435-113">Gibt an, dass der Eigenschaftswert für Prüfungen der vollständigen Parallelität verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76435-113">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="76435-114">Alle primitiven Typeigenschaften</span><span class="sxs-lookup"><span data-stu-id="76435-114">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="76435-115">Gibt den Standardwert der Eigenschaft an, wenn bei der Instanziierung kein Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76435-115">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="76435-116">Alle primitiven Typeigenschaften</span><span class="sxs-lookup"><span data-stu-id="76435-116">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="76435-117">Gibt an, ob sich die Länge des Eigenschaftswerts ändern kann.</span><span class="sxs-lookup"><span data-stu-id="76435-117">Specifies whether the length of the property value can vary.</span></span>|<span data-ttu-id="76435-118">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="76435-118">`Binary`, `String`</span></span>|  
|`MaxLength`|<span data-ttu-id="76435-119">Gibt die maximale Länge des Eigenschaftswerts an.</span><span class="sxs-lookup"><span data-stu-id="76435-119">Specifies the maximum length of the property value.</span></span>|<span data-ttu-id="76435-120">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="76435-120">`Binary`, `String`</span></span>|  
|`Nullable`|<span data-ttu-id="76435-121">Gibt an, ob die Eigenschaft über einen NULL-Wert verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="76435-121">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="76435-122">Alle primitiven Typeigenschaften</span><span class="sxs-lookup"><span data-stu-id="76435-122">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="76435-123">Bei Eigenschaften des Typs `Decimal` wird die Anzahl der Ziffern angegeben, über die ein Eigenschaftswert verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="76435-123">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="76435-124">Bei Eigenschaften der Typen `Time`, `DateTime` und `DateTimeOffset` wird die Anzahl der Dezimalstellen für die Sekunden des Eigenschaftswerts angegeben.</span><span class="sxs-lookup"><span data-stu-id="76435-124">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|<span data-ttu-id="76435-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="76435-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="76435-126">Gibt die Anzahl der Dezimalstellen für den Eigenschaftswert an.</span><span class="sxs-lookup"><span data-stu-id="76435-126">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="76435-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="76435-127">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="76435-128">Gibt an, ob der Eigenschaftswert als Unicode gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="76435-128">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="76435-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76435-129">Example</span></span>  
 <span data-ttu-id="76435-130">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="76435-130">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="76435-131">Die folgende CSDL definiert einen `Book`-Entitätstyp.</span><span class="sxs-lookup"><span data-stu-id="76435-131">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="76435-132">Beachten Sie, dass Facets als XML-Attribute implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="76435-132">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="76435-133">Die Facetwerte geben an, dass keine Eigenschaft auf NULL festgelegt werden kann, und dass `Scale` und `Precision` der `Revision`-Eigenschaft jeweils auf 29 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="76435-133">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="76435-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76435-134">See Also</span></span>  
 [<span data-ttu-id="76435-135">Schlüsselkonzepte von Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76435-135">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="76435-136">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76435-136">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
