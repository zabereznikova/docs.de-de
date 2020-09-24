---
title: Multiplizität des Zuordnungsendes
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cf9e6b5af0dc6a33af364901c631b4ce66fe0480
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153507"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="32f6f-102">Multiplizität des Zuordnungsendes</span><span class="sxs-lookup"><span data-stu-id="32f6f-102">association end multiplicity</span></span>

<span data-ttu-id="32f6f-103">Die Multiplizität des Zuordnungs *Endes* definiert die Anzahl von [Entitätstyp](entity-type.md) Instanzen, die an einem [Ende einer Zuordnung liegen können.](association-type.md)</span><span class="sxs-lookup"><span data-stu-id="32f6f-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="32f6f-104">Eine Multiplizität des Zuordnungsendes kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="32f6f-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="32f6f-105">eins (1): Gibt an, dass genau eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="32f6f-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="32f6f-106">null oder eins (0..1): Gibt an, dass keine (null) oder eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="32f6f-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="32f6f-107">Many ( \* ): gibt an, dass keine, eine oder mehrere Entitätstyp Instanzen am Zuordnungs Ende vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="32f6f-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="32f6f-108">Eine Zuordnung wird oft nach ihren Zuordnungsendemultiplizitäten charakterisiert.</span><span class="sxs-lookup"><span data-stu-id="32f6f-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="32f6f-109">Wenn z. b. die Enden einer Zuordnung Multiplizitäten a (1) und many ( \* ) aufweisen, wird die Zuordnung als 1: n-Zuordnung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="32f6f-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="32f6f-110">Im Beispiel unten ist die `PublishedBy`-Zuordnung eine 1:n-Zuordnung (ein Verleger veröffentlicht viele Bücher, und ein Buch wird von einem Verleger veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="32f6f-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="32f6f-111">Die `WrittenBy`-Zuordnung ist eine m:n-Zuordnung (ein Buch kann mehrere Autoren haben, und ein Autor kann mehrere Bücher schreiben).</span><span class="sxs-lookup"><span data-stu-id="32f6f-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="32f6f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32f6f-112">Example</span></span>  

 <span data-ttu-id="32f6f-113">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="32f6f-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="32f6f-114">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="32f6f-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="32f6f-115">Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität des `Book` Endes ist many ( \* ).</span><span class="sxs-lookup"><span data-stu-id="32f6f-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="32f6f-117">Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="32f6f-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="32f6f-118">Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:</span><span class="sxs-lookup"><span data-stu-id="32f6f-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="32f6f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32f6f-119">See also</span></span>

- [<span data-ttu-id="32f6f-120">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="32f6f-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="32f6f-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="32f6f-121">Entity Data Model</span></span>](entity-data-model.md)
