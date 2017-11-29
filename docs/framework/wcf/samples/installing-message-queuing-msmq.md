---
title: Installieren von Message Queuing (MSMQ)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 89d81a25da6494fc9cbf041ae68f2985b5c90a81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="21e9a-102">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="21e9a-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="21e9a-103">Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="21e9a-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21e9a-104">Message Queuing 4.0 ist in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="21e9a-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="21e9a-105">So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="21e9a-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1.  <span data-ttu-id="21e9a-106">Klicken Sie im Server-Manager auf **Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-106">In Server Manager, click **Features**.</span></span>  
  
2.  <span data-ttu-id="21e9a-107">Im rechten Bereich unter **Featureübersicht**, klicken Sie auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3.  <span data-ttu-id="21e9a-108">Erweitern Sie im jetzt geöffneten Fenster **Message Queuing**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4.  <span data-ttu-id="21e9a-109">Erweitern Sie **Message Queuing-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-109">Expand **Message Queuing Services**.</span></span>  
  
5.  <span data-ttu-id="21e9a-110">Klicken Sie auf **Verzeichnisdienstintegration** (für Computer Mitglied einer Domäne), und klicken Sie auf **HTTP-Unterstützung**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6.  <span data-ttu-id="21e9a-111">Klicken Sie auf **Weiter**, klicken Sie dann auf **installieren**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="21e9a-112">So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista</span><span class="sxs-lookup"><span data-stu-id="21e9a-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="21e9a-113">Open **in der Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-113">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="21e9a-114">Klicken Sie auf **Programme** und dann unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3.  <span data-ttu-id="21e9a-115">Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="21e9a-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    -   <span data-ttu-id="21e9a-116">MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)</span><span class="sxs-lookup"><span data-stu-id="21e9a-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    -   <span data-ttu-id="21e9a-117">MSMQ-HTTP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="21e9a-117">MSMQ HTTP Support.</span></span>  
  
4.  <span data-ttu-id="21e9a-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="21e9a-119">Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="21e9a-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="21e9a-120">So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="21e9a-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1.  <span data-ttu-id="21e9a-121">Open **in der Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-121">Open **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="21e9a-122">Klicken Sie auf **Software** , und klicken Sie dann auf **Windows-Komponenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3.  <span data-ttu-id="21e9a-123">Wählen Sie Message Queuing, und klicken Sie auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21e9a-124">Wenn Sie [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, wählen Sie den Anwendungsserver für den Zugriff auf Message Queuing aus.</span><span class="sxs-lookup"><span data-stu-id="21e9a-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4.  <span data-ttu-id="21e9a-125">Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="21e9a-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5.  <span data-ttu-id="21e9a-126">Klicken Sie auf **OK** , schließen die Seite "Details", und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="21e9a-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="21e9a-127">Schließen Sie die Installation ab.</span><span class="sxs-lookup"><span data-stu-id="21e9a-127">Complete the installation.</span></span>  
  
6.  <span data-ttu-id="21e9a-128">Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="21e9a-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e9a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21e9a-129">See Also</span></span>  
 [<span data-ttu-id="21e9a-130">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="21e9a-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
