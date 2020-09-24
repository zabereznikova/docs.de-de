---
title: Programmierhandbuch (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 720d9a90583a0dcf3453689a362f6043157a326c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161558"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="587cf-102">Programmierhandbuch (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="587cf-102">Programming Guide (LINQ to DataSet)</span></span>

<span data-ttu-id="587cf-103">Dieser Abschnitt enthält konzeptionelle Informationen und Beispiele für die Programmierung mit LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="587cf-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="587cf-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="587cf-104">In This Section</span></span>  

 [<span data-ttu-id="587cf-105">Abfragen in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="587cf-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="587cf-106">Enthält Informationen zum Schreiben von LINQ to DataSet-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="587cf-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="587cf-107">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="587cf-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="587cf-108">Beschreibt die Vorgehensweise beim Abfragen von <xref:System.Data.DataSet>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="587cf-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="587cf-109">Vergleichen von DataRows</span><span class="sxs-lookup"><span data-stu-id="587cf-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="587cf-110">Beschreibt die Vorgehensweise bei der Verwendung des <xref:System.Data.DataRowComparer>-Objekts zum Vergleichen von Datenzeilen.</span><span class="sxs-lookup"><span data-stu-id="587cf-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="587cf-111">Erstellen einer DataTable aus einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="587cf-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="587cf-112">Stellt Informationen zum Erstellen einer <xref:System.Data.DataTable> aus einer LINQ to DataSet Abfrage mithilfe der- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="587cf-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="587cf-113">Gewusst wie: Implementieren von "copydedatable", \<T> wobei der generische Typ "T" keine "DataRow" ist</span><span class="sxs-lookup"><span data-stu-id="587cf-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="587cf-114">Beschreibt die Implementierung einer benutzerdefinierten `CopyToDataTable<T>`-Methode, wobei der generische Parameter T nicht den Typ <xref:System.Data.DataRow> aufweist.</span><span class="sxs-lookup"><span data-stu-id="587cf-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="587cf-115">Generische Field- und SetField-Methoden</span><span class="sxs-lookup"><span data-stu-id="587cf-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="587cf-116">Enthält Informationen zu den generischen Methoden <xref:System.Data.DataRowExtensions.Field%2A> und <xref:System.Data.DataRowExtensions.SetField%2A>.</span><span class="sxs-lookup"><span data-stu-id="587cf-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="587cf-117">Datenbindung und LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="587cf-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="587cf-118">Beschreibt die Datenbindung mit dem <xref:System.Data.DataView>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="587cf-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="587cf-119">Debuggen von LINQ to DataSet-Abfragen</span><span class="sxs-lookup"><span data-stu-id="587cf-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="587cf-120">Enthält Informationen zum Debuggen und zur Problembehandlung LINQ to DataSet Abfragen.</span><span class="sxs-lookup"><span data-stu-id="587cf-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="587cf-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="587cf-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="587cf-122">Beschreibt Sicherheitsprobleme in LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="587cf-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="587cf-123">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="587cf-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="587cf-124">Enthält Abfragebeispiele, in denen die LINQ-Operatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="587cf-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="587cf-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="587cf-125">Reference</span></span>  

 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="587cf-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="587cf-126">See also</span></span>

- [<span data-ttu-id="587cf-127">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="587cf-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="587cf-128">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="587cf-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
