---
title: Übersicht über Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150375"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="57637-102">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="57637-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="57637-103">ist eine SQL-ähnliche Sprache, mit der Sie konzeptionelle Modelle im Entity Framework abfragen können.</span><span class="sxs-lookup"><span data-stu-id="57637-103">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="57637-104">Konzeptionelle Modelle stellen Daten als [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Entitäten und Beziehungen dar und ermöglichen es Ihnen, diese Entitäten und Beziehungen in einem Format abzufragen, das denjenigen vertraut ist, die SQL verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="57637-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  

 <span data-ttu-id="57637-105">Entity Framework arbeitet mit speicherspezifischen Datenanbietern [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zusammen, um generische Abfragen in speicherspezifische Abfragen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="57637-105">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="57637-106">Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="57637-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="57637-107">Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen.</span><span class="sxs-lookup"><span data-stu-id="57637-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="57637-108">Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="57637-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="57637-109">Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="57637-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="57637-110">Zusätzlich zum EntityClient-Anbieter können Sie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] mit Entity Framework Abfragen für ein konzeptionelles Modell ausführen und Daten als stark typisierte CLR-Objekte zurückgeben, die Instanzen von Entitätstypen sind.</span><span class="sxs-lookup"><span data-stu-id="57637-110">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="57637-111">Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="57637-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="57637-112">In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="57637-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57637-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="57637-113">In This Section</span></span>  
 [<span data-ttu-id="57637-114">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57637-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="57637-115">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="57637-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="57637-116">Typensystem</span><span class="sxs-lookup"><span data-stu-id="57637-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="57637-117">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="57637-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="57637-118">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="57637-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="57637-119">Zwischenspeichern von Abfrageplänen</span><span class="sxs-lookup"><span data-stu-id="57637-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="57637-120">Namespaces</span><span class="sxs-lookup"><span data-stu-id="57637-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="57637-121">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="57637-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="57637-122">Parameter</span><span class="sxs-lookup"><span data-stu-id="57637-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="57637-123">Variablen</span><span class="sxs-lookup"><span data-stu-id="57637-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="57637-124">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="57637-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="57637-125">Literale</span><span class="sxs-lookup"><span data-stu-id="57637-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="57637-126">NULL-Literale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="57637-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="57637-127">Eingabezeichensatz</span><span class="sxs-lookup"><span data-stu-id="57637-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="57637-128">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="57637-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="57637-129">Functions</span><span class="sxs-lookup"><span data-stu-id="57637-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="57637-130">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="57637-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="57637-131">Paging</span><span class="sxs-lookup"><span data-stu-id="57637-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="57637-132">Vergleichssemantik</span><span class="sxs-lookup"><span data-stu-id="57637-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="57637-133">Zusammenstellen verschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="57637-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="57637-134">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="57637-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="57637-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57637-135">See also</span></span>

- [<span data-ttu-id="57637-136">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="57637-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="57637-137">Entity SQL-Sprache</span><span class="sxs-lookup"><span data-stu-id="57637-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="57637-138">CSDL-, SSDL- und MSL-Spezifikationen</span><span class="sxs-lookup"><span data-stu-id="57637-138">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
