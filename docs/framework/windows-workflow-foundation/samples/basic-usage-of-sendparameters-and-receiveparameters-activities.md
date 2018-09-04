---
title: Grundlegende Verwendung der Aktivitäten SendParameters und ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: c13999ad1571a6413e30e801b6c642000f8e4654
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504007"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="59caf-102">Grundlegende Verwendung der Aktivitäten SendParameters und ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="59caf-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="59caf-103">Anhand dieses Beispiels wird die Verwendung der <xref:System.ServiceModel.Activities.SendParametersContent>-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveParametersContent>-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="59caf-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="59caf-104">Der Dienst macht einen Vorgang verfügbar, der ein Zeichenfolgenargument verwendet, und gibt die Eingabe in einem Echo-Vorgang an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="59caf-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="59caf-105">Im Beispiel wird gezeigt, wie die Parameter für diese Messagingaktivitäten eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="59caf-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59caf-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="59caf-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="59caf-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="59caf-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="59caf-108">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="59caf-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59caf-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="59caf-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="59caf-110">Verwenden dieses Beispiels</span><span class="sxs-lookup"><span data-stu-id="59caf-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="59caf-111">Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="59caf-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="59caf-112">Führen Sie zunächst die unter "[Projektmappenbasisverzeichnis]\EchoWorkflowService\bin\debug" generierte EchoWorkflowService-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="59caf-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="59caf-113">Führen Sie als Nächstes die unter "[Projektmappenbasisverzeichnis]\EchoWorkflowClient\bin\debug" generierte EchoWorkflowClient-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="59caf-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="59caf-114">Der Client ruft den Echo-Vorgang für den Dienst auf und gibt die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="59caf-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="59caf-115">Drücken Sie nach dem Abschluss die EINGABETASTE, um den Client und dann der Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="59caf-115">When complete, press ENTER to exit the client and then the service.</span></span>