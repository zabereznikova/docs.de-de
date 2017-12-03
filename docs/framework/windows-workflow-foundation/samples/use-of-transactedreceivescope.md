---
title: Verwendung von TransactedReceiveScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9d20e6280b440e3b1595dd25535857ac7828d2d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="use-of-transactedreceivescope"></a><span data-ttu-id="df82b-102">Verwendung von TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="df82b-102">Use of TransactedReceiveScope</span></span>
<span data-ttu-id="df82b-103">Dieses Beispiel veranschaulicht, wie eine Transaktion mit <xref:System.Activities.Statements.TransactionScope> von einem Client auf einen Server übertragen wird, um eine neue Transaktion auf dem Client und ein <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Element zu erstellen, sodass eine Meldung mit einem Transaktionsfluss empfangen und die Lebensdauer der Transaktion auf dem Server mit einem Bereich versehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="df82b-103">This sample shows how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="df82b-104">Das Beispiel besteht aus zwei Projekten, die in den Rollen des Clients und des Server fungieren.</span><span class="sxs-lookup"><span data-stu-id="df82b-104">The sample consists of two projects that fill the roles of client and server.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="df82b-105">Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="df82b-105">Client Application</span></span>  
 <span data-ttu-id="df82b-106">Die Clientanwendung führt einen Workflow aus, der die verteilte Transaktions-ID ausgibt, eine Meldung an den Server sendet, die Transaktion übertragt, die Antwort empfängt, die verteilte Transaktions-ID erneut ausgibt und den Vorgang dann abschließt.</span><span class="sxs-lookup"><span data-stu-id="df82b-106">The client application runs a workflow that prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="df82b-107">Wenn die verteilte Transaktions-ID zu Beginn Daten ausgibt, handelt es sich um eine leere GUID, da die Transaktion nach wie vor lokal ist.</span><span class="sxs-lookup"><span data-stu-id="df82b-107">When the distributed transaction ID is initially prints, it is an empty GUID as the transaction is still only local.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="df82b-108">Serveranwendung</span><span class="sxs-lookup"><span data-stu-id="df82b-108">Server Application</span></span>  
 <span data-ttu-id="df82b-109">Das Serverprojekt verhält sich ähnlich, der Workflow wird jedoch in <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet, da ein Endpunkt auf die Meldung des Clients hin überwacht werden muss.</span><span class="sxs-lookup"><span data-stu-id="df82b-109">The server project is similar, however, the workflow is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> because it must listen on an endpoint for the message from the client.</span></span> <span data-ttu-id="df82b-110">Der Workflow basiert auf dem <xref:System.ServiceModel.Activities.TransactedReceiveScope>, der die übertragene Transaktion vom Client empfängt, die gesendete Meldung ausgibt, die verteilte Transaktions-ID ausgibt und die Antwort an den Client sendet.</span><span class="sxs-lookup"><span data-stu-id="df82b-110">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the message that was sent, prints the distributed transaction ID and sends the reply to the client.</span></span> <span data-ttu-id="df82b-111">Die verteilte Transaktions-ID ist jetzt eine nicht leere GUID, und wenn dem Text des <xref:System.ServiceModel.Activities.TransactedReceiveScope> eine Aktivität hinzugefügt wurde, die Transaktionen verarbeiten kann, würde dieser unter der übertragenen Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df82b-111">The distributed transaction ID is now a non-empty GUID and if a transaction-aware activity was added to the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, it would execute under the flowed transaction.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="df82b-112">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="df82b-112">To run the sample</span></span>  
  
1.  <span data-ttu-id="df82b-113">Öffnen Sie die Projektmappe "TransactedReceiveScope.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df82b-113">Open the TransactedReceiveScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="df82b-114">Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="df82b-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="df82b-115">Sobald die Erstellung erfolgreich war, mit der rechten Maustaste in der Projektmappe, und wählen Sie **Startprojekte festlegen**.</span><span class="sxs-lookup"><span data-stu-id="df82b-115">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="df82b-116">Wählen Sie im Dialogfeld **mehrere Startprojekte** und sicherzustellen, dass die Aktion für beide Projekte **starten**.</span><span class="sxs-lookup"><span data-stu-id="df82b-116">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="df82b-117">Drücken Sie F5, oder wählen Sie **Debuggen** aus der **Debuggen** Menü.</span><span class="sxs-lookup"><span data-stu-id="df82b-117">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="df82b-118">Alternativ können Sie STRG + F5 oder wählen Sie **Starten ohne Debugging** aus der **Debuggen** -Menü, um ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="df82b-118">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df82b-119">Der Server muss vor dem Starten des Clients ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df82b-119">The server must be running prior to starting the client.</span></span> <span data-ttu-id="df82b-120">Die Ausgabe im Konsolenfenster, das den Dienst hostet, gibt an, wenn dieser gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="df82b-120">The output from the console window hosting the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="df82b-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="df82b-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="df82b-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="df82b-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="df82b-123">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="df82b-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="df82b-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="df82b-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`