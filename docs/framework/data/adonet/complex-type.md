---
title: Komplexer Typ
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: ef20de6a9e72d3123d745ef5501ecdb7fa63967d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203786"
---
# <a name="complex-type"></a><span data-ttu-id="902bc-102">Komplexer Typ</span><span class="sxs-lookup"><span data-stu-id="902bc-102">complex type</span></span>

<span data-ttu-id="902bc-103">Ein *komplexer Typ* ist eine Vorlage zum Definieren von umfangreichen, strukturierten Eigenschaften für [Entitäts Typen](entity-type.md) oder für andere komplexe Typen.</span><span class="sxs-lookup"><span data-stu-id="902bc-103">A *complex type* is a template for defining rich, structured properties on [entity types](entity-type.md) or on other complex types.</span></span> <span data-ttu-id="902bc-104">Jede Vorlage enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="902bc-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="902bc-105">Eine eindeutige Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="902bc-105">A unique name.</span></span> <span data-ttu-id="902bc-106">(Erforderlich)</span><span class="sxs-lookup"><span data-stu-id="902bc-106">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="902bc-107">Der Name eines komplexen Typs darf nicht mit dem Namen eines Entitätstyps innerhalb des gleichen Namespace übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="902bc-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="902bc-108">Daten in Form von einer oder mehreren [Eigenschaften](property.md).</span><span class="sxs-lookup"><span data-stu-id="902bc-108">Data in the form of one or more [properties](property.md).</span></span> <span data-ttu-id="902bc-109">(Optional.)</span><span class="sxs-lookup"><span data-stu-id="902bc-109">(Optional.)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="902bc-110">Eine Eigenschaft eines komplexen Typs kann ein anderer komplexer Typ sein.</span><span class="sxs-lookup"><span data-stu-id="902bc-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="902bc-111">Ein komplexer Typ ähnelt insofern einem Entitätstyp, als ein komplexer Typ eine Datennutzlast in Form von primitiven Typeigenschaften oder anderen komplexen Typen enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="902bc-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="902bc-112">Es gibt jedoch einige Hauptunterschiede zwischen komplexen Typen und Entitätstypen:</span><span class="sxs-lookup"><span data-stu-id="902bc-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="902bc-113">Komplexe Typen weisen keine Identitäten auf und können daher nicht unabhängig sein.</span><span class="sxs-lookup"><span data-stu-id="902bc-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="902bc-114">Komplexe Typen können nur Eigenschaften von Entitätstypen oder anderen komplexen Typen sein.</span><span class="sxs-lookup"><span data-stu-id="902bc-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="902bc-115">Komplexe Typen können nicht an [Zuordnungen](association-type.md)teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="902bc-115">Complex types cannot participate in [associations](association-type.md).</span></span> <span data-ttu-id="902bc-116">Keines der Enden einer Zuordnung kann ein komplexer Typ sein, daher können [Navigations Eigenschaften](navigation-property.md) nicht für komplexe Typen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="902bc-116">Neither end of an association can be a complex type, and therefore [navigation properties](navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="902bc-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="902bc-117">Example</span></span>  

 <span data-ttu-id="902bc-118">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="902bc-118">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="902bc-119">Die folgende CSDL definiert einen komplexen Typ, Adress, mit den primitiven Typeigenschaften `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="902bc-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="902bc-120">Deklarieren Sie den Eigenschaftentyp in der Entitätstypdefinition, um den komplexen Typ `Address` (oben) als Eigenschaft für einen Entitätstyp zu definieren.</span><span class="sxs-lookup"><span data-stu-id="902bc-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="902bc-121">Die folgende CSDL deklariert die `Address`-Eigenschaft als komplexen Typ für einen Entitätstyp (Publisher):</span><span class="sxs-lookup"><span data-stu-id="902bc-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="902bc-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="902bc-122">See also</span></span>

- [<span data-ttu-id="902bc-123">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="902bc-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="902bc-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="902bc-124">Entity Data Model</span></span>](entity-data-model.md)
