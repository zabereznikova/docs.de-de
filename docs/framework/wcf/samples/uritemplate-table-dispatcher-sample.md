---
title: Beispiel zum UriTemplate-Tabellenverteiler
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 57489264de62b6adbca1c98230a0f90735b3918a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294949"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="8b883-102">Beispiel zum UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="8b883-102">UriTemplate Table Dispatcher Sample</span></span>

<span data-ttu-id="8b883-103">Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von <xref:System.UriTemplate>-Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="8b883-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="8b883-104">Dieses Beispiel demonstriert eine grundlegende, mit `UriTemplateTable` erstellte Verteiler-Engine, ein allgemeines Verwendungsszenario für die `UriTemplateTable`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8b883-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="8b883-105">Dieses Beispiel demonstriert die folgenden Schlüsselkonzepte für die `UriTemplateTable`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="8b883-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="8b883-106">Das Zuordnen von Delegaten mit `UriTemplates` in einer `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="8b883-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="8b883-107">Das Verwenden <xref:System.UriTemplateTable.MatchSingle%2A>, um den richtigen Handlerdelegaten für einen bestimmten URI zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8b883-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="8b883-108">Das Aufrufen des Handlerdelegaten zum Verarbeiten der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8b883-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8b883-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="8b883-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8b883-110">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="8b883-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="8b883-111">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b883-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8b883-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8b883-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8b883-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8b883-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8b883-114">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8b883-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8b883-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8b883-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="8b883-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b883-116">See also</span></span>

- [<span data-ttu-id="8b883-117">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8b883-117">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="8b883-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8b883-118">UriTemplate</span></span>](uritemplate-sample.md)
