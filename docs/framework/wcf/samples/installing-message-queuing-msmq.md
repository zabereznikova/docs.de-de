---
title: Installieren von Message Queuing (MSMQ)
description: Erfahren Sie, wie Sie Message Queuing 4,0 und Message Queuing 3,0 als Teil eines einmaligen Einrichtungs Verfahrens für die Verwendung mit WFC-Beispielen installieren.
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: bf33a5cd899bf2d7ef4947c51ac1723c8eb80c29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281871"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="96e4b-103">Installieren von Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="96e4b-103">Installing Message Queuing (MSMQ)</span></span>

<span data-ttu-id="96e4b-104">Im Folgenden wird beschrieben, wie Sie Message Queuing 4.0 und Message Queuing 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="96e4b-104">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96e4b-105">Message Queuing 4,0 ist in Windows XP und Windows Server 2003 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96e4b-105">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="96e4b-106">So installieren Sie Message Queuing 4.0 unter Windows Server 2008 oder Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="96e4b-106">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="96e4b-107">Klicken Sie in Server-Manager auf **Features**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-107">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="96e4b-108">Klicken Sie im rechten Bereich unter **featurezusammenfassung** auf **Features hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-108">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="96e4b-109">Erweitern Sie im resultierenden Fenster **Message Queuing**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-109">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="96e4b-110">Erweitern Sie **Message Queuing Dienste**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-110">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="96e4b-111">Klicken Sie auf **Verzeichnisdienst Integration** (bei Computern, die einer Domäne beigetreten sind), und klicken Sie dann auf **http**</span><span class="sxs-lookup"><span data-stu-id="96e4b-111">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="96e4b-112">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-112">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="96e4b-113">So installieren Sie Message Queuing 4.0 unter Windows 7 oder Windows Vista</span><span class="sxs-lookup"><span data-stu-id="96e4b-113">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="96e4b-114">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-114">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="96e4b-115">Klicken Sie auf **Programme** , und klicken Sie dann unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-115">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="96e4b-116">Erweitern Sie Microsoft Message Queue (MSMQ)-Server, erweitern Sie Microsoft Message Queue (MSMQ)-Serverkernkomponenten, und aktivieren Sie die Kontrollkästchen für die zu installierenden Message Queuing-Funktionen:</span><span class="sxs-lookup"><span data-stu-id="96e4b-116">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="96e4b-117">MSMQ-Active Directory-Domänendienstintegration (für Computer, die einer Domäne zugewiesen sind)</span><span class="sxs-lookup"><span data-stu-id="96e4b-117">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="96e4b-118">MSMQ-HTTP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="96e4b-118">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="96e4b-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-119">Click **OK**.</span></span>  
  
5. <span data-ttu-id="96e4b-120">Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="96e4b-120">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="96e4b-121">So installieren Sie Message Queuing 3.0 unter Windows XP und Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="96e4b-121">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="96e4b-122">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-122">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="96e4b-123">Klicken Sie auf Software **Entfernen** und dann auf **Windows-Komponenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-123">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="96e4b-124">Wählen Sie Message Queuing und klicken Sie auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-124">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="96e4b-125">Wenn Sie Windows Server 2003 ausführen, wählen Sie Anwendungs Server aus, um auf Message Queuing zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="96e4b-125">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="96e4b-126">Stellen Sie sicher, dass die Option MSMQ-HTTP-Unterstützung auf der Detailseite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="96e4b-126">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="96e4b-127">Klicken Sie auf **OK** , um die Detailseite zu schließen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="96e4b-127">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="96e4b-128">Schließen Sie die Installation ab.</span><span class="sxs-lookup"><span data-stu-id="96e4b-128">Complete the installation.</span></span>  
  
6. <span data-ttu-id="96e4b-129">Wenn Sie aufgefordert werden, den Computer neu zu starten, klicken Sie auf **OK** , um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="96e4b-129">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e4b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96e4b-130">See also</span></span>

- [<span data-ttu-id="96e4b-131">Setupanweisungen</span><span class="sxs-lookup"><span data-stu-id="96e4b-131">Set-Up Instructions</span></span>](set-up-instructions.md)
