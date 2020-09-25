---
title: Fremdschlüsseleigenschaft
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: be0fcb94b0b457a33c17e7125cd22db50f298cc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189317"
---
# <a name="foreign-key-property"></a><span data-ttu-id="6da78-102">Fremdschlüsseleigenschaft</span><span class="sxs-lookup"><span data-stu-id="6da78-102">foreign key property</span></span>

<span data-ttu-id="6da78-103">Eine *Fremdschlüssel Eigenschaft* im Entity Data Model (EDM) ist eine primitive [Typeigenschaft](property.md) (oder ein Satz primitiver Typeigenschaften) für einen [Entitätstyp](entity-type.md) , der den [Entitäts Schlüssel](entity-key.md) eines anderen Entitäts Typs enthält.</span><span class="sxs-lookup"><span data-stu-id="6da78-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="6da78-104">Eine Fremdschlüsseleigenschaft entspricht einer Fremdschlüsselspalte in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6da78-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="6da78-105">Auf dieselbe Weise, wie Fremdschlüssel Spalten in einer relationalen Datenbank verwendet werden, um Beziehungen zwischen Zeilen in Tabellen zu erstellen, werden Fremdschlüssel Eigenschaften in einem konzeptionellen Modell verwendet, um [Zuordnungen](association-type.md) zwischen Entitäts Typen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="6da78-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="6da78-106">Eine [Einschränkung der referenziellen Integrität](referential-integrity-constraint.md) wird verwendet, um eine Zuordnung zwischen zwei Entitäts Typen zu definieren, wenn einer der Typen über eine Fremdschlüssel Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="6da78-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6da78-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6da78-107">Example</span></span>  

 <span data-ttu-id="6da78-108">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="6da78-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="6da78-109">Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.</span><span class="sxs-lookup"><span data-stu-id="6da78-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="6da78-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Beispiel eines referenziellen Einschränkungs Modells")</span><span class="sxs-lookup"><span data-stu-id="6da78-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="6da78-111">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6da78-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="6da78-112">Die folgende CSDL verwendet die Fremdschlüsseleigenschaft `PublisherId`, um eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung zu definieren, die im konzeptionellen Modell oben gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="6da78-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="6da78-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6da78-113">See also</span></span>

- [<span data-ttu-id="6da78-114">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="6da78-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="6da78-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="6da78-115">Entity Data Model</span></span>](entity-data-model.md)
