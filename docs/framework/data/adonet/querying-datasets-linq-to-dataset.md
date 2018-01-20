---
title: Abfragen von DataSets (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 21c4b2a37dfc9a7c570b39fa164267f90fa7055d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="ad53d-102">Abfragen von DataSets (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ad53d-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="ad53d-103">Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="ad53d-104">Das Formulieren von Abfragen mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ähnelt der Verwendung von [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] zur Abfrage anderer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-fähiger Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-104">Formulating queries with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="ad53d-105">Bedenken Sie jedoch, die bei der Verwendung [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen im Verlauf einer <xref:System.Data.DataSet> eine Enumeration des abgefragten Objekts <xref:System.Data.DataRow> Objekte, statt einer Enumeration eines benutzerdefinierten Typs.</span><span class="sxs-lookup"><span data-stu-id="ad53d-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="ad53d-106">Dies bedeutet, dass Sie eines der Elemente verwenden können die <xref:System.Data.DataRow> -Klasse in Ihrem [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="ad53d-107">Auf diese Weise lassen sich umfangreiche und komplexe Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="ad53d-108">Wie bei anderen Implementierungen von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], Sie können erstellen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen in zwei verschiedenen Formen: Abfrageausdruckssyntax und mit methodenbasierter Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="ad53d-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="ad53d-109">Weitere Informationen zu diesen beiden Formen finden Sie unter [erste Schritte mit LINQ](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span><span class="sxs-lookup"><span data-stu-id="ad53d-109">For more information about these two forms, see [Getting Started with LINQ](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).</span></span> <span data-ttu-id="ad53d-110">Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-110">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad53d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ad53d-111">In This Section</span></span>  
 [<span data-ttu-id="ad53d-112">Abfragen für einzelne Tabellen</span><span class="sxs-lookup"><span data-stu-id="ad53d-112">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="ad53d-113">Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ad53d-113">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="ad53d-114">Tabellenübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="ad53d-114">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="ad53d-115">Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.</span><span class="sxs-lookup"><span data-stu-id="ad53d-115">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="ad53d-116">Abfragen von typisierten DataSets</span><span class="sxs-lookup"><span data-stu-id="ad53d-116">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 <span data-ttu-id="ad53d-117">Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="ad53d-117">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad53d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad53d-118">See Also</span></span>  
 [<span data-ttu-id="ad53d-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ad53d-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="ad53d-120">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="ad53d-120">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
