---
title: Programmierhandbuch (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 0c6b026d86a898aa52d93833ac3e447d6f6cba11
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513369"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="bdb7d-102">Programmierhandbuch (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="bdb7d-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="bdb7d-103">Dieser Abschnitt enthält grundlegende Informationen und Beispiele zum Programmieren mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdb7d-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdb7d-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bdb7d-104">In This Section</span></span>  
 [<span data-ttu-id="bdb7d-105">Abfragen in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="bdb7d-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-106">Enthält Informationen zur Vorgehensweise beim Schreiben von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="bdb7d-107">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="bdb7d-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-108">Beschreibt die Vorgehensweise beim Abfragen von <xref:System.Data.DataSet>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="bdb7d-109">Vergleichen von DataRows</span><span class="sxs-lookup"><span data-stu-id="bdb7d-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-110">Beschreibt die Vorgehensweise bei der Verwendung des <xref:System.Data.DataRowComparer>-Objekts zum Vergleichen von Datenzeilen.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="bdb7d-111">Erstellen einer DataTable aus einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="bdb7d-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-112">Enthält Informationen zum Erstellen einer <xref:System.Data.DataTable> aus einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage mithilfe der <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="bdb7d-113">Vorgehensweise: Implementieren von CopyToDataTable\<T >, in dem der generische Typ T ist kein DataRow</span><span class="sxs-lookup"><span data-stu-id="bdb7d-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="bdb7d-114">Beschreibt die Implementierung einer benutzerdefinierten `CopyToDataTable<T>`-Methode, wobei der generische Parameter T nicht den Typ <xref:System.Data.DataRow> aufweist.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="bdb7d-115">Generische Field- und SetField-Methoden</span><span class="sxs-lookup"><span data-stu-id="bdb7d-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-116">Enthält Informationen zu den generischen Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="bdb7d-117">Datenbindung und LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="bdb7d-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-118">Beschreibt die Datenbindung mit dem <xref:System.Data.DataView>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="bdb7d-119">Debuggen von LINQ to DataSet-Abfragen</span><span class="sxs-lookup"><span data-stu-id="bdb7d-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="bdb7d-120">Enthält Informationen zu debuggen und Problembehandlung [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="bdb7d-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bdb7d-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="bdb7d-122">Beschreibt Sicherheitsprobleme in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdb7d-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="bdb7d-123">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="bdb7d-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="bdb7d-124">Enthält Abfragebeispiele, in denen die [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-Operatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bdb7d-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bdb7d-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="bdb7d-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="bdb7d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdb7d-126">See also</span></span>

- [<span data-ttu-id="bdb7d-127">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bdb7d-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)  
- [<span data-ttu-id="bdb7d-128">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="bdb7d-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
