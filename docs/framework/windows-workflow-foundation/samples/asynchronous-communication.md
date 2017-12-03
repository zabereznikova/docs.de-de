---
title: Asynchrone Kommunikation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea2d705a38ddae1689d212bbd50196920fe73fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-communication"></a><span data-ttu-id="2129b-102">Asynchrone Kommunikation</span><span class="sxs-lookup"><span data-stu-id="2129b-102">Asynchronous Communication</span></span>
<span data-ttu-id="2129b-103">Anhand dieses Beispiels wird veranschaulicht, wie die Kommunikation zwischen zwei verschiedenen [!INCLUDE[wf](../../../../includes/wf-md.md)]-Diensten standardmäßig asynchron erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2129b-103">This sample demonstrates how the communication between two different [!INCLUDE[wf](../../../../includes/wf-md.md)] services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2129b-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="2129b-104">Demonstrates</span></span>  
 <span data-ttu-id="2129b-105">Asynchrone Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Diensten.</span><span class="sxs-lookup"><span data-stu-id="2129b-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2129b-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="2129b-106">Discussion</span></span>  
 <span data-ttu-id="2129b-107">Dieses Beispiel zeigt, wie die Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Anwendungen mithilfe der von .NET Framework bereitgestellten Messagingaktivitäten asynchron erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2129b-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="2129b-108">Dieses Beispiel besteht aus den folgenden drei Projekten.</span><span class="sxs-lookup"><span data-stu-id="2129b-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="2129b-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="2129b-109">CreditCheckService</span></span>  
 <span data-ttu-id="2129b-110">Dieser Dienst empfängt den Kreditscore (die Kreditwürdigkeit) einer bestimmten Person oder den Wert des zu erwerbenden Elements und legt dann fest, ob der Person der Kredit gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="2129b-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="2129b-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="2129b-111">RentalApprovalService</span></span>  
 <span data-ttu-id="2129b-112">Dieser Dienst empfängt eine Anwendung von einer Person, die einen Kredit benötigt.</span><span class="sxs-lookup"><span data-stu-id="2129b-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="2129b-113">Dieser Dienst kommuniziert asynchron mit dem `CreditCheckService`-Dienst, um zu bestimmen, ob die Kreditanwendung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="2129b-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="2129b-114">Client</span><span class="sxs-lookup"><span data-stu-id="2129b-114">Client</span></span>  
 <span data-ttu-id="2129b-115">Der Client kommuniziert synchron mit dem `RentalApprovalService`-Dienst, um zu ermitteln, ob der Kredit genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="2129b-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2129b-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="2129b-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2129b-117">Mit der rechten Maustaste die **AsynchronousCommunication** Lösung, und wählen **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2129b-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2129b-118">In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie **mehrere Startprojekte**.</span><span class="sxs-lookup"><span data-stu-id="2129b-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="2129b-119">Verschieben Sie **RentalApprovalService** an die erste Position in der Liste, gefolgt von **CreditCheckService**, gefolgt von **Client**.</span><span class="sxs-lookup"><span data-stu-id="2129b-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="2129b-120">Legen Sie die **starten** Aktion für alle drei Projekte.</span><span class="sxs-lookup"><span data-stu-id="2129b-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="2129b-121">Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="2129b-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2129b-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2129b-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2129b-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2129b-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2129b-124">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2129b-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2129b-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2129b-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
