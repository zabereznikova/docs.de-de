---
title: Beispiel für die asynchrone Suche
ms.date: 03/30/2017
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
ms.openlocfilehash: 37edcb4d1f04eb56d3f24ca3acc3543d7f9696f5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424390"
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="4c597-102">Beispiel für die asynchrone Suche</span><span class="sxs-lookup"><span data-stu-id="4c597-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="4c597-103">In diesem Beispiel wird gezeigt, wie der asynchrone Suchvorgang aus einer Clientanwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c597-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="4c597-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="4c597-104">Sample Details</span></span>  
 <span data-ttu-id="4c597-105">Der Vorteil dieses Entwurfsmusters besteht darin, dass der Client in Folge der Suchanforderung asynchron über die gefundenen Endpunkte benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c597-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="4c597-106">Öffnen Sie die Datei Client.cs, um die Funktionsweise zu sehen.</span><span class="sxs-lookup"><span data-stu-id="4c597-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="4c597-107">Beachten Sie, dass zwei Delegaten an den Ereignishandlern des <xref:System.ServiceModel.Discovery.DiscoveryClient>-Objekts angefügt sind.</span><span class="sxs-lookup"><span data-stu-id="4c597-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="4c597-108">Ein Delegat wird aufgerufen, wenn ein <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted>-Ereignis ausgelöst wird, und ein anderer Delegat wird jedes Mal aufgerufen, wenn ein <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>-Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4c597-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="4c597-109">Im Beispiel wird gezeigt, wie Sie dieses Muster in der Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4c597-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c597-110">In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung müssen die richtigen URL-ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4c597-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> <span data-ttu-id="4c597-111">Weitere Informationen finden Sie unter [Konfigurieren von HTTP und HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="4c597-111">For more information, see [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="4c597-112">Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c597-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="4c597-113">Es empfiehlt sich, die folgenden Argumente durch die Domäne und den Benutzernamen zu ersetzen, wenn der Befehl nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4c597-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c597-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="4c597-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4c597-115">Öffnen Sie die Datei AsyncFind.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c597-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="4c597-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c597-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="4c597-117">Öffnen Sie eine [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung, und navigieren Sie zum Verzeichnis \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug oder \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug, und führen Sie Service.exe aus.</span><span class="sxs-lookup"><span data-stu-id="4c597-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="4c597-118">Nachdem der Dienst gestartet wurde, navigieren Sie zum Verzeichnis \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug oder WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug, und führen Sie Client.exe aus.</span><span class="sxs-lookup"><span data-stu-id="4c597-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="4c597-119">Beobachten Sie, ob der Client den Dienst finden und aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="4c597-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c597-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4c597-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c597-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4c597-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4c597-122">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4c597-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c597-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4c597-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="4c597-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c597-124">See Also</span></span>
