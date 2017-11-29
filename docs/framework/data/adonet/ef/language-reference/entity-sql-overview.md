---
title: "Übersicht über Entity SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 301a934cad59b14d1a65a1e98247490d578e6866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-overview"></a><span data-ttu-id="d62d7-102">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d62d7-102">Entity SQL Overview</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="d62d7-103"> ist eine SQL-ähnliche Sprache, die die Abfrage von konzeptionellen Modellen in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d62d7-103"> is a SQL-like language that enables you to query conceptual models in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="d62d7-104">Konzeptionelle Modelle stellen Daten als Entitäten und Beziehungen dar und [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können Sie Abfragen, die Entitäten und Beziehungen in einem Format, das die vertraut sind, die SQL verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="d62d7-104">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  
  
 <span data-ttu-id="d62d7-105">Das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="d62d7-105">The [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="d62d7-106">Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d62d7-106">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="d62d7-107">Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d62d7-107">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d62d7-108">Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d62d7-108">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="d62d7-109">Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="d62d7-109">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="d62d7-110">Neben dem EntityClient-Anbieter ermöglicht [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] die Verwendung von [!INCLUDE[esql](../../../../../../includes/esql-md.md)], um Abfragen für ein konzeptionelles Modell auszuführen und Daten als stark typisierte CLR-Objekte zurückzugeben, die Instanzen von Entitätstypen sind.</span><span class="sxs-lookup"><span data-stu-id="d62d7-110">In addition to the EntityClient provider, the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly-typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="d62d7-111">Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="d62d7-111">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="d62d7-112">In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d62d7-112">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d62d7-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d62d7-113">In This Section</span></span>  
 [<span data-ttu-id="d62d7-114">Unterschiede zwischen Entity SQL und Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d62d7-114">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="d62d7-115">Entity SQL-Kurzreferenz</span><span class="sxs-lookup"><span data-stu-id="d62d7-115">Entity SQL Quick Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="d62d7-116">Typsystem</span><span class="sxs-lookup"><span data-stu-id="d62d7-116">Type System</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-117">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="d62d7-117">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-118">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="d62d7-118">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-119">Zwischenspeichern von Abfrageplänen</span><span class="sxs-lookup"><span data-stu-id="d62d7-119">Query Plan Caching</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-120">Namespaces</span><span class="sxs-lookup"><span data-stu-id="d62d7-120">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-121">Identifiers (Bezeichner)</span><span class="sxs-lookup"><span data-stu-id="d62d7-121">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-122">Parameter</span><span class="sxs-lookup"><span data-stu-id="d62d7-122">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-123">Variablen</span><span class="sxs-lookup"><span data-stu-id="d62d7-123">Variables</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-124">Nicht unterstützte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d62d7-124">Unsupported Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-125">Literale</span><span class="sxs-lookup"><span data-stu-id="d62d7-125">Literals</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-126">NULL-Literale und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="d62d7-126">Null Literals and Type Inference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-127">Eingabezeichensatz</span><span class="sxs-lookup"><span data-stu-id="d62d7-127">Input Character Set</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-128">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="d62d7-128">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-129">Funktionen</span><span class="sxs-lookup"><span data-stu-id="d62d7-129">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-130">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="d62d7-130">Operator Precedence</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-131">Paging</span><span class="sxs-lookup"><span data-stu-id="d62d7-131">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-132">Vergleichssemantik</span><span class="sxs-lookup"><span data-stu-id="d62d7-132">Comparison Semantics</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="d62d7-133">Erstellen geschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="d62d7-133">Composing Nested Entity SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="d62d7-134">Strukturierte Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="d62d7-134">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="d62d7-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d62d7-135">See Also</span></span>  
 [<span data-ttu-id="d62d7-136">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d62d7-136">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="d62d7-137">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="d62d7-137">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="d62d7-138">CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)</span><span class="sxs-lookup"><span data-stu-id="d62d7-138">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
