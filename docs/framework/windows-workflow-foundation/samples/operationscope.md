---
title: OperationScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6d1e2738e8cdb546a1dcbb00689e5b4c360ddd04
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="operationscope"></a><span data-ttu-id="42ab8-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="42ab8-102">OperationScope</span></span>
<span data-ttu-id="42ab8-103">Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet werden können, um in einem Workflowdienst eine vorhandene benutzerdefinierte Aktivität als Vorgang verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="42ab8-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="42ab8-104">Dieses Beispiel umfasst eine neue benutzerdefinierte Aktivität, die als `OperationScope` bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="42ab8-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="42ab8-105">Sie ist dazu vorgesehen, die Entwicklung eines Workflowdiensts zu vereinfachen, indem Benutzer den Textkörper der Vorgänge als benutzerdefinierte Aktivitäten getrennt erstellen können und sie dann einfach als Dienstvorgänge mit der `OperationScope`-Aktivität verfügbar machen können.</span><span class="sxs-lookup"><span data-stu-id="42ab8-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="42ab8-106">Eine benutzerdefinierte `Add`-Aktivität, die zwei `in`-Argumente annimmt und ein `out`-Argument zurückgibt, könnte z. B. als `Add`-Vorgang mit dem Workflowdienst verfügbar gemacht werden, indem es in einer `OperationScope`-Aktivität abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="42ab8-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="42ab8-107">Der Bereich funktioniert, indem er die als Textkörper bereitgestellte Aktivität überprüft.</span><span class="sxs-lookup"><span data-stu-id="42ab8-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="42ab8-108">Alle ungebundenen `in`-Argumente werden als Eingaben von der eingehenden Nachricht betrachtet.</span><span class="sxs-lookup"><span data-stu-id="42ab8-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="42ab8-109">Alle `out`-Argumente, unabhängig davon, ob sie gebunden sind, werden als Ausgaben in der nachfolgenden Antwortnachricht betrachtet.</span><span class="sxs-lookup"><span data-stu-id="42ab8-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="42ab8-110">Der Name des verfügbar gemachten Vorgangs wird dem Anzeigenamen der `OperationScope`-Aktivität entnommen.</span><span class="sxs-lookup"><span data-stu-id="42ab8-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="42ab8-111">Das Endergebnis ist, dass die Textaktivität mit den Parametern aus den Nachrichten, die an die Argumente der Aktivität gebunden sind, von <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> umschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="42ab8-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="42ab8-112">Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="42ab8-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="42ab8-113">Für die Ausführung müssen richtige URL-ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="42ab8-113">To run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="42ab8-114">[Konfigurieren von HTTP und HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="42ab8-114"> [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="42ab8-115">Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten fügt die entsprechenden ACLs hinzu (Stellen Sie sicher, dass die Domäne und den Benutzernamen, für die Domäne ersetzt werden %\\%UserName%).</span><span class="sxs-lookup"><span data-stu-id="42ab8-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="42ab8-116">**Netsh http Urlacl Url hinzufügen = http: / / +: 8000 / Benutzer = "% Domäne"\\%UserName%**</span><span class="sxs-lookup"><span data-stu-id="42ab8-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="42ab8-117">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="42ab8-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="42ab8-118">Öffnen Sie die Projektmappe "OperationScope.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42ab8-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="42ab8-119">Mehrere Startprojekte festlegen, indem Sie die Projektmappe im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Startprojekte festlegen**.</span><span class="sxs-lookup"><span data-stu-id="42ab8-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="42ab8-120">Fügen Sie Scenario und Scenario_Client (in dieser Reihenfolge) als mehrere Startprojekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="42ab8-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="42ab8-121">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42ab8-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="42ab8-122">Dieser Schritt ist aufgrund der benutzerdefinierten `OperationScope`-Aktivität zum Anzeigen des Workflows "BankService.xaml" erforderlich.</span><span class="sxs-lookup"><span data-stu-id="42ab8-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="42ab8-123">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="42ab8-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="42ab8-124">Die Konsole Scenario_Client fordert Sie zu Eingaben auf, und die entsprechende Ausgabe wird in der Konsole Scenario dargestellt.</span><span class="sxs-lookup"><span data-stu-id="42ab8-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="42ab8-125">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="42ab8-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="42ab8-126">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="42ab8-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="42ab8-127">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="42ab8-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="42ab8-128">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="42ab8-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`  
  
## <a name="see-also"></a><span data-ttu-id="42ab8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42ab8-129">See Also</span></span>
