---
title: Beispiel zur UriTemplate-Tabelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8d8b05bcb897cfb7371b1d5353b6fd0e7949b08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="dfc0e-102">Beispiel zur UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="dfc0e-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="dfc0e-103">Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von `UriTemplate`-Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="dfc0e-104">Bestimmte URIs (Uniform Resource Identifiers) können effizient mit allen Vorlagen in der Tabelle verglichen und die zur gefundenen Vorlage gehörenden Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="dfc0e-105">Dieses Beispiel demonstriert die folgenden Grundbegriffe bezüglich der `UriTemplateTable`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="dfc0e-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="dfc0e-106">Die Syntax zum Instanziieren einer `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="dfc0e-107">Das Auffüllen einer `UriTemplateTable` mit einem Satz von Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
-   <span data-ttu-id="dfc0e-108">Das Vergleichen eines möglichen URI mit der Tabelle per <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dfc0e-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="dfc0e-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dfc0e-110">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="dfc0e-111">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfc0e-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfc0e-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dfc0e-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfc0e-114">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfc0e-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dfc0e-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="dfc0e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfc0e-116">See Also</span></span>  
 [<span data-ttu-id="dfc0e-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="dfc0e-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)  
 [<span data-ttu-id="dfc0e-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="dfc0e-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
