---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: c4069ef760877935c4ce194144d131d0dc58b4d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504366"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="be84f-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="be84f-102">LINQ to DataSet</span></span>
<span data-ttu-id="be84f-103">LINQ to DataSet erleichtert Ihnen schneller zur Abfrage von Daten und zwischengespeichert, und einem <xref:System.Data.DataSet> Objekt.</span><span class="sxs-lookup"><span data-stu-id="be84f-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="be84f-104">Genauer gesagt, vereinfacht die LINQ to DataSet, Abfragen, da der Entwickler Schreiben von Abfragen von der Programmiersprache selbst, anstatt eine separate Abfragesprache mit.</span><span class="sxs-lookup"><span data-stu-id="be84f-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="be84f-105">Dies ist besonders nützlich für Visual Studio-Entwickler, die nun die syntaxüberprüfung für während der Kompilierung, statische Typisierung und IntelliSense-Unterstützung, die von der Visual Studio in ihren Abfragen bereitgestellten nutzen können.</span><span class="sxs-lookup"><span data-stu-id="be84f-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="be84f-106">LINQ to DataSet kann auch verwendet werden zur Abfrage von Daten, die aus einem oder mehreren Datenquellen konsolidiert wurden.</span><span class="sxs-lookup"><span data-stu-id="be84f-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="be84f-107">Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="be84f-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="be84f-108">Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="be84f-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="be84f-109">Die LINQ to DataSet-Funktionalität verfügbar gemacht wird, in erster Linie durch die Erweiterungsmethoden in den <xref:System.Data.DataRowExtensions> und <xref:System.Data.DataTableExtensions> Klassen.</span><span class="sxs-lookup"><span data-stu-id="be84f-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="be84f-110">LINQ to DataSet basiert auf und verwendet die vorhandene ADO.NET-Architektur und ist nicht zum Ersetzen von ADO.NET in Anwendungscode vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="be84f-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="be84f-111">Vorhandene ADO.NET-Code funktionieren weiterhin in einer LINQ to DataSet-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="be84f-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="be84f-112">Die Beziehung zwischen LINQ to DataSet zu ADO.NET und dem Datenspeicher wird im folgenden Diagramm veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be84f-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![Das Diagramm zeigt, dass LINQ to DataSet auf dem ADO.NET-Anbieter basiert.](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="be84f-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="be84f-114">In This Section</span></span>  
 [<span data-ttu-id="be84f-115">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="be84f-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="be84f-116">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="be84f-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="be84f-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="be84f-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="be84f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be84f-118">See also</span></span>

- [<span data-ttu-id="be84f-119">Language Integrated Query (LINQ) – C#</span><span class="sxs-lookup"><span data-stu-id="be84f-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="be84f-120">Language Integrated Query (LINQ) – Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be84f-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="be84f-121">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="be84f-121">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="be84f-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="be84f-122">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
