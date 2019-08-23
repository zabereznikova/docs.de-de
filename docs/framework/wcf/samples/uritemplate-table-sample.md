---
title: Beispiel zur UriTemplate-Tabelle
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: 174c0035adb0b38ddb18f79f9cc4d76d3db46b74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962915"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="f563d-102">Beispiel zur UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="f563d-102">UriTemplate Table Sample</span></span>
<span data-ttu-id="f563d-103">Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von `UriTemplate`-Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="f563d-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="f563d-104">Bestimmte URIs (Uniform Resource Identifiers) können effizient mit allen Vorlagen in der Tabelle verglichen und die zur gefundenen Vorlage gehörenden Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f563d-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="f563d-105">Dieses Beispiel demonstriert die folgenden Grundbegriffe bezüglich der `UriTemplateTable`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="f563d-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="f563d-106">Die Syntax zum Instanziieren einer `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="f563d-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="f563d-107">Das Auffüllen einer `UriTemplateTable` mit einem Satz von Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="f563d-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="f563d-108">Das Vergleichen eines möglichen URI mit der Tabelle per <xref:System.UriTemplateTable.MatchSingle%2A>.</span><span class="sxs-lookup"><span data-stu-id="f563d-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f563d-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f563d-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f563d-110">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f563d-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="f563d-111">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f563d-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f563d-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f563d-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f563d-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f563d-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f563d-114">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f563d-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f563d-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f563d-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="f563d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f563d-116">See also</span></span>

- [<span data-ttu-id="f563d-117">UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="f563d-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="f563d-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="f563d-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
