---
title: 'Vorgehensweise: Starten von Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 3544f7d846ecf68ed5ed01812b9c69b295c63c69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952422"
---
# <a name="how-to-start-services"></a><span data-ttu-id="fa71e-102">Vorgehensweise: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="fa71e-102">How to: Start Services</span></span>
<span data-ttu-id="fa71e-103">Nachdem ein Dienst installiert wurde, muss er gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fa71e-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="fa71e-104">Beim Starten wird die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode für die Dienstklasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fa71e-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="fa71e-105">In der Regel werden die Vorgänge, die vom Dienst durchgeführt werden, von der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="fa71e-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="fa71e-106">Nachdem ein Dienst gestartet worden ist, bleibt er aktiv, solange er nicht manuell angehalten oder beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa71e-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="fa71e-107">Für Dienste kann festgelegt werden, ob sie automatisch oder manuell gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fa71e-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="fa71e-108">Ein automatisch startender Dienst wird gestartet, wenn der Computer, auf dem er installiert ist, neu gestartet oder zum ersten Mal eingeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="fa71e-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="fa71e-109">Ein Dienst, der manuell gestartet wird, muss von Benutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fa71e-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa71e-110">Mit Visual Studio erstellte Dienste sind standardmäßig auf manuelles Starten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fa71e-110">By default, services created with Visual Studio are set to start manually.</span></span>  
  
 <span data-ttu-id="fa71e-111">Ein Dienst kann auf verschiedene Weise manuell gestartet werden: Mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** oder indem im Code die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa71e-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="fa71e-112">Die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft für die <xref:System.ServiceProcess.ServiceInstaller>-Klasse wird festgelegt, um zu bestimmen, ob ein Dienst manuell oder automatisch gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa71e-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="fa71e-113">So geben Sie an, wie ein Dienst gestartet werden soll</span><span class="sxs-lookup"><span data-stu-id="fa71e-113">To specify how a service should start</span></span>  
  
1. <span data-ttu-id="fa71e-114">Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa71e-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="fa71e-115">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fa71e-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2. <span data-ttu-id="fa71e-116">Klicken Sie im Designer auf das Dienstinstallationsprogramm für den Dienst, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa71e-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3. <span data-ttu-id="fa71e-117">Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf einen der folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="fa71e-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="fa71e-118">Installationszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="fa71e-118">To have your service install</span></span>|<span data-ttu-id="fa71e-119">Festzulegender Wert</span><span class="sxs-lookup"><span data-stu-id="fa71e-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="fa71e-120">Sobald der Computer neu gestartet wird</span><span class="sxs-lookup"><span data-stu-id="fa71e-120">When the computer is restarted</span></span>|<span data-ttu-id="fa71e-121">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="fa71e-121">**Automatic**</span></span>|  
    |<span data-ttu-id="fa71e-122">Sobald der Dienst von einer expliziten Benutzeraktion gestartet wird</span><span class="sxs-lookup"><span data-stu-id="fa71e-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="fa71e-123">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="fa71e-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="fa71e-124">Wenn der Dienst nie gestartet werden soll, legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="fa71e-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="fa71e-125">Wenn ein Server mehrmals neu gestartet wird, kann damit Zeit gespart werden, indem das Starten von Diensten verhindert wird, die in der Regel gestartet würden.</span><span class="sxs-lookup"><span data-stu-id="fa71e-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fa71e-126">Diese und weitere Eigenschaften können geändert werden, nachdem der Dienst installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fa71e-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="fa71e-127">Es stehen mehrere Möglichkeiten zur Verfügung, einen Dienst zu starten, dessen <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Vorgang auf **Manuell** festgelegt ist: mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** von Windows oder programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="fa71e-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="fa71e-128">Wichtig dabei ist, dass der Dienst nicht von allen Methoden im Kontext des **Dienststeuerungs-Managers** gestartet wird. Tatsächlich wird der Controller mit dem **Server-Explorer** und mit programmgesteuerten Startmethoden geändert.</span><span class="sxs-lookup"><span data-stu-id="fa71e-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="fa71e-129">So starten Sie einen Dienst manuell mit dem Server-Explorer</span><span class="sxs-lookup"><span data-stu-id="fa71e-129">To manually start a service from Server Explorer</span></span>  
  
1. <span data-ttu-id="fa71e-130">Fügen Sie im **Server-Explorer** den gewünschten Server hinzu, sofern dieser noch nicht aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="fa71e-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="fa71e-131">Weitere Informationen finden Sie unter „Gewusst wie: Zugreifen auf und Initialisieren von Server-Explorer und Datenbank-Explorer“.</span><span class="sxs-lookup"><span data-stu-id="fa71e-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2. <span data-ttu-id="fa71e-132">Erweitern Sie den Knoten **Dienste**, und suchen Sie den zu startenden Dienst.</span><span class="sxs-lookup"><span data-stu-id="fa71e-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3. <span data-ttu-id="fa71e-133">Klicken Sie mit der rechten Maustaste auf den Dienst, und klicken Sie dann auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="fa71e-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="fa71e-134">So starten Sie einen Dienst manuell mit dem Dienststeuerungs-Manager</span><span class="sxs-lookup"><span data-stu-id="fa71e-134">To manually start a service from Services Control Manager</span></span>  
  
1. <span data-ttu-id="fa71e-135">Öffnen Sie den **Dienststeuerungs-Manager**, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fa71e-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    - <span data-ttu-id="fa71e-136">Klicken Sie in Windows XP und 2000 Professional auf dem Desktop des Computers mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie anschließend auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="fa71e-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="fa71e-137">Erweitern Sie im nun angezeigten Dialogfeld den Knoten **Dienste und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="fa71e-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="fa71e-138">\- oder –</span><span class="sxs-lookup"><span data-stu-id="fa71e-138">\- or -</span></span>  
  
    - <span data-ttu-id="fa71e-139">Klicken Sie in Windows Server 2003 und Windows 2000 Server auf **Start**, und zeigen Sie auf **Programme**. Klicken Sie auf **Verwaltung** und anschließend auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="fa71e-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fa71e-140">In Windows NT 4.0 kann das Dialogfeld über die **Systemsteuerung** geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="fa71e-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="fa71e-141">Der Dienst wird nun im Bereich **Dienste** des Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa71e-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2. <span data-ttu-id="fa71e-142">Wählen Sie den Dienst in der Liste aus, klicken Sie mit der rechten Maustaste darauf, und klicken Sie dann auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="fa71e-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="fa71e-143">So starten Sie einen Dienst programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="fa71e-143">To manually start a service from code</span></span>  
  
1. <span data-ttu-id="fa71e-144">Erstellen Sie eine Instanz der <xref:System.ServiceProcess.ServiceController>-Klasse, und konfigurieren Sie sie so, dass Daten mit dem Dienst ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="fa71e-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2. <span data-ttu-id="fa71e-145">Starten Sie den Dienst, indem Sie die <xref:System.ServiceProcess.ServiceController.Start%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fa71e-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa71e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa71e-146">See also</span></span>

- [<span data-ttu-id="fa71e-147">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="fa71e-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="fa71e-148">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="fa71e-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="fa71e-149">Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="fa71e-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
