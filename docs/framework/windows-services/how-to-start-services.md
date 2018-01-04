---
title: 'Gewusst wie: Starten von Diensten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 8352edaa9386adc1fbf3057c6e98f5a9cf9ce4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-start-services"></a><span data-ttu-id="007b4-102">Gewusst wie: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="007b4-102">How to: Start Services</span></span>
<span data-ttu-id="007b4-103">Nachdem ein Dienst installiert wurde, muss er gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="007b4-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="007b4-104">Beim Starten wird die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode für die Dienstklasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="007b4-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="007b4-105">In der Regel werden die Vorgänge, die vom Dienst durchgeführt werden, von der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="007b4-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="007b4-106">Nachdem ein Dienst gestartet worden ist, bleibt er aktiv, solange er nicht manuell angehalten oder beendet wird.</span><span class="sxs-lookup"><span data-stu-id="007b4-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="007b4-107">Für Dienste kann festgelegt werden, ob sie automatisch oder manuell gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="007b4-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="007b4-108">Ein automatisch startender Dienst wird gestartet, wenn der Computer, auf dem er installiert ist, neu gestartet oder zum ersten Mal eingeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="007b4-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="007b4-109">Ein Dienst, der manuell gestartet wird, muss von Benutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="007b4-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="007b4-110">Mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] erstellte Dienste haben standardmäßig die Startmethode Manuell.</span><span class="sxs-lookup"><span data-stu-id="007b4-110">By default, services created with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] are set to start manually.</span></span>  
  
 <span data-ttu-id="007b4-111">Es gibt mehrere Möglichkeiten, die Sie manuell einen Dienst zu starten – aus **Server-Explorer**, aus der **Dienststeuerungs-Manager**, oder von Code mithilfe einer Komponente namens der <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="007b4-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="007b4-112">Die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft für die <xref:System.ServiceProcess.ServiceInstaller>-Klasse wird festgelegt, um zu bestimmen, ob ein Dienst manuell oder automatisch gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="007b4-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="007b4-113">So geben Sie an, wie ein Dienst gestartet werden soll</span><span class="sxs-lookup"><span data-stu-id="007b4-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="007b4-114">Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="007b4-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="007b4-115">Weitere Informationen finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="007b4-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="007b4-116">Klicken Sie im Designer auf das Dienstinstallationsprogramm für den Dienst, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="007b4-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="007b4-117">In der **Eigenschaften** legen die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> -Eigenschaft auf einen der folgenden:</span><span class="sxs-lookup"><span data-stu-id="007b4-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="007b4-118">Installationszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="007b4-118">To have your service install</span></span>|<span data-ttu-id="007b4-119">Festzulegender Wert</span><span class="sxs-lookup"><span data-stu-id="007b4-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="007b4-120">Sobald der Computer neu gestartet wird</span><span class="sxs-lookup"><span data-stu-id="007b4-120">When the computer is restarted</span></span>|<span data-ttu-id="007b4-121">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="007b4-121">**Automatic**</span></span>|  
    |<span data-ttu-id="007b4-122">Sobald der Dienst von einer expliziten Benutzeraktion gestartet wird</span><span class="sxs-lookup"><span data-stu-id="007b4-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="007b4-123">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="007b4-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="007b4-124">Um zu verhindern, dass den Dienst gestartet wird, legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Eigenschaft **deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="007b4-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="007b4-125">Wenn ein Server mehrmals neu gestartet wird, kann damit Zeit gespart werden, indem das Starten von Diensten verhindert wird, die in der Regel gestartet würden.</span><span class="sxs-lookup"><span data-stu-id="007b4-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="007b4-126">Diese und weitere Eigenschaften können geändert werden, nachdem der Dienst installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="007b4-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="007b4-127">Es gibt mehrere Möglichkeiten, Sie können starten ein Diensts, dessen <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Prozess festgelegt werden, um **manuell** – aus **Server-Explorer**, aus der **Windows-Dienstkontroll-Manager**, oder von Code.</span><span class="sxs-lookup"><span data-stu-id="007b4-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="007b4-128">Es ist wichtig zu beachten, dass nicht alle diese Methoden tatsächlich den Dienst im Kontext der start der **Dienststeuerungs-Manager**; **Server-Explorer** und programmgesteuerte Methoden für das Starten des Diensts Startmethoden geändert, den Controller.</span><span class="sxs-lookup"><span data-stu-id="007b4-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="007b4-129">So starten Sie einen Dienst manuell mit dem Server-Explorer</span><span class="sxs-lookup"><span data-stu-id="007b4-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="007b4-130">In **Server-Explorer**, fügen Sie den Server soll, wenn er noch nicht aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="007b4-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="007b4-131">Weitere Informationen finden Sie unter Vorgehensweise: Zugriff und Server-Explorer-Datenbank-Explorer zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="007b4-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="007b4-132">Erweitern Sie die **Services** Knoten, und suchen Sie den Dienst, die Sie starten möchten.</span><span class="sxs-lookup"><span data-stu-id="007b4-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="007b4-133">Maustaste auf den Namen des Diensts, und klicken Sie auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="007b4-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="007b4-134">So starten Sie einen Dienst manuell mit dem Dienststeuerungs-Manager</span><span class="sxs-lookup"><span data-stu-id="007b4-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="007b4-135">Öffnen der **Dienststeuerungs-Manager** durch eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="007b4-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="007b4-136">Windows XP und 2000 Professional, mit der Maustaste **Arbeitsplatz** auf den Desktop, und klicken Sie dann auf **verwalten**.</span><span class="sxs-lookup"><span data-stu-id="007b4-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="007b4-137">Erweitern Sie im angezeigten Dialogfeld die **Dienste und Anwendungen** Knoten.</span><span class="sxs-lookup"><span data-stu-id="007b4-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="007b4-138">\- oder –</span><span class="sxs-lookup"><span data-stu-id="007b4-138">\- or -</span></span>  
  
    -   <span data-ttu-id="007b4-139">Klicken Sie in Windows Server 2003 und Windows 2000 Server **starten**, zeigen Sie auf **Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Services**.</span><span class="sxs-lookup"><span data-stu-id="007b4-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="007b4-140">In Windows NT, Version 4.0, können Sie öffnen das Dialogfeld über **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="007b4-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="007b4-141">Daraufhin sollte jetzt der Dienst die **Services** Bereich des Fensters.</span><span class="sxs-lookup"><span data-stu-id="007b4-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="007b4-142">Wählen Sie den Dienst in der Liste der rechten Maustaste darauf, und klicken Sie dann auf **starten**.</span><span class="sxs-lookup"><span data-stu-id="007b4-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="007b4-143">So starten Sie einen Dienst programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="007b4-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="007b4-144">Erstellen Sie eine Instanz der <xref:System.ServiceProcess.ServiceController>-Klasse, und konfigurieren Sie sie so, dass Daten mit dem Dienst ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="007b4-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="007b4-145">Starten Sie den Dienst, indem Sie die <xref:System.ServiceProcess.ServiceController.Start%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="007b4-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007b4-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="007b4-146">See Also</span></span>  
 [<span data-ttu-id="007b4-147">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="007b4-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="007b4-148">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="007b4-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="007b4-149">Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="007b4-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
