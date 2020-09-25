---
title: Einschränkung der referenziellen Integrität
description: Erfahren Sie mehr über Einschränkungen der referenziellen Integrität in der Entity Data Model, die sicherstellen, dass gültige Zuordnungen zwischen Entitäts Typen immer vorhanden sind.
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 6ade9d0155a6915757c7f47c5cb3ab0a51dbd437
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172735"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="ffeae-103">Einschränkung der referenziellen Integrität</span><span class="sxs-lookup"><span data-stu-id="ffeae-103">referential integrity constraint</span></span>

<span data-ttu-id="ffeae-104">Eine *Einschränkung der referenziellen Integrität* im Entity Data Model (EDM) ähnelt einer Einschränkung der referenziellen Integrität in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ffeae-104">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="ffeae-105">Auf dieselbe Weise, wie eine Spalte (oder Spalten) einer Datenbanktabelle auf den Primärschlüssel einer anderen Tabelle verweisen kann, kann eine [Eigenschaft](property.md) (oder Eigenschaften) eines [Entitäts Typs](entity-type.md) auf den [Entitäts Schlüssel](entity-key.md) eines anderen Entitäts Typs verweisen.</span><span class="sxs-lookup"><span data-stu-id="ffeae-105">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="ffeae-106">Der Entitätstyp, auf den verwiesen wird, wird als *Prinzipal Ende* der Einschränkung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffeae-106">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="ffeae-107">Der Entitätstyp, der auf das Prinzipal Ende verweist, wird als *abhängiges Ende* der Einschränkung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffeae-107">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="ffeae-108">Eine Einschränkung der referenziellen Integrität wird als Teil einer Zuordnung [zwischen zwei](association-type.md) Entitäts Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="ffeae-108">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="ffeae-109">Die Definition für eine Einschränkung der referenziellen Integrität gibt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="ffeae-109">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="ffeae-110">Das Prinzipalende der Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="ffeae-110">The principal end of the constraint.</span></span> <span data-ttu-id="ffeae-111">(Ein Entitätstyp, auf dessen Entitätsschlüssel durch das abhängige Ende verwiesen wird.)</span><span class="sxs-lookup"><span data-stu-id="ffeae-111">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="ffeae-112">Den Entitätsschlüssel des Prinzipalendes.</span><span class="sxs-lookup"><span data-stu-id="ffeae-112">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="ffeae-113">Das abhängige Ende der Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="ffeae-113">The dependent end of the constraint.</span></span> <span data-ttu-id="ffeae-114">(Ein Entitätstyp, der über eine Eigenschaft oder Eigenschaften verfügt, die auf den Entitätsschlüssel des Prinzipalendes verweisen.)</span><span class="sxs-lookup"><span data-stu-id="ffeae-114">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="ffeae-115">Die verweisende Eigenschaft oder Eigenschaften des abhängigen Endes.</span><span class="sxs-lookup"><span data-stu-id="ffeae-115">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="ffeae-116">Mit Einschränkungen der referenziellen Integrität im EDM soll sichergestellt werden, dass gültige Zuordnungen immer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ffeae-116">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="ffeae-117">Weitere Informationen finden Sie unter [Fremdschlüssel Eigenschaft](foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="ffeae-117">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffeae-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ffeae-118">Example</span></span>  

 <span data-ttu-id="ffeae-119">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="ffeae-119">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="ffeae-120">Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.</span><span class="sxs-lookup"><span data-stu-id="ffeae-120">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="ffeae-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Beispiel eines referenziellen Einschränkungs Modells")</span><span class="sxs-lookup"><span data-stu-id="ffeae-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="ffeae-122">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ffeae-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="ffeae-123">Die folgende CSDL definiert eine Einschränkung der referenziellen Integrität für die oben im konzeptionellen Modell gezeigte `PublishedBy`-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ffeae-123">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="ffeae-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffeae-124">See also</span></span>

- [<span data-ttu-id="ffeae-125">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ffeae-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="ffeae-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="ffeae-126">Entity Data Model</span></span>](entity-data-model.md)
