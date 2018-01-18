---
title: "Fremdschlüsseleigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 044be77cbbd8b5ad16cfbd5bbf1fdde984a060d5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="foreign-key-property"></a><span data-ttu-id="bb5d8-102">Fremdschlüsseleigenschaft</span><span class="sxs-lookup"><span data-stu-id="bb5d8-102">foreign key property</span></span>
<span data-ttu-id="bb5d8-103">Ein *Fremdschlüsseleigenschaft* im Entity Data Model (EDM) ist ein primitiver Typ [Eigenschaft](../../../../docs/framework/data/adonet/property.md) (oder einen Satz von primitiven Typeigenschaften) auf eine [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) , enthält die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) eines anderen Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="bb5d8-104">Eine Fremdschlüsseleigenschaft entspricht einer Fremdschlüsselspalte in einer relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="bb5d8-105">Auf die gleiche Weise, dass Fremdschlüsselspalten in einer relationalen Datenbank verwendet werden, um Beziehungen zwischen Zeilen in Tabellen zu erstellen, dienen Fremdschlüsseleigenschaften in einem konzeptionellen Modell herstellen [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md) zwischen Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="bb5d8-106">Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) dient zum Definieren einer Beziehung zwischen zwei Entitätstypen, wenn einer der Typen eine Fremdschlüsseleigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb5d8-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb5d8-107">Example</span></span>  
 <span data-ttu-id="bb5d8-108">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="bb5d8-109">Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="bb5d8-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="bb5d8-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="bb5d8-111">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="bb5d8-112">Die folgende CSDL verwendet die Fremdschlüsseleigenschaft `PublisherId`, um eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung zu definieren, die im konzeptionellen Modell oben gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5d8-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="bb5d8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb5d8-113">See Also</span></span>  
 [<span data-ttu-id="bb5d8-114">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="bb5d8-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="bb5d8-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="bb5d8-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
