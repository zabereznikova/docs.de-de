---
title: 'Vorgehensweise: Starten von Diensten'
description: Hier lernen Sie verschiedene Möglichkeiten zum Starten von Diensten kennen. Nachdem ein Dienst installiert wurde, muss er gestartet werden. Beim Starten wird die „OnStart“-Methode für die Dienstklasse aufgerufen.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925721"
---
# <a name="how-to-start-services"></a><span data-ttu-id="fb021-105">Vorgehensweise: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="fb021-105">How to: Start Services</span></span>

<span data-ttu-id="fb021-106">Nachdem ein Dienst installiert wurde, muss er gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fb021-106">After a service is installed, it must be started.</span></span> <span data-ttu-id="fb021-107">Beim Starten wird die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode für die Dienstklasse aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fb021-107">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="fb021-108">In der Regel werden die Vorgänge, die vom Dienst durchgeführt werden, von der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="fb021-108">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="fb021-109">Nachdem ein Dienst gestartet worden ist, bleibt er aktiv, solange er nicht manuell angehalten oder beendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb021-109">After a service starts, it remains active until it is manually paused or stopped.</span></span>

<span data-ttu-id="fb021-110">Für Dienste kann festgelegt werden, ob sie automatisch oder manuell gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fb021-110">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="fb021-111">Ein automatisch startender Dienst wird gestartet, wenn der Computer, auf dem er installiert ist, neu gestartet oder zum ersten Mal eingeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="fb021-111">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="fb021-112">Ein Dienst, der manuell gestartet wird, muss von Benutzern gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="fb021-112">A user must start a service that starts manually.</span></span>

> [!NOTE]
> <span data-ttu-id="fb021-113">Mit Visual Studio erstellte Dienste sind standardmäßig auf manuelles Starten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb021-113">By default, services created with Visual Studio are set to start manually.</span></span>

<span data-ttu-id="fb021-114">Ein Dienst kann auf verschiedene Weise manuell gestartet werden: Mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** oder indem im Code die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb021-114">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>

<span data-ttu-id="fb021-115">Die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft für die <xref:System.ServiceProcess.ServiceInstaller>-Klasse wird festgelegt, um zu bestimmen, ob ein Dienst manuell oder automatisch gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb021-115">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>

### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="fb021-116">So geben Sie an, wie ein Dienst gestartet werden soll</span><span class="sxs-lookup"><span data-stu-id="fb021-116">To specify how a service should start</span></span>

1. <span data-ttu-id="fb021-117">Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb021-117">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="fb021-118">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fb021-118">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>

2. <span data-ttu-id="fb021-119">Klicken Sie im Designer auf das Dienstinstallationsprogramm für den Dienst, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb021-119">In the designer, click the service installer for the service you are working with.</span></span>

3. <span data-ttu-id="fb021-120">Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf einen der folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="fb021-120">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>

    |<span data-ttu-id="fb021-121">Installationszeitpunkt</span><span class="sxs-lookup"><span data-stu-id="fb021-121">To have your service install</span></span>|<span data-ttu-id="fb021-122">Festzulegender Wert</span><span class="sxs-lookup"><span data-stu-id="fb021-122">Set this value</span></span>|
    |----------------------------------|--------------------|
    |<span data-ttu-id="fb021-123">Sobald der Computer neu gestartet wird</span><span class="sxs-lookup"><span data-stu-id="fb021-123">When the computer is restarted</span></span>|<span data-ttu-id="fb021-124">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="fb021-124">**Automatic**</span></span>|
    |<span data-ttu-id="fb021-125">Sobald der Dienst von einer expliziten Benutzeraktion gestartet wird</span><span class="sxs-lookup"><span data-stu-id="fb021-125">When an explicit user action starts the service</span></span>|<span data-ttu-id="fb021-126">**Manuell**</span><span class="sxs-lookup"><span data-stu-id="fb021-126">**Manual**</span></span>|

    > [!TIP]
    > <span data-ttu-id="fb021-127">Wenn der Dienst nie gestartet werden soll, legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="fb021-127">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="fb021-128">Wenn ein Server mehrmals neu gestartet wird, kann damit Zeit gespart werden, indem das Starten von Diensten verhindert wird, die in der Regel gestartet würden.</span><span class="sxs-lookup"><span data-stu-id="fb021-128">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb021-129">Diese und weitere Eigenschaften können geändert werden, nachdem der Dienst installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb021-129">These and other properties can be changed after your service is installed.</span></span>

    <span data-ttu-id="fb021-130">Es stehen mehrere Möglichkeiten zur Verfügung, einen Dienst zu starten, dessen <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Vorgang auf **Manuell** festgelegt ist: mit dem **Server-Explorer**, dem **Dienststeuerungs-Manager** von Windows oder programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="fb021-130">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="fb021-131">Wichtig dabei ist, dass der Dienst nicht von allen Methoden im Kontext des **Dienststeuerungs-Managers** gestartet wird. Tatsächlich wird der Controller mit dem **Server-Explorer** und mit programmgesteuerten Startmethoden geändert.</span><span class="sxs-lookup"><span data-stu-id="fb021-131">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>

### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="fb021-132">So starten Sie einen Dienst manuell mit dem Server-Explorer</span><span class="sxs-lookup"><span data-stu-id="fb021-132">To manually start a service from Server Explorer</span></span>

1. <span data-ttu-id="fb021-133">Fügen Sie im **Server-Explorer** den gewünschten Server hinzu, sofern dieser noch nicht aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="fb021-133">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="fb021-134">Weitere Informationen finden Sie unter „Gewusst wie: Zugreifen auf und Initialisieren von Server-Explorer und Datenbank-Explorer“.</span><span class="sxs-lookup"><span data-stu-id="fb021-134">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>

2. <span data-ttu-id="fb021-135">Erweitern Sie den Knoten **Dienste**, und suchen Sie den zu startenden Dienst.</span><span class="sxs-lookup"><span data-stu-id="fb021-135">Expand the **Services** node, and then locate the service you want to start.</span></span>

3. <span data-ttu-id="fb021-136">Klicken Sie mit der rechten Maustaste auf den Dienst, und klicken Sie dann auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="fb021-136">Right-click the name of the service, and click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="fb021-137">So starten Sie einen Dienst manuell mit dem Dienststeuerungs-Manager</span><span class="sxs-lookup"><span data-stu-id="fb021-137">To manually start a service from Services Control Manager</span></span>

1. <span data-ttu-id="fb021-138">Öffnen Sie den **Dienststeuerungs-Manager**, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fb021-138">Open the **Services Control Manager** by doing one of the following:</span></span>

    - <span data-ttu-id="fb021-139">Klicken Sie in Windows XP und 2000 Professional auf dem Desktop des Computers mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie anschließend auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="fb021-139">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="fb021-140">Erweitern Sie im nun angezeigten Dialogfeld den Knoten **Dienste und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="fb021-140">In the dialog box that appears, expand the **Services and Applications** node.</span></span>

      <span data-ttu-id="fb021-141">\- oder -</span><span class="sxs-lookup"><span data-stu-id="fb021-141">\- or -</span></span>

    - <span data-ttu-id="fb021-142">Klicken Sie in Windows Server 2003 und Windows 2000 Server auf **Start**, und zeigen Sie auf **Programme**. Klicken Sie auf **Verwaltung** und anschließend auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="fb021-142">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="fb021-143">In Windows NT 4.0 kann das Dialogfeld über die **Systemsteuerung** geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="fb021-143">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>

    <span data-ttu-id="fb021-144">Der Dienst wird nun im Bereich **Dienste** des Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb021-144">You should now see your service listed in the **Services** section of the window.</span></span>

2. <span data-ttu-id="fb021-145">Wählen Sie den Dienst in der Liste aus, klicken Sie mit der rechten Maustaste darauf, und klicken Sie dann auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="fb021-145">Select your service in the list, right-click it, and then click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="fb021-146">So starten Sie einen Dienst programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="fb021-146">To manually start a service from code</span></span>

1. <span data-ttu-id="fb021-147">Erstellen Sie eine Instanz der <xref:System.ServiceProcess.ServiceController>-Klasse, und konfigurieren Sie sie so, dass Daten mit dem Dienst ausgetauscht werden können.</span><span class="sxs-lookup"><span data-stu-id="fb021-147">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>

2. <span data-ttu-id="fb021-148">Starten Sie den Dienst, indem Sie die <xref:System.ServiceProcess.ServiceController.Start%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fb021-148">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb021-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb021-149">See also</span></span>

- [<span data-ttu-id="fb021-150">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="fb021-150">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="fb021-151">How to: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="fb021-151">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="fb021-152">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="fb021-152">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
