---
title: "Multiplizität des Zuordnungsendes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3d6071b2dfab4a1f057c9e04b84e1163fb0a53c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="593d8-102">Multiplizität des Zuordnungsendes</span><span class="sxs-lookup"><span data-stu-id="593d8-102">association end multiplicity</span></span>
<span data-ttu-id="593d8-103">*Zuordnungsendes* definiert die Anzahl von [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) Instanzen, die an einem Ende einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="593d8-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="593d8-104">Eine Multiplizität des Zuordnungsendes kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="593d8-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="593d8-105">eins (1): Gibt an, dass genau eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="593d8-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="593d8-106">null oder eins (0..1): Gibt an, dass keine (null) oder eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="593d8-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="593d8-107">n (*): Gibt an, dass keine (null) oder mindestens eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="593d8-107">many (*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="593d8-108">Eine Zuordnung wird oft nach ihren Zuordnungsendemultiplizitäten charakterisiert.</span><span class="sxs-lookup"><span data-stu-id="593d8-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="593d8-109">Wenn die Zuordnungsenden z. B. die Multiplizitäten eins (1) und n (*) aufweisen, wird die Zuordnung als 1:n-Zuordnung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="593d8-109">For example, if the ends of an association have multiplicities one (1) and many (*), the association is called a one-to-many association.</span></span> <span data-ttu-id="593d8-110">Im Beispiel unten ist die `PublishedBy`-Zuordnung eine 1:n-Zuordnung (ein Verleger veröffentlicht viele Bücher, und ein Buch wird von einem Verleger veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="593d8-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="593d8-111">Die `WrittenBy`-Zuordnung ist eine m:n-Zuordnung (ein Buch kann mehrere Autoren haben, und ein Autor kann mehrere Bücher schreiben).</span><span class="sxs-lookup"><span data-stu-id="593d8-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="593d8-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="593d8-112">Example</span></span>  
 <span data-ttu-id="593d8-113">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="593d8-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="593d8-114">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="593d8-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="593d8-115">Die Multiplizität des `Publisher`-Endes ist eins (1), und die Multiplizität des `Book`-Endes ist n (*).</span><span class="sxs-lookup"><span data-stu-id="593d8-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*).</span></span>  
  
 <span data-ttu-id="593d8-116">![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="593d8-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="593d8-117">Das ADO.NET Entity Framework verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="593d8-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="593d8-118">Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:</span><span class="sxs-lookup"><span data-stu-id="593d8-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="593d8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="593d8-119">See Also</span></span>  
 [<span data-ttu-id="593d8-120">Schlüsselkonzepte von Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="593d8-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="593d8-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="593d8-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
