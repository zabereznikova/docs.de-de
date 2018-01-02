---
title: LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 75ab1e733915349c64742e1a9c1142cad988ade0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-dataset"></a><span data-ttu-id="dd5ef-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="dd5ef-102">LINQ to DataSet</span></span>
<span data-ttu-id="dd5ef-103">Mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] können Daten, die in einem <xref:System.Data.DataSet>-Objekt zwischengespeichert sind, leichter und schneller abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-103">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="dd5ef-104">Insbesondere [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] vereinfacht, da der Entwickler Schreiben von Abfragen in der Programmiersprache selbst, anstatt eine separate Abfragesprache mit Abfragen.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="dd5ef-105">Dies ist besonders nützlich für [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] jetzt die syntaxüberprüfung der Zeitpunkt der Kompilierung, statische Typisierung und IntelliSense-Unterstützung durch nutzen können Entwickler die [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] in seinen Abfragen.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-105">This is especially useful for [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="dd5ef-106"> kann auch für das Abfragen von Daten verwendet werden, die aus einer oder mehreren Datenquellen konsolidiert wurden.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-106"> can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="dd5ef-107">Dies ermöglicht eine Vielzahl von Szenarios, bei denen Flexibilität bei der Darstellung und Behandlung von Daten erforderlich ist, wie das Abfragen lokal aggregierter Daten und die Zwischenspeicherung auf der mittleren Ebene bei Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="dd5ef-108">Diese Manipulationsmethode wird insbesondere bei der Erstellung von Berichterstellungs-, Analyse- und Business Intelligence-Anwendungen benötigt.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="dd5ef-109">Die [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Funktionalität wird bereitgestellt, in erster Linie durch die Erweiterungsmethoden in den <xref:System.Data.DataRowExtensions> und <xref:System.Data.DataTableExtensions> Klassen.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="dd5ef-110">baut auf und verwendet die vorhandene [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] -Architektur und ist nicht vorgesehen, ersetzen Sie [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] im Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-110"> builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="dd5ef-111">Der vorhandene ADO.NET 2.0-Code funktioniert auch in einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="dd5ef-112">Die Beziehung zwischen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] und [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] und dem Datenspeicher wird im folgenden Diagramm illustriert.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 <span data-ttu-id="dd5ef-113">![LINQ to DataSet basiert auf dem ADO.NET-Anbieter](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span><span class="sxs-lookup"><span data-stu-id="dd5ef-113">![LINQ to DataSet is based on the ADO.NET Provider](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd5ef-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd5ef-114">In This Section</span></span>  
 [<span data-ttu-id="dd5ef-115">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd5ef-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="dd5ef-116">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dd5ef-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="dd5ef-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="dd5ef-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="dd5ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd5ef-118">See Also</span></span>  
 [<span data-ttu-id="dd5ef-119">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="dd5ef-119">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="dd5ef-120">LINQ und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dd5ef-120">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="dd5ef-121">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dd5ef-121">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
