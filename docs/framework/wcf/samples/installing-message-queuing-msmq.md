---
title: Installieren von Message Queuing (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 118143f2d434e9f4399c3e9141743fc0254b61ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039621"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="ef5e0-102">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="ef5e0-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="ef5e0-103">Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef5e0-104">Message Queuing 4.0 ist in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="ef5e0-105">So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ef5e0-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="ef5e0-106">Klicken Sie in Server-Manager auf **Features**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="ef5e0-107">Klicken Sie im rechten Bereich unter **featurezusammenfassung**auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="ef5e0-108">Erweitern Sie im resultierenden Fenster **Message Queuing**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="ef5e0-109">Erweitern Sie **Message Queuing Dienste**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="ef5e0-110">Klicken Sie auf **Verzeichnisdienst Integration** (bei Computern, die einer Domäne beigetreten sind), und klicken Sie dann auf **http**</span><span class="sxs-lookup"><span data-stu-id="ef5e0-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="ef5e0-111">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="ef5e0-112">So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista</span><span class="sxs-lookup"><span data-stu-id="ef5e0-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="ef5e0-113">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="ef5e0-114">Klicken Sie auf **Programme** , und klicken Sie dann unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="ef5e0-115">Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="ef5e0-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="ef5e0-116">MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)</span><span class="sxs-lookup"><span data-stu-id="ef5e0-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="ef5e0-117">MSMQ-HTTP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="ef5e0-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="ef5e0-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="ef5e0-119">Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="ef5e0-120">So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ef5e0-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="ef5e0-121">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="ef5e0-122">Klicken Sie auf Software **Entfernen** und dann auf **Windows-Komponenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="ef5e0-123">Wählen Sie Message Queuing und klicken Sie auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef5e0-124">Wenn Sie [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, wählen Sie den Anwendungsserver für den Zugriff auf Message Queuing aus.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-124">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="ef5e0-125">Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="ef5e0-126">Klicken Sie auf **OK** , um die Detailseite zu schließen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="ef5e0-127">Schließen Sie die Installation ab.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="ef5e0-128">Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ef5e0-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef5e0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef5e0-129">See also</span></span>

- [<span data-ttu-id="ef5e0-130">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="ef5e0-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
