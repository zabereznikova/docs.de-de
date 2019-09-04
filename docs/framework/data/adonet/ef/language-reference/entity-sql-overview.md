---
title: Übersicht über Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 4d7db9c6a7aaeef900132663a5b0aa7420afe668
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251072"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="294da-102">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="294da-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="294da-103">ist eine SQL-ähnliche Sprache, die die Abfrage von konzeptionellen Modellen in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="294da-103">is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="294da-104">Konzeptionelle Modelle stellen Daten als Entitäten und Beziehungen dar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] und ermöglichen es Ihnen, diese Entitäten und Beziehungen in einem Format abzufragen, das den Benutzern, die SQL verwendet haben, vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="294da-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="294da-105">Das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="294da-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="294da-106">Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="294da-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="294da-107">Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen.</span><span class="sxs-lookup"><span data-stu-id="294da-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="294da-108">Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="294da-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="294da-109">Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="294da-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="294da-110">Neben dem EntityClient-Anbieter ermöglicht [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] die Verwendung von [!INCLUDE[esql](../../../../../../includes/esql-md.md)], um Abfragen für ein konzeptionelles Modell auszuführen und Daten als stark typisierte CLR-Objekte zurückzugeben, die Instanzen von Entitätstypen sind.</span><span class="sxs-lookup"><span data-stu-id="294da-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="294da-111">Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="294da-111">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="294da-112">In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="294da-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="294da-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="294da-113">In This Section</span></span>  
 [<span data-ttu-id="294da-114">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="294da-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="294da-115">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="294da-115">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="294da-116">Typsystem</span><span class="sxs-lookup"><span data-stu-id="294da-116">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="294da-117">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="294da-117">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="294da-118">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="294da-118">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="294da-119">Zwischenspeichern von Abfrageplänen</span><span class="sxs-lookup"><span data-stu-id="294da-119">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="294da-120">Namespaces</span><span class="sxs-lookup"><span data-stu-id="294da-120">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="294da-121">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="294da-121">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="294da-122">Parameter</span><span class="sxs-lookup"><span data-stu-id="294da-122">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="294da-123">Variablen</span><span class="sxs-lookup"><span data-stu-id="294da-123">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="294da-124">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="294da-124">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="294da-125">Literale</span><span class="sxs-lookup"><span data-stu-id="294da-125">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="294da-126">NULL-Literale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="294da-126">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="294da-127">Eingabezeichensatz</span><span class="sxs-lookup"><span data-stu-id="294da-127">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="294da-128">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="294da-128">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="294da-129">Funktionen</span><span class="sxs-lookup"><span data-stu-id="294da-129">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="294da-130">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="294da-130">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="294da-131">Paging</span><span class="sxs-lookup"><span data-stu-id="294da-131">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="294da-132">Vergleichssemantik</span><span class="sxs-lookup"><span data-stu-id="294da-132">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="294da-133">Zusammenstellen verschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="294da-133">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="294da-134">Strukturierte Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="294da-134">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="294da-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="294da-135">See also</span></span>

- [<span data-ttu-id="294da-136">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="294da-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="294da-137">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="294da-137">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="294da-138">CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)</span><span class="sxs-lookup"><span data-stu-id="294da-138">CSDL, SSDL, and MSL Specifications</span></span>](csdl-ssdl-and-msl-specifications.md)
