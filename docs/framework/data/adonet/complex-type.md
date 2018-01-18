---
title: Komplexer Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6a7fbdace6403d2f1037beff8fe28d7c934d3174
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="complex-type"></a><span data-ttu-id="7a6e3-102">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="7a6e3-102">complex type</span></span>
<span data-ttu-id="7a6e3-103">Ein *komplexen Typ* ist eine Vorlage zum Definieren von umfangreichen, strukturierter Eigenschaften für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) oder andere komplexe Typen.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="7a6e3-104">Jede Vorlage enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7a6e3-104">Each template contains the following:</span></span>  
  
-   <span data-ttu-id="7a6e3-105">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-105">A unique name.</span></span> <span data-ttu-id="7a6e3-106">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="7a6e3-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a6e3-107">Der Name eines komplexen Typs darf nicht mit dem Namen eines Entitätstyps innerhalb des gleichen Namespace übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
-   <span data-ttu-id="7a6e3-108">Daten in Form einer oder mehrerer [Eigenschaften](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="7a6e3-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="7a6e3-109">(Optional)</span><span class="sxs-lookup"><span data-stu-id="7a6e3-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a6e3-110">Eine Eigenschaft eines komplexen Typs kann ein anderer komplexer Typ sein.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="7a6e3-111">Ein komplexer Typ ähnelt insofern einem Entitätstyp, als ein komplexer Typ eine Datennutzlast in Form von primitiven Typeigenschaften oder anderen komplexen Typen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="7a6e3-112">Es gibt jedoch einige Hauptunterschiede zwischen komplexen Typen und Entitätstypen:</span><span class="sxs-lookup"><span data-stu-id="7a6e3-112">However, there are some key differences between complex types and entity types:</span></span>  
  
-   <span data-ttu-id="7a6e3-113">Komplexe Typen weisen keine Identitäten auf und können daher nicht unabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="7a6e3-114">Komplexe Typen können nur Eigenschaften von Entitätstypen oder anderen komplexen Typen sein.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
-   <span data-ttu-id="7a6e3-115">Komplexe Typen können nicht beteiligt [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="7a6e3-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="7a6e3-116">Enden einer Zuordnung kann ein komplexer Typ sein und daher [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) kann nicht für complex-Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a6e3-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a6e3-117">Example</span></span>  
 <span data-ttu-id="7a6e3-118">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="7a6e3-119">Die folgende CSDL definiert einen komplexen Typ, Adress, mit den primitiven Typeigenschaften `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="7a6e3-120">Deklarieren Sie den Eigenschaftentyp in der Entitätstypdefinition, um den komplexen Typ `Address` (oben) als Eigenschaft für einen Entitätstyp zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7a6e3-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="7a6e3-121">Die folgende CSDL deklariert die `Address`-Eigenschaft als komplexen Typ für einen Entitätstyp (Publisher):</span><span class="sxs-lookup"><span data-stu-id="7a6e3-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="7a6e3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a6e3-122">See Also</span></span>  
 [<span data-ttu-id="7a6e3-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7a6e3-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="7a6e3-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7a6e3-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
