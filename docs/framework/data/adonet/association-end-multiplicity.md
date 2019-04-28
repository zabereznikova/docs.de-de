---
title: Multiplizität des Zuordnungsendes
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 59eed56204543adf405cfc7c71a49697a9e18374
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769668"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="b5568-102">Multiplizität des Zuordnungsendes</span><span class="sxs-lookup"><span data-stu-id="b5568-102">association end multiplicity</span></span>
<span data-ttu-id="b5568-103">*Zuordnungsendes* definiert die Anzahl der [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) -Instanzen, die an einem Ende einer [Zuordnung](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="b5568-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="b5568-104">Eine Multiplizität des Zuordnungsendes kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="b5568-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="b5568-105">eins (1): Gibt an, dass diese genau eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b5568-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="b5568-106">0 (null) oder eine (0.. 1): Gibt an, dass 0 (null) oder eine Entitätstypinstanz am Zuordnungsende vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b5568-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="b5568-107">viele (\*): Gibt an, dass 0 (null), einer oder mehrere Instanzen eines Entitätstyps am Zuordnungsende vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b5568-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="b5568-108">Eine Zuordnung wird oft nach ihren Zuordnungsendemultiplizitäten charakterisiert.</span><span class="sxs-lookup"><span data-stu-id="b5568-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="b5568-109">Wenn die Enden einer Zuordnung die Multiplizitäten eins (1) und viele haben z. B. (\*), die Zuordnung wird als eine 1: n Zuordnung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b5568-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="b5568-110">Im Beispiel unten ist die `PublishedBy`-Zuordnung eine 1:n-Zuordnung (ein Verleger veröffentlicht viele Bücher, und ein Buch wird von einem Verleger veröffentlicht).</span><span class="sxs-lookup"><span data-stu-id="b5568-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="b5568-111">Die `WrittenBy`-Zuordnung ist eine m:n-Zuordnung (ein Buch kann mehrere Autoren haben, und ein Autor kann mehrere Bücher schreiben).</span><span class="sxs-lookup"><span data-stu-id="b5568-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5568-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5568-112">Example</span></span>  
 <span data-ttu-id="b5568-113">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="b5568-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="b5568-114">Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="b5568-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="b5568-115">Die Multiplizität des der `Publisher` -Endes ist eins (1), und die Multiplizität der `Book` End kann viele (\*).</span><span class="sxs-lookup"><span data-stu-id="b5568-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Beispielmodell mit drei Entitätstypen](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="b5568-117">Das ADO.NET Entity Framework verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b5568-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="b5568-118">Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:</span><span class="sxs-lookup"><span data-stu-id="b5568-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b5568-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5568-119">See also</span></span>

- [<span data-ttu-id="b5568-120">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b5568-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="b5568-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b5568-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
