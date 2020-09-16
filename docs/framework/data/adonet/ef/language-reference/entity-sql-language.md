---
title: Entity SQL-Sprache
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 2600b7626ebc5196c702f2d1e3159fd9549227f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553381"
---
# <a name="entity-sql-language"></a><span data-ttu-id="fd5f8-102">Entity SQL-Sprache</span><span class="sxs-lookup"><span data-stu-id="fd5f8-102">Entity SQL Language</span></span>
<span data-ttu-id="fd5f8-103">Entity SQL ist eine speicherunabhängige Abfragesprache, die SQL ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="fd5f8-104">Mit Entity SQL können Sie Entitätsdaten als Objekte oder in einem Tabellenformular abfragen.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="fd5f8-105">In den folgenden Fällen empfiehlt sich die Verwendung von Entity SQL:</span><span class="sxs-lookup"><span data-stu-id="fd5f8-105">You should consider using Entity SQL in the following cases:</span></span>  
  
- <span data-ttu-id="fd5f8-106">Eine Abfrage muss dynamisch zur Laufzeit erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="fd5f8-107">In diesem Fall sollten Sie ebenfalls erwägen, die Abfrage-Generator-Methoden von <xref:System.Data.Objects.ObjectQuery%601> zu verwenden, statt zur Laufzeit eine Entity SQL-Abfragezeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
- <span data-ttu-id="fd5f8-108">Eine Abfrage soll als Teil der Modelldefinition definiert werden.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="fd5f8-109">In einem Datenmodell wird nur Entity SQL unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="fd5f8-110">Weitere Informationen finden Sie unter [QueryView-Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl) .</span><span class="sxs-lookup"><span data-stu-id="fd5f8-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
- <span data-ttu-id="fd5f8-111">EntityClient wird zur Rückgabe von schreibgeschützten Entitätsdaten als Rowsets mithilfe von <xref:System.Data.EntityClient.EntityDataReader> verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="fd5f8-112">Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="fd5f8-112">For more information, see [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).</span></span>  
  
- <span data-ttu-id="fd5f8-113">Wenn Sie Experte für SQL-basierte Abfragesprachen sind, sind Sie mit Entity SQL möglicherweise bereits vertraut.</span><span class="sxs-lookup"><span data-stu-id="fd5f8-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="fd5f8-114">Verwenden von Entity SQL mit dem EntityClient-Anbieter</span><span class="sxs-lookup"><span data-stu-id="fd5f8-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="fd5f8-115">Weitere Informationen zum Verwenden von Entity SQL mit dem EntityClient-Anbieter finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fd5f8-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="fd5f8-116">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fd5f8-116">EntityClient Provider for the Entity Framework</span></span>](../entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="fd5f8-117">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fd5f8-117">How to: Build an EntityConnection Connection String</span></span>](../how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="fd5f8-118">Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="fd5f8-119">Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="fd5f8-120">Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-120">How to: Execute a Query that Returns RefType Results</span></span>](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="fd5f8-121">Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-121">How to: Execute a Query that Returns Complex Types</span></span>](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="fd5f8-122">Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-122">How to: Execute a Query that Returns Nested Collections</span></span>](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="fd5f8-123">Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“</span><span class="sxs-lookup"><span data-stu-id="fd5f8-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="fd5f8-124">Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“</span><span class="sxs-lookup"><span data-stu-id="fd5f8-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="fd5f8-125">Vorgehensweise: Ausführen einer polymorphen Abfrage</span><span class="sxs-lookup"><span data-stu-id="fd5f8-125">How to: Execute a Polymorphic Query</span></span>](../how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="fd5f8-126">Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator</span><span class="sxs-lookup"><span data-stu-id="fd5f8-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="fd5f8-127">Verwenden von Entity SQL mit Objektabfragen</span><span class="sxs-lookup"><span data-stu-id="fd5f8-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="fd5f8-128">Weitere Informationen zum Verwenden von Entity SQL mit Objektabfragen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fd5f8-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="fd5f8-129">[Gewusst wie: Ausführen einer Abfrage, die Entitätstypobjekte zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-129">[How to: Execute a Query that Returns Entity Type Objects](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-130">[Gewusst wie: Ausführen einer parametrisierten Abfrage](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-130">[How to: Execute a Parameterized Query](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-131">[Gewusst wie: Navigieren von Beziehungen mithilfe von Navigationseigenschaften](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-131">[How to: Navigate Relationships Using Navigation Properties](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-132">[Gewusst wie: Aufrufen einer benutzerdefinierten Funktion](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-132">[How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-133">[Gewusst wie: Filtern von Daten](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-133">[How to: Filter Data](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-134">[Gewusst wie: Sortieren von Daten](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-134">[How to: Sort Data](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-135">[Gewusst wie: Gruppieren von Daten](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-135">[How to: Group Data](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-136">[Gewusst wie: Aggregieren von Daten](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-136">[How to: Aggregate Data](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-137">[Gewusst wie: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-137">[How to: Execute a Query that Returns Anonymous Type Objects](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-138">[Gewusst wie: Ausführen einer Abfrage, die eine Auflistung primitiver Typen zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-138">[How to: Execute a Query that Returns a Collection of Primitive Types](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-139">[Gewusst wie: Abfragen verbundener Objekte in einer "EntityCollection"](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-139">[How to: Query Related Objects in an EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-140">[Gewusst wie: Sortieren zweier mit dem Union-Befehl zusammengefasster Abfragen](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-140">[How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="fd5f8-141">[Gewusst wie: Seitenweise durch Abfrageresultate navigieren](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd5f8-141">[How to: Page Through Query Results](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd5f8-142">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fd5f8-142">In This Section</span></span>  
 [<span data-ttu-id="fd5f8-143">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fd5f8-143">Entity SQL Overview</span></span>](entity-sql-overview.md)  
  
 [<span data-ttu-id="fd5f8-144">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="fd5f8-144">Entity SQL Reference</span></span>](entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="fd5f8-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd5f8-145">See also</span></span>

- [<span data-ttu-id="fd5f8-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fd5f8-146">ADO.NET Entity Framework</span></span>](../index.md)
- [<span data-ttu-id="fd5f8-147">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fd5f8-147">Language Reference</span></span>](index.md)
