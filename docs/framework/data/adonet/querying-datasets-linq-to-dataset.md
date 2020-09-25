---
title: Abfragen von DataSets (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: f42cd792772a4e2b9f24ea8f76ea588da10d9c51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184975"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="e1d3c-102">Abfragen von DataSets (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e1d3c-102">Querying DataSets (LINQ to DataSet)</span></span>

<span data-ttu-id="e1d3c-103">Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="e1d3c-104">Das Formulieren von Abfragen mit LINQ to DataSet ähnelt der Verwendung von LINQ (Language-Integrated Query) mit anderen LINQ-fähigen Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-104">Formulating queries with LINQ to DataSet is similar to using Language-Integrated Query (LINQ) against other LINQ-enabled data sources.</span></span> <span data-ttu-id="e1d3c-105">Beachten Sie jedoch, dass Sie bei der Verwendung von LINQ-Abfragen für ein- <xref:System.Data.DataSet> Objekt eine Enumeration von- <xref:System.Data.DataRow> Objekten statt einer Enumeration eines benutzerdefinierten Typs Abfragen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-105">Remember, however, that when you use LINQ queries over a <xref:System.Data.DataSet> object, you're querying an enumeration of <xref:System.Data.DataRow> objects instead of an enumeration of a custom type.</span></span> <span data-ttu-id="e1d3c-106">Dies bedeutet, dass Sie alle Member der- <xref:System.Data.DataRow> Klasse in den LINQ-Abfragen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your LINQ queries.</span></span> <span data-ttu-id="e1d3c-107">Auf diese Weise können Sie umfangreiche, komplexe Abfragen erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-107">This lets you create rich, complex queries.</span></span>  
  
 <span data-ttu-id="e1d3c-108">Wie bei anderen Implementierungen von LINQ können Sie LINQ to DataSet Abfragen in zwei unterschiedlichen Formen erstellen: Abfrage Ausdruckssyntax und Methoden basierte Abfrage Syntax.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-108">As with other implementations of LINQ, you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="e1d3c-109">Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1d3c-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e1d3c-110">In This Section</span></span>  

 [<span data-ttu-id="e1d3c-111">Abfragen für einzelne Tabellen</span><span class="sxs-lookup"><span data-stu-id="e1d3c-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="e1d3c-112">Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="e1d3c-113">Tabellenübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="e1d3c-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="e1d3c-114">Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="e1d3c-115">Abfragen von typisierten DataSets</span><span class="sxs-lookup"><span data-stu-id="e1d3c-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="e1d3c-116">Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="e1d3c-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d3c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1d3c-117">See also</span></span>

- [<span data-ttu-id="e1d3c-118">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e1d3c-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="e1d3c-119">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="e1d3c-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
