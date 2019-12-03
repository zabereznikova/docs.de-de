---
title: LINQ-Meldungsabfragekorrelation
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: a4b0ed058cfe8d3d487342c9feefdf1b1efe07c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715585"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="c9c67-102">LINQ-Meldungsabfragekorrelation</span><span class="sxs-lookup"><span data-stu-id="c9c67-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="c9c67-103">Dieses Beispiel veranschaulicht, wie die inhaltsbasierte Korrelation mithilfe einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.MessageQuery>-Implementierung im Gegensatz zu der vom System bereitgestellten <xref:System.ServiceModel.XPathMessageQuery> erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c9c67-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="c9c67-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="c9c67-104">Demonstrates</span></span>  
 <span data-ttu-id="c9c67-105">Benutzerdefinierte <xref:System.ServiceModel.Dispatcher.MessageQuery>, inhaltsbasierte Korrelation.</span><span class="sxs-lookup"><span data-stu-id="c9c67-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="c9c67-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="c9c67-106">Discussion</span></span>  
 <span data-ttu-id="c9c67-107">In diesem Beispiel wird veranschaulicht, wie zum Zwecke der Korrelation eine Erweiterung von der <xref:System.ServiceModel.Dispatcher.MessageQuery>-Basisklasse durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9c67-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="c9c67-108">Die benutzerdefinierte Implementierung, `LinqMessageQuery`, ermöglicht es Benutzern, einen XName anzugeben, der innerhalb der Meldung mit XLinq gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9c67-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="c9c67-109">Die von der Abfrage abgerufenen Daten werden verwendet, um den Korrelationsschlüssel zu bilden, mit dem Meldungen an die entsprechende Workflowinstanz weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c67-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9c67-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c9c67-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c9c67-111">Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9c67-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="c9c67-112">Zum Ausführen dieses Beispiels müssen die richtigen URL-ACLs hinzugefügt werden (Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) ), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten, um die entsprechenden ACLs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9c67-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="c9c67-113">Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c9c67-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="c9c67-114">Sobald die URL-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="c9c67-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="c9c67-115">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="c9c67-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="c9c67-116">Legen Sie mehrere Start Projekte fest, indem Sie mit der rechten Maustaste auf die Projekt Mappe Klicken und **Start Projekte festlegen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c9c67-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="c9c67-117">Fügen Sie den **Dienst** und den **Client** (in dieser Reihenfolge) als mehrere Start Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9c67-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="c9c67-118">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="c9c67-118">Run the application.</span></span> <span data-ttu-id="c9c67-119">Die Clientkonsole zeigt einen Workflow, der eine Bestellung sendet und die Bestell-ID empfängt und dann daraufhin den Auftrag bestätigt.</span><span class="sxs-lookup"><span data-stu-id="c9c67-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="c9c67-120">Das Fenster "Dienst" zeigt die Anforderungen, die verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c67-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c9c67-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c9c67-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c9c67-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c9c67-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="c9c67-123">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c9c67-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9c67-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c9c67-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
