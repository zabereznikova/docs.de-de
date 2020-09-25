---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 1c03cca80de6003a4e49278871983ed7fcb3dc0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200666"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="6bc53-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="6bc53-102">LINQ to DataSet</span></span>

<span data-ttu-id="6bc53-103">Mit LINQ to DataSet wird die Abfrage von Daten, die in einem-Objekt zwischengespeichert sind, vereinfacht <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="6bc53-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="6bc53-104">Insbesondere LINQ to DataSet die Abfrage vereinfacht, indem Sie Entwicklern das Schreiben von Abfragen aus der Programmiersprache selbst ermöglichen, anstatt eine separate Abfragesprache zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bc53-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="6bc53-105">Dies ist besonders nützlich für Visual Studio-Entwickler, die nun die Syntax Überprüfung zur Kompilierzeit, statische Typisierung und IntelliSense-Unterstützung nutzen können, die von Visual Studio in Ihren Abfragen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6bc53-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="6bc53-106">LINQ to DataSet können auch verwendet werden, um Daten abzufragen, die aus einer oder mehreren Datenquellen konsolidiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6bc53-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="6bc53-107">Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="6bc53-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="6bc53-108">Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="6bc53-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="6bc53-109">Die LINQ to DataSet-Funktion wird primär durch die Erweiterungs Methoden in den <xref:System.Data.DataRowExtensions> Klassen und verfügbar gemacht <xref:System.Data.DataTableExtensions> .</span><span class="sxs-lookup"><span data-stu-id="6bc53-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="6bc53-110">LINQ to DataSet baut auf auf und verwendet die vorhandene ADO.NET-Architektur und ist nicht dazu gedacht, ADO.net im Anwendungscode zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6bc53-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="6bc53-111">Vorhandener ADO.NET-Code funktioniert weiterhin in einer LINQ to DataSet Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6bc53-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="6bc53-112">Die Beziehung von LINQ to DataSet zu ADO.net und dem Datenspeicher wird im folgenden Diagramm veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6bc53-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Diagramm, das anzeigt, dass LINQ to DataSet auf dem ADO.NET-Anbieter basiert.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="6bc53-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6bc53-114">In This Section</span></span>  

 [<span data-ttu-id="6bc53-115">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="6bc53-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="6bc53-116">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6bc53-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="6bc53-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="6bc53-117">Reference</span></span>  

 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="6bc53-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bc53-118">See also</span></span>

- [<span data-ttu-id="6bc53-119">Language Integrated Query (LINQ) – C#</span><span class="sxs-lookup"><span data-stu-id="6bc53-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6bc53-120">Language Integrated Query (LINQ) – Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6bc53-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="6bc53-121">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6bc53-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="6bc53-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6bc53-122">ADO.NET</span></span>](index.md)
