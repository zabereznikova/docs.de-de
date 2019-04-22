---
title: Typdefinitionen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 2e068db0ce202c26cad36c8ed7adf0acdfb8e363
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096022"
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="c9a15-102">Typdefinitionen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c9a15-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="c9a15-103">Eine Typdefinition wird in der Deklarationsanweisung einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Inlinefunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9a15-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a15-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9a15-104">Remarks</span></span>  
 <span data-ttu-id="c9a15-105">Die deklarationsanweisung für eine Inlinefunktion besteht aus den [Funktion](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) Schlüsselwort, gefolgt von der Bezeichner, die den Funktionsnamen (z. B. "MyAvg"), gefolgt von der Parameterdefinitionsliste in Klammern (für darstellt. beispielsweise "gebührenauflistung (Decimal).</span><span class="sxs-lookup"><span data-stu-id="c9a15-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="c9a15-106">Die Parameterdefinitionsliste besteht aus 0 (null) oder mehreren Parameterdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c9a15-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="c9a15-107">Jede Parameterdefinition besteht aus einem von einer Typdefinition (z. B. "Auflistung (Decimal)") gefolgten Bezeichner (der Name des Parameters der Funktion, z. B. "Gebühren").</span><span class="sxs-lookup"><span data-stu-id="c9a15-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="c9a15-108">Dies sind die zulässigen Typdefinitionen:</span><span class="sxs-lookup"><span data-stu-id="c9a15-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="c9a15-109">Der Typ des Bezeichners (z. B. "Int32" oder "AdventureWorks.Order").</span><span class="sxs-lookup"><span data-stu-id="c9a15-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="c9a15-110">Das `COLLECTION`-Schlüsselwort, das von einer anderen Typdefinition in Klammern gefolgt wird (z. B. "Collection(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="c9a15-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="c9a15-111">Das von einer Liste von Eigenschaftendefinitionen in Klammern (z. B. "Row(x AdventureWorks.Order))" gefolgte ROW-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c9a15-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="c9a15-112">Eigenschaftendefinitionen besitzen Formate wie z. B. "`identifier type_definition`, `identifier type_definition`,...".</span><span class="sxs-lookup"><span data-stu-id="c9a15-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="c9a15-113">Das vom Typ des Bezeichners in Klammern (z. B. "Ref(AdventureWorks.Order)") gefolgte REF-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c9a15-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="c9a15-114">Der REF-Typdefinitionsoperator erfordert einen Entitätstyp als Argument.</span><span class="sxs-lookup"><span data-stu-id="c9a15-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="c9a15-115">Sie können keinen primitiven Typ als Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="c9a15-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="c9a15-116">Sie können Typdefinitionen auch schachteln (z. B., "Collection(Row(x Ref(AdventureWorks.Order)))").</span><span class="sxs-lookup"><span data-stu-id="c9a15-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="c9a15-117">Die Typdefinitionsoptionen lauten folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="c9a15-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="c9a15-118">`IdentifierName supported_type`, oder</span><span class="sxs-lookup"><span data-stu-id="c9a15-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="c9a15-119">`IdentifierName` COLLECTION(`type_definition`) oder</span><span class="sxs-lookup"><span data-stu-id="c9a15-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="c9a15-120">`IdentifierName` ROW(`property_definition`) oder</span><span class="sxs-lookup"><span data-stu-id="c9a15-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="c9a15-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="c9a15-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="c9a15-122">Die Eigenschaftendefinitionsoption ist `IdentifierName type_definition`.</span><span class="sxs-lookup"><span data-stu-id="c9a15-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="c9a15-123">Unterstützte Typen sind alle Typen im aktuellen Namespace.</span><span class="sxs-lookup"><span data-stu-id="c9a15-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="c9a15-124">Diese schließen sowohl primitive Typen als auch Entitätstypen ein.</span><span class="sxs-lookup"><span data-stu-id="c9a15-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="c9a15-125">Unterstützte Entitätstypen verweisen im aktuellen Namespace nur auf Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="c9a15-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="c9a15-126">Sie schließen keine primitiven Typen ein.</span><span class="sxs-lookup"><span data-stu-id="c9a15-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c9a15-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c9a15-127">Examples</span></span>  
 <span data-ttu-id="c9a15-128">Im folgenden Beispiel wird eine einfache Typdefinition dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c9a15-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="c9a15-129">Dies ist ein Beispiel für eine COLLECTION-Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="c9a15-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="c9a15-130">Dies ist ein Beispiel für eine ROW-Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="c9a15-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="c9a15-131">Dies ist ein Beispiel für eine REF-Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="c9a15-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9a15-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9a15-132">See also</span></span>

- [<span data-ttu-id="c9a15-133">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c9a15-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="c9a15-134">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="c9a15-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
