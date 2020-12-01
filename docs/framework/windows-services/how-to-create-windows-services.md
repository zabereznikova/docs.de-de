---
title: 'Vorgehensweise: Erstellen von Windows-Diensten'
description: Verwenden Sie die Projektvorlage „Windows-Dienst“, um einen Dienst zu erstellen. Legen Sie die Eigenschaft ServiceName fest, erstellen Sie Installationsprogramme, und setzen Sie die Methoden OnStart und OnStop außer Kraft.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
ms.openlocfilehash: 9b171fa54cf65a482625c276c26185b12075c753
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270705"
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="41125-104">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="41125-104">How to: Create Windows Services</span></span>

<span data-ttu-id="41125-105">Wenn Sie einen Dienst erstellen möchten, können Sie die Visual Studio-Projektvorlage **Windows-Dienst** verwenden.</span><span class="sxs-lookup"><span data-stu-id="41125-105">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="41125-106">Von dieser Vorlage wird ein großer Teil der Arbeit übernommen, indem auf die entsprechenden Klassen und Namespaces verwiesen wird, die Vererbung von den Basisklassen für Dienste eingerichtet wird und eine Reihe von Methoden überschrieben werden, die voraussichtlich überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="41125-106">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="41125-107">Die Projektvorlage Windows Service ist nicht in der Express Edition von Visual Studio verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41125-107">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="41125-108">Das Erstellen eines funktionierenden Diensts erfordert mindestens:</span><span class="sxs-lookup"><span data-stu-id="41125-108">At a minimum, to create a functional service you must:</span></span>  
  
- <span data-ttu-id="41125-109">Legen Sie die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="41125-109">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
- <span data-ttu-id="41125-110">Das Erstellen der für die Dienstanwendung erforderlichen Installationsprogramme.</span><span class="sxs-lookup"><span data-stu-id="41125-110">Create the necessary installers for your service application.</span></span>  
  
- <span data-ttu-id="41125-111">Durch das Überschreiben der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und der <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode und die Eingabe von Code wird das Verhalten des Diensts angepasst.</span><span class="sxs-lookup"><span data-stu-id="41125-111">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="41125-112">So erstellen Sie eine Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="41125-112">To create a Windows Service application</span></span>  
  
1. <span data-ttu-id="41125-113">Erstellen Sie ein **Windows-Dienstprojekt**.</span><span class="sxs-lookup"><span data-stu-id="41125-113">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41125-114">Anweisungen zum Schreiben von Diensten ohne die Vorlage finden Sie unter [Vorgehensweise: Programmgesteuertes Schreiben von Diensten](how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="41125-114">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](how-to-write-services-programmatically.md).</span></span>  
  
2. <span data-ttu-id="41125-115">Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft für den Dienst fest.</span><span class="sxs-lookup"><span data-stu-id="41125-115">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="41125-116">![Legen Sie die Eigenschaft ServiceName fest.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="41125-116">![Set the ServiceName property.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41125-117">Der Wert der <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft muss immer mit dem Namen übereinstimmen, der in den Installationsprogrammklassen aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="41125-117">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="41125-118">Wenn Sie diese Eigenschaft ändern, muss auch die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Installationsprogrammklassen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="41125-118">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3. <span data-ttu-id="41125-119">Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um zu bestimmen, wie der Dienst funktionieren soll.</span><span class="sxs-lookup"><span data-stu-id="41125-119">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="41125-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="41125-120">Property</span></span>|<span data-ttu-id="41125-121">Einstellung</span><span class="sxs-lookup"><span data-stu-id="41125-121">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="41125-122">Mit `True` wird angezeigt, dass vom Dienst Anforderungen zum Beenden angenommen werden. Mit `false` wird verhindert, dass der Dienst beendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="41125-122">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="41125-123">Mit `True` wird angegeben, dass der Dienst benachrichtigt werden soll, wenn der ausführende Computer heruntergefahren wird. Dadurch wird ermöglicht, dass die <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>-Prozedur aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="41125-123">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="41125-124">Mit `True` wird angegeben, dass vom Dienst Anforderungen zum Anhalten und Fortsetzen angenommen werden. Mit `false` wird verhindert, dass der Dienst angehalten oder fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="41125-124">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="41125-125">Mit `True` wird angegeben, dass der Dienst Benachrichtigungen zu Änderungen des Leistungsstatus eines Computers verarbeiten kann. `false` gibt an, dass der Dienst nicht über diese Änderungen informiert wird.</span><span class="sxs-lookup"><span data-stu-id="41125-125">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="41125-126">Mit `True` werden informative Einträge in das Anwendungsereignisprotokoll geschrieben, sobald vom Dienst eine Aktion durchgeführt wird. Mit `false` wird diese Funktion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="41125-126">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="41125-127">Weitere Informationen finden Sie unter [Vorgehensweise: Protokollinformationen über Dienste](how-to-log-information-about-services.md).</span><span class="sxs-lookup"><span data-stu-id="41125-127">For more information, see [How to: Log Information About Services](how-to-log-information-about-services.md).</span></span> <span data-ttu-id="41125-128">**Hinweis**:  <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> ist standardmäßig auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="41125-128">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="41125-129">Wenn <xref:System.ServiceProcess.ServiceBase.CanStop%2A> oder <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> auf `false` festgelegt sind, werden vom **Dienststeuerungs-Manager** die entsprechenden Menüoptionen zum Beenden, Anhalten oder Fortsetzen des Diensts deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="41125-129">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4. <span data-ttu-id="41125-130">Greifen Sie auf den Code-Editor zu, und geben Sie die gewünschte Verarbeitung für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="41125-130">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5. <span data-ttu-id="41125-131">Überschreiben Sie alle anderen Methoden, für die Sie Funktionen definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="41125-131">Override any other methods for which you want to define functionality.</span></span>  
  
6. <span data-ttu-id="41125-132">Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="41125-132">Add the necessary installers for your service application.</span></span> <span data-ttu-id="41125-133">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="41125-133">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
7. <span data-ttu-id="41125-134">Erstellen Sie das Projekt, indem Sie im Menü **Erstellen** den Befehl **Projektmappe erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="41125-134">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41125-135">Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="41125-135">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8. <span data-ttu-id="41125-136">Installieren Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="41125-136">Install the service.</span></span> <span data-ttu-id="41125-137">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="41125-137">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41125-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41125-138">See also</span></span>

- [<span data-ttu-id="41125-139">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="41125-139">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="41125-140">How to: Programmgesteuertes Schreiben von Diensten</span><span class="sxs-lookup"><span data-stu-id="41125-140">How to: Write Services Programmatically</span></span>](how-to-write-services-programmatically.md)
- [<span data-ttu-id="41125-141">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="41125-141">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="41125-142">How to: Protokollinformationen über Dienste</span><span class="sxs-lookup"><span data-stu-id="41125-142">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="41125-143">How to: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="41125-143">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="41125-144">How to: Angeben des Sicherheitskontexts für Dienste</span><span class="sxs-lookup"><span data-stu-id="41125-144">How to: Specify the Security Context for Services</span></span>](how-to-specify-the-security-context-for-services.md)
- [<span data-ttu-id="41125-145">How to: Installieren und Deinstallieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="41125-145">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="41125-146">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="41125-146">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
