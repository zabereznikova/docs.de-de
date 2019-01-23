---
title: Entity SQL-Sprache
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 0c698f04c3b95ffb204a20d41e91ef3f6210c5d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494096"
---
# <a name="entity-sql-language"></a><span data-ttu-id="7597e-102">Entity SQL-Sprache</span><span class="sxs-lookup"><span data-stu-id="7597e-102">Entity SQL Language</span></span>
<span data-ttu-id="7597e-103">Entity SQL ist eine speicherunabhängige Abfragesprache, die SQL ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="7597e-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="7597e-104">Mit Entity SQL können Sie Entitätsdaten als Objekte oder in einem Tabellenformular abfragen.</span><span class="sxs-lookup"><span data-stu-id="7597e-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="7597e-105">In den folgenden Fällen empfiehlt sich die Verwendung von Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="7597e-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="7597e-106">Eine Abfrage muss dynamisch zur Laufzeit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7597e-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="7597e-107">In diesem Fall sollten Sie ebenfalls erwägen, die Abfrage-Generator-Methoden von <xref:System.Data.Objects.ObjectQuery%601> zu verwenden, statt zur Laufzeit eine Entity SQL-Abfragezeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7597e-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="7597e-108">Eine Abfrage soll als Teil der Modelldefinition definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7597e-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="7597e-109">In einem Datenmodell wird nur Entity SQL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7597e-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="7597e-110">Weitere Informationen finden Sie unter [QueryView-Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="7597e-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="7597e-111">EntityClient wird zur Rückgabe von schreibgeschützten Entitätsdaten als Rowsets mithilfe von <xref:System.Data.EntityClient.EntityDataReader> verwendet.</span><span class="sxs-lookup"><span data-stu-id="7597e-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="7597e-112">Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="7597e-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="7597e-113">Wenn Sie Experte für SQL-basierte Abfragesprachen sind, sind Sie mit Entity SQL möglicherweise bereits vertraut.</span><span class="sxs-lookup"><span data-stu-id="7597e-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="7597e-114">Verwenden von Entity SQL mit dem EntityClient-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7597e-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="7597e-115">Weitere Informationen zum Verwenden von Entity SQL mit dem EntityClient-Anbieter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="7597e-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="7597e-116">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7597e-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="7597e-117">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7597e-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="7597e-118">Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="7597e-119">Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="7597e-120">Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="7597e-121">Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="7597e-122">Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="7597e-123">Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von EntityCommand</span><span class="sxs-lookup"><span data-stu-id="7597e-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="7597e-124">Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand</span><span class="sxs-lookup"><span data-stu-id="7597e-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="7597e-125">Vorgehensweise: Ausführen einer polymorphen Abfrage</span><span class="sxs-lookup"><span data-stu-id="7597e-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="7597e-126">Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator</span><span class="sxs-lookup"><span data-stu-id="7597e-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="7597e-127">Verwenden von Entity SQL mit Objektabfragen</span><span class="sxs-lookup"><span data-stu-id="7597e-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="7597e-128">Weitere Informationen zum Verwenden von Entity SQL mit Objektabfragen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="7597e-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="7597e-129">Vorgehensweise: Ausführen einer Abfrage, die Entitätstypobjekte zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="7597e-130">Vorgehensweise: Ausführen einer parametrisierten Abfrage</span><span class="sxs-lookup"><span data-stu-id="7597e-130">How to: Execute a Parameterized Query</span></span>](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="7597e-131">Vorgehensweise: Navigieren Sie in Beziehungen mithilfe von Navigationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="7597e-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="7597e-132">Vorgehensweise: Aufrufen einer benutzerdefinierten Funktion</span><span class="sxs-lookup"><span data-stu-id="7597e-132">How to: Call a User-Defined Function</span></span>](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="7597e-133">Vorgehensweise: Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="7597e-133">How to: Filter Data</span></span>](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="7597e-134">Vorgehensweise: Sortieren von Daten</span><span class="sxs-lookup"><span data-stu-id="7597e-134">How to: Sort Data</span></span>](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="7597e-135">Vorgehensweise: Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="7597e-135">How to: Group Data</span></span>](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="7597e-136">Vorgehensweise: Aggregieren von Daten</span><span class="sxs-lookup"><span data-stu-id="7597e-136">How to: Aggregate Data</span></span>](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="7597e-137">Vorgehensweise: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="7597e-138">Vorgehensweise: Ausführen einer Abfrage, die eine Auflistung von primitiven Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7597e-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="7597e-139">Vorgehensweise: Fragen Sie verbundener Objekte in einer "EntityCollection ab"</span><span class="sxs-lookup"><span data-stu-id="7597e-139">How to: Query Related Objects in an EntityCollection</span></span>](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="7597e-140">Vorgehensweise: Reihenfolge der Union von zwei Abfragen</span><span class="sxs-lookup"><span data-stu-id="7597e-140">How to: Order the Union of Two Queries</span></span>](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="7597e-141">Vorgehensweise: Seitenweise Abfrageresultate durch Navigieren</span><span class="sxs-lookup"><span data-stu-id="7597e-141">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="7597e-142">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7597e-142">In This Section</span></span>  
 [<span data-ttu-id="7597e-143">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7597e-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="7597e-144">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="7597e-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="7597e-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7597e-145">See also</span></span>
- [<span data-ttu-id="7597e-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7597e-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="7597e-147">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7597e-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
