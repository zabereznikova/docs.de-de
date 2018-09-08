---
title: Beispiel zum UriTemplate-Tabellenverteiler
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 4a4f725e88e014da241e1042c27bfee270e13268
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187278"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="d5776-102">Beispiel zum UriTemplate-Tabellenverteiler</span><span class="sxs-lookup"><span data-stu-id="d5776-102">UriTemplate Table Dispatcher Sample</span></span>
<span data-ttu-id="d5776-103">Die <xref:System.UriTemplateTable>-Klasse stellt eine wörterbuchähnliche assoziative Tabellenstruktur zum Arbeiten mit einem Satz von <xref:System.UriTemplate>-Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="d5776-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="d5776-104">Dieses Beispiel demonstriert eine grundlegende, mit `UriTemplateTable` erstellte Verteiler-Engine, ein allgemeines Verwendungsszenario für die `UriTemplateTable`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d5776-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="d5776-105">Dieses Beispiel demonstriert die folgenden Schlüsselkonzepte für die `UriTemplateTable`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="d5776-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
-   <span data-ttu-id="d5776-106">Das Zuordnen von Delegaten mit `UriTemplates` in einer `UriTemplateTable`.</span><span class="sxs-lookup"><span data-stu-id="d5776-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
-   <span data-ttu-id="d5776-107">Das Verwenden <xref:System.UriTemplateTable.MatchSingle%2A>, um den richtigen Handlerdelegaten für einen bestimmten URI zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d5776-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
-   <span data-ttu-id="d5776-108">Das Aufrufen des Handlerdelegaten zum Verarbeiten der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d5776-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d5776-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d5776-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d5776-110">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d5776-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="d5776-111">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d5776-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5776-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d5776-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d5776-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d5776-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d5776-114">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d5776-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d5776-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5776-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="d5776-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5776-116">See Also</span></span>  
 [<span data-ttu-id="d5776-117">UriTemplate-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d5776-117">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="d5776-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="d5776-118">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
