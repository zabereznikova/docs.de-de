---
title: Komplexer Typ
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 8daeac8309434b3c4e090d8e75f2de02d63e8b11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756812"
---
# <a name="complex-type"></a><span data-ttu-id="1256e-102">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="1256e-102">complex type</span></span>
<span data-ttu-id="1256e-103">Ein *komplexen Typ* ist eine Vorlage zum Definieren von umfangreichen, strukturierter Eigenschaften für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) oder andere komplexe Typen.</span><span class="sxs-lookup"><span data-stu-id="1256e-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="1256e-104">Jede Vorlage enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1256e-104">Each template contains the following:</span></span>  
  
-   <span data-ttu-id="1256e-105">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="1256e-105">A unique name.</span></span> <span data-ttu-id="1256e-106">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="1256e-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1256e-107">Der Name eines komplexen Typs darf nicht mit dem Namen eines Entitätstyps innerhalb des gleichen Namespace übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1256e-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
-   <span data-ttu-id="1256e-108">Daten in Form einer oder mehrerer [Eigenschaften](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="1256e-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="1256e-109">(Optional)</span><span class="sxs-lookup"><span data-stu-id="1256e-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1256e-110">Eine Eigenschaft eines komplexen Typs kann ein anderer komplexer Typ sein.</span><span class="sxs-lookup"><span data-stu-id="1256e-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="1256e-111">Ein komplexer Typ ähnelt insofern einem Entitätstyp, als ein komplexer Typ eine Datennutzlast in Form von primitiven Typeigenschaften oder anderen komplexen Typen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="1256e-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="1256e-112">Es gibt jedoch einige Hauptunterschiede zwischen komplexen Typen und Entitätstypen:</span><span class="sxs-lookup"><span data-stu-id="1256e-112">However, there are some key differences between complex types and entity types:</span></span>  
  
-   <span data-ttu-id="1256e-113">Komplexe Typen weisen keine Identitäten auf und können daher nicht unabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="1256e-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="1256e-114">Komplexe Typen können nur Eigenschaften von Entitätstypen oder anderen komplexen Typen sein.</span><span class="sxs-lookup"><span data-stu-id="1256e-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
-   <span data-ttu-id="1256e-115">Komplexe Typen können nicht beteiligt [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="1256e-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="1256e-116">Enden einer Zuordnung kann ein komplexer Typ sein und daher [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) kann nicht für complex-Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1256e-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1256e-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1256e-117">Example</span></span>  
 <span data-ttu-id="1256e-118">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1256e-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="1256e-119">Die folgende CSDL definiert einen komplexen Typ, Adress, mit den primitiven Typeigenschaften `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="1256e-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="1256e-120">Deklarieren Sie den Eigenschaftentyp in der Entitätstypdefinition, um den komplexen Typ `Address` (oben) als Eigenschaft für einen Entitätstyp zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1256e-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="1256e-121">Die folgende CSDL deklariert die `Address`-Eigenschaft als komplexen Typ für einen Entitätstyp (Publisher):</span><span class="sxs-lookup"><span data-stu-id="1256e-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="1256e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1256e-122">See Also</span></span>  
 [<span data-ttu-id="1256e-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1256e-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="1256e-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="1256e-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
