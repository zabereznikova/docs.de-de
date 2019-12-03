---
title: Asynchrone Kommunikation
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: 28b325a6bd870282577a2989b616628d52262deb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711862"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="ec1c1-102">Asynchrone Kommunikation</span><span class="sxs-lookup"><span data-stu-id="ec1c1-102">Asynchronous Communication</span></span>
<span data-ttu-id="ec1c1-103">In diesem Beispiel wird veranschaulicht, wie die Kommunikation zwischen zwei unterschiedlichen WF-Diensten (Windows Workflow Foundation) standardmäßig asynchron erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ec1c1-104">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="ec1c1-104">Demonstrates</span></span>  
 <span data-ttu-id="ec1c1-105">Asynchrone Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Diensten.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ec1c1-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ec1c1-106">Discussion</span></span>  
 <span data-ttu-id="ec1c1-107">Dieses Beispiel zeigt, wie die Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Anwendungen mithilfe der von .NET Framework bereitgestellten Messagingaktivitäten asynchron erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="ec1c1-108">Dieses Beispiel besteht aus den folgenden drei Projekten.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="ec1c1-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="ec1c1-109">CreditCheckService</span></span>  
 <span data-ttu-id="ec1c1-110">Dieser Dienst empfängt den Kreditscore (die Kreditwürdigkeit) einer bestimmten Person oder den Wert des zu erwerbenden Elements und legt dann fest, ob der Person der Kredit gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="ec1c1-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="ec1c1-111">RentalApprovalService</span></span>  
 <span data-ttu-id="ec1c1-112">Dieser Dienst empfängt eine Anwendung von einer Person, die einen Kredit benötigt.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="ec1c1-113">Dieser Dienst kommuniziert asynchron mit dem `CreditCheckService`-Dienst, um zu bestimmen, ob die Kreditanwendung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="ec1c1-114">Client</span><span class="sxs-lookup"><span data-stu-id="ec1c1-114">Client</span></span>  
 <span data-ttu-id="ec1c1-115">Der Client kommuniziert synchron mit dem `RentalApprovalService`-Dienst, um zu ermitteln, ob der Kredit genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ec1c1-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ec1c1-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ec1c1-117">Klicken Sie mit der rechten Maustaste auf die Lösung **asynchronouscommunication** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="ec1c1-118">Wählen Sie unter **Allgemeine Eigenschaften**die Option **Startprojekt**aus, und wählen Sie **mehrere Start Projekte**aus.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="ec1c1-119">Verschieben Sie **rentalapprovalservice** an die erste Position in der Liste, gefolgt von **creditcheckservice**, gefolgt vom **Client**.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="ec1c1-120">Legen Sie die **Start** Aktion für alle drei Projekte fest.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="ec1c1-121">Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ec1c1-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ec1c1-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="ec1c1-124">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec1c1-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ec1c1-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
