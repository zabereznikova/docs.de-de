---
title: 'Vorgehensweise: Erstellen von Windows-Diensten'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
ms.openlocfilehash: 514675b3c3ce1f6701dff571361df672fb520c6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053657"
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="fb4b2-102">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="fb4b2-102">How to: Create Windows Services</span></span>
<span data-ttu-id="fb4b2-103">Wenn Sie einen Dienst erstellen möchten, können Sie die Visual Studio-Projektvorlage **Windows-Dienst** verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-103">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="fb4b2-104">Von dieser Vorlage wird ein großer Teil der Arbeit übernommen, indem auf die entsprechenden Klassen und Namespaces verwiesen wird, die Vererbung von den Basisklassen für Dienste eingerichtet wird und eine Reihe von Methoden überschrieben werden, die voraussichtlich überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-104">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="fb4b2-105">Die Projektvorlage Windows Service ist nicht in der Express Edition von Visual Studio verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-105">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="fb4b2-106">Das Erstellen eines funktionierenden Diensts erfordert mindestens:</span><span class="sxs-lookup"><span data-stu-id="fb4b2-106">At a minimum, to create a functional service you must:</span></span>  
  
- <span data-ttu-id="fb4b2-107">Legen Sie die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-107">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
- <span data-ttu-id="fb4b2-108">Das Erstellen der für die Dienstanwendung erforderlichen Installationsprogramme.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-108">Create the necessary installers for your service application.</span></span>  
  
- <span data-ttu-id="fb4b2-109">Durch das Überschreiben der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode und der <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Methode und die Eingabe von Code wird das Verhalten des Diensts angepasst.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-109">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="fb4b2-110">So erstellen Sie eine Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="fb4b2-110">To create a Windows Service application</span></span>  
  
1. <span data-ttu-id="fb4b2-111">Erstellen Sie ein **Windows-Dienstprojekt**.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-111">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb4b2-112">Anweisungen zum Schreiben von Diensten ohne die Vorlage finden Sie unter [Vorgehensweise: Programmgesteuertes Schreiben von Diensten](how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b2-112">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](how-to-write-services-programmatically.md).</span></span>  
  
2. <span data-ttu-id="fb4b2-113">Legen Sie im Fenster **Eigenschaften** die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft für den Dienst fest.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-113">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="fb4b2-114">![Legen Sie die ServiceName-Eigenschaft fest.](./media/windowsservice-servicename.PNG "Windows_Dienstname")</span><span class="sxs-lookup"><span data-stu-id="fb4b2-114">![Set the ServiceName property.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb4b2-115">Der Wert der <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft muss immer mit dem Namen übereinstimmen, der in den Installationsprogrammklassen aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-115">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="fb4b2-116">Wenn Sie diese Eigenschaft ändern, muss auch die <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>-Eigenschaft der Installationsprogrammklassen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-116">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3. <span data-ttu-id="fb4b2-117">Legen Sie eine oder mehrere der folgenden Eigenschaften fest, um zu bestimmen, wie der Dienst funktionieren soll.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-117">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="fb4b2-118">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fb4b2-118">Property</span></span>|<span data-ttu-id="fb4b2-119">Einstellung</span><span class="sxs-lookup"><span data-stu-id="fb4b2-119">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="fb4b2-120">Mit `True` wird angezeigt, dass vom Dienst Anforderungen zum Beenden angenommen werden. Mit `false` wird verhindert, dass der Dienst beendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-120">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="fb4b2-121">Mit `True` wird angegeben, dass der Dienst benachrichtigt werden soll, wenn der ausführende Computer heruntergefahren wird. Dadurch wird ermöglicht, dass die <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>-Prozedur aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-121">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="fb4b2-122">Mit `True` wird angegeben, dass vom Dienst Anforderungen zum Anhalten und Fortsetzen angenommen werden. Mit `false` wird verhindert, dass der Dienst angehalten oder fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-122">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="fb4b2-123">Mit `True` wird angegeben, dass der Dienst Benachrichtigungen zu Änderungen des Leistungsstatus eines Computers verarbeiten kann. `false` gibt an, dass der Dienst nicht über diese Änderungen informiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-123">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="fb4b2-124">Mit `True` werden informative Einträge in das Anwendungsereignisprotokoll geschrieben, sobald vom Dienst eine Aktion durchgeführt wird. Mit `false` wird diese Funktion deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-124">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="fb4b2-125">Weitere Informationen finden Sie unter [Vorgehensweise: Protokollinformationen über Dienste](how-to-log-information-about-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b2-125">For more information, see [How to: Log Information About Services](how-to-log-information-about-services.md).</span></span> <span data-ttu-id="fb4b2-126">**Hinweis**:  <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> ist standardmäßig auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-126">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="fb4b2-127">Wenn <xref:System.ServiceProcess.ServiceBase.CanStop%2A> oder <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> auf `false` festgelegt sind, werden vom **Dienststeuerungs-Manager** die entsprechenden Menüoptionen zum Beenden, Anhalten oder Fortsetzen des Diensts deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-127">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4. <span data-ttu-id="fb4b2-128">Greifen Sie auf den Code-Editor zu, und geben Sie die gewünschte Verarbeitung für die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Prozedur und die <xref:System.ServiceProcess.ServiceBase.OnStop%2A>-Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-128">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5. <span data-ttu-id="fb4b2-129">Überschreiben Sie alle anderen Methoden, für die Sie Funktionen definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-129">Override any other methods for which you want to define functionality.</span></span>  
  
6. <span data-ttu-id="fb4b2-130">Fügen Sie die für die Dienstanwendung erforderlichen Installationsprogramme hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-130">Add the necessary installers for your service application.</span></span> <span data-ttu-id="fb4b2-131">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b2-131">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
7. <span data-ttu-id="fb4b2-132">Erstellen Sie das Projekt, indem Sie im Menü **Erstellen** den Befehl **Projektmappe erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-132">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb4b2-133">Drücken Sie nicht F5, um das Projekt auszuführen. Dienstprojekte können auf diese Weise nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-133">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8. <span data-ttu-id="fb4b2-134">Installieren Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="fb4b2-134">Install the service.</span></span> <span data-ttu-id="fb4b2-135">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="fb4b2-135">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4b2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb4b2-136">See also</span></span>

- [<span data-ttu-id="fb4b2-137">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="fb4b2-137">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="fb4b2-138">How to: Programmgesteuertes Schreiben von Diensten</span><span class="sxs-lookup"><span data-stu-id="fb4b2-138">How to: Write Services Programmatically</span></span>](how-to-write-services-programmatically.md)
- [<span data-ttu-id="fb4b2-139">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="fb4b2-139">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="fb4b2-140">How to: Protokollinformationen über Dienste</span><span class="sxs-lookup"><span data-stu-id="fb4b2-140">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="fb4b2-141">How to: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="fb4b2-141">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="fb4b2-142">How to: Angeben des Sicherheitskontexts für Dienste</span><span class="sxs-lookup"><span data-stu-id="fb4b2-142">How to: Specify the Security Context for Services</span></span>](how-to-specify-the-security-context-for-services.md)
- [<span data-ttu-id="fb4b2-143">How to: Installieren und Deinstallieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="fb4b2-143">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="fb4b2-144">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="fb4b2-144">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
