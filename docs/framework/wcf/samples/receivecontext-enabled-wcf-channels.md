---
title: ReceiveContext-aktivierte WCF-Kanäle
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442745"
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="ba5f4-102">ReceiveContext-aktivierte WCF-Kanäle</span><span class="sxs-lookup"><span data-stu-id="ba5f4-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="ba5f4-103">In diesem Beispiel wird die Nützlichkeit WCF-Kanälen mit Aktivierung von <xref:System.ServiceModel.Channels.ReceiveContext> erläutert.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="ba5f4-104">Im Beispiel wird ein Dienst für die Suche nach dem Produkt von zwei Zahlen mithilfe eines NetMSMQ-Kanals implementiert.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="ba5f4-105">Mit der <xref:System.ServiceModel.Channels.ReceiveContext>-Klasse kann eine Anwendung entscheiden, ob auf die Meldung zugegriffen werden oder sie für die weitere Verarbeitung in der Warteschlange belassen werden soll, selbst nachdem der Inhalt der Meldung überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="ba5f4-106">In diesem Beispiel sendet ein Client zufällige ganze Zahlen an eine Transaktionswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="ba5f4-107">Der `ProductCalculator`-Dienst empfängt die Meldungen und überprüft den Meldungsinhalt, der aus ganzen Zahlen besteht, um zu bestimmen, ob das Produkt berechnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="ba5f4-108">Wenn der Dienstvorgang das Produkt nicht berechnet, wird die Meldung zurück an die Warteschlange gesendet und kann erneut vom Dienst empfangen werden, der die Warteschlange überwacht.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba5f4-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ba5f4-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ba5f4-111">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ba5f4-112">Dieses Beispiel befindet sich im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ba5f4-113">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba5f4-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ba5f4-114">Stellen Sie sicher, dass Microsoft Message Queuing (MSMQ) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="ba5f4-115">So installieren Sie MSMQ unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba5f4-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ba5f4-116">In **Server-Manager**, klicken Sie auf **Features**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="ba5f4-117">Im rechten Bereich unter **Featureübersicht**, klicken Sie auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="ba5f4-118">Erweitern Sie im angezeigten Fenster **Message Queuing-**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="ba5f4-119">Erweitern Sie **Message Queuing-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="ba5f4-120">Klicken Sie auf **Verzeichnisdienstintegration** (bei Computern mit einer Domäne verknüpft ist), und klicken Sie dann auf **HTTP-Unterstützung**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="ba5f4-121">Klicken Sie auf **Weiter**, und klicken Sie dann auf **installieren**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="ba5f4-122">So installieren Sie MSMQ unter [!INCLUDE[wv](../../../../includes/wv-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba5f4-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ba5f4-123">Open **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="ba5f4-124">Klicken Sie auf **Programme** und dann unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="ba5f4-125">Erweitern Sie **Microsoft Message Queue (MSMQ) Server**, erweitern Sie **Microsoft Message Queue (MSMQ) Server Core**, und wählen Sie dann die Kontrollkästchen für die Message Queuing-Funktionen installieren:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="ba5f4-126">Message Queuing Server</span><span class="sxs-lookup"><span data-stu-id="ba5f4-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="ba5f4-127">MSMQ-Active Directory-Domänendienstintegration (bei Computern, die einer Domäne zugewiesen sind)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="ba5f4-128">MSMQ-HTTP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="ba5f4-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="ba5f4-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="ba5f4-130">Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="ba5f4-131">Stellen Sie sicher, dass [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="ba5f4-132">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die ReceiveContextProductGenerator.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="ba5f4-133">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="ba5f4-134">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-134">To run the solution, press CTRL+F5.</span></span>
