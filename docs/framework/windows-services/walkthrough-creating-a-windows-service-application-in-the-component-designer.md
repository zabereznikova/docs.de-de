---
title: 'Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Service applications, walkthroughs
- Windows Service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: c33b8badcacd4e228d70f8e770d4bf27144c29eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520512"
---
# <a name="walkthrough-creating-a-windows-service-application-in-the-component-designer"></a><span data-ttu-id="07c43-102">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer</span><span class="sxs-lookup"><span data-stu-id="07c43-102">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>
<span data-ttu-id="07c43-103">In diesem Artikel wird beschrieben, wie Sie eine einfache Windows-Dienstanwendung in Visual Studio erstellen, die Meldungen in ein Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="07c43-103">This article demonstrates how to create a simple Windows Service application in Visual Studio that writes messages to an event log.</span></span> <span data-ttu-id="07c43-104">Hier werden die grundlegenden Schritte beschrieben, die Sie zum Erstellen und Verwenden Ihres Dienstes:</span><span class="sxs-lookup"><span data-stu-id="07c43-104">Here are the basic steps that you perform to create and use your service:</span></span>  
  
1.  <span data-ttu-id="07c43-105">[Erstellen eines Diensts](#BK_CreateProject) , indem Sie die Projektvorlage **Windows-Dienst** verwenden und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-105">[Creating a Service](#BK_CreateProject) by using the **Windows Service** project template, and configure it.</span></span> <span data-ttu-id="07c43-106">Mit dieser Vorlage wird eine Klasse erstellt, die aus <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> geerbt wird. Außerdem wird ein Großteil des grundlegenden Dienstcodes geschrieben, z. B. der Code zum Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="07c43-106">This template creates a class for you that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> and writes much of the basic service code, such as the code to start the service.</span></span>  
  
2.  <span data-ttu-id="07c43-107">[Hinzufügen von Features zum Dienst](#BK_WriteCode) für die Prozeduren <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> , und überschreiben Sie alle anderen Methoden, die Sie neu definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="07c43-107">[Adding Features to the Service](#BK_WriteCode) for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures, and override any other methods that you want to redefine.</span></span>  
  
3.  <span data-ttu-id="07c43-108">[Einstellung des Dienststatus](#BK_SetStatus).</span><span class="sxs-lookup"><span data-stu-id="07c43-108">[Setting Service Status](#BK_SetStatus).</span></span> <span data-ttu-id="07c43-109">Standardmäßig umfassen Dienste, die mit <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erstellt werden, nur eine Teilmenge der verfügbaren Status-Markierungen.</span><span class="sxs-lookup"><span data-stu-id="07c43-109">By default, services created with <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> implement only a subset of the available status flags.</span></span> <span data-ttu-id="07c43-110">Wenn Ihr Dienst sehr lange zum Starten, Anhalten oder Beenden braucht, können Sie die Statuswerte, wie Start ausstehend oder Stopp ausstehend, implementieren, um anzugeben, dass die Funktion für einen Arbeitsgang aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-110">If your service takes a long time to start up, pause, or stop, you can implement status values such as Start Pending or Stop Pending to indicate that it's working on an operation.</span></span>  
  
4.  <span data-ttu-id="07c43-111">[Hinzufügen von Installern zum Dienst](#BK_AddInstallers) für Ihre Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="07c43-111">[Adding Installers to the Service](#BK_AddInstallers) for your service application.</span></span>  
  
5.  <span data-ttu-id="07c43-112">(Optional) [Einstellung der Startparameter](#BK_StartupParameters), geben Sie Standard-Startargumente an, und bieten Sie Benutzern die Möglichkeit, die Standardeinstellungen beim manuellen Starten des Diensts außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="07c43-112">(Optional) [Set Startup Parameters](#BK_StartupParameters), specify default startup arguments, and enable users to override default settings when they start your service manually.</span></span>  
  
6.  <span data-ttu-id="07c43-113">[Erstellen des Dienstes](#BK_Build).</span><span class="sxs-lookup"><span data-stu-id="07c43-113">[Building the Service](#BK_Build).</span></span>  
  
7.  <span data-ttu-id="07c43-114">[Installieren des Dienstes](#BK_Install) auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="07c43-114">[Installing the Service](#BK_Install) on the local machine.</span></span>  
  
8.  <span data-ttu-id="07c43-115">Greifen Sie auf den Windows Service Control Manager zu und [Starten und Ausführen des Dienstes](#BK_StartService).</span><span class="sxs-lookup"><span data-stu-id="07c43-115">Access the Windows Service Control Manager and [Starting and Running the Service](#BK_StartService).</span></span>  
  
9. <span data-ttu-id="07c43-116">[Ein Windowsdienst wird deinstalliert...](#BK_Uninstall).</span><span class="sxs-lookup"><span data-stu-id="07c43-116">[Uninstalling a Windows Service](#BK_Uninstall).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="07c43-117">In der Express Edition von Visual Studio ist die Windows Services-Projektvorlage, die für diese exemplarische Vorgehensweise erforderlich ist, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="07c43-117">The Windows Services project template that is required for this walkthrough is not available in the Express edition of Visual Studio.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]  
  
<a name="BK_CreateProject"></a>   
## <a name="creating-a-service"></a><span data-ttu-id="07c43-118">Erstellen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="07c43-118">Creating a Service</span></span>  
 <span data-ttu-id="07c43-119">Erstellen Sie zunächst das Projekt, und legen Sie die Werte fest, die für die korrekte Funktion des Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="07c43-119">To begin, you create the project and set values that are required for the service to function correctly.</span></span>  
  
#### <a name="to-create-and-configure-your-service"></a><span data-ttu-id="07c43-120">So erstellen und konfigurieren Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-120">To create and configure your service</span></span>  
  
1.  <span data-ttu-id="07c43-121">Wählen Sie in der Visual Studio-Menüleiste **Datei**, **Neu**und **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-121">In Visual Studio, on the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="07c43-122">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07c43-122">The **New Project** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="07c43-123">Wählen Sie **Windows-Dienst**in der Liste der Projektvorlagen für Visual Basic oder Visual C# aus, und nennen Sie das Projekt **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="07c43-123">In the list of Visual Basic or Visual C# project templates, choose **Windows Service**, and name the project **MyNewService**.</span></span> <span data-ttu-id="07c43-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="07c43-124">Choose **OK**.</span></span>  
  
     <span data-ttu-id="07c43-125">Die Projektvorlage fügt automatisch die Komponentenklasse `Service1` hinzu, die von <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erbt.</span><span class="sxs-lookup"><span data-stu-id="07c43-125">The project template automatically adds a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="07c43-126">Im Menü **Bearbeiten** wählen Sie **Suchen und Ersetzen**, **In Dateien suchen** (Tastatur: STRG+UMSCHALT+F).</span><span class="sxs-lookup"><span data-stu-id="07c43-126">On the **Edit** menu, choose **Find and Replace**, **Find in Files** (Keyboard: Ctrl+Shift+F).</span></span> <span data-ttu-id="07c43-127">Ersetzen Sie alle Vorkommen von `Service1` durch `MyNewService`.</span><span class="sxs-lookup"><span data-stu-id="07c43-127">Change all occurrences of `Service1` to `MyNewService`.</span></span> <span data-ttu-id="07c43-128">Instanzen finden Sie im Service1.cs Program.cs und Service1.Designer.cs (oder ihre Entsprechungen von VB).</span><span class="sxs-lookup"><span data-stu-id="07c43-128">You’ll find instances in Service1.cs, Program.cs, and Service1.Designer.cs (or their .vb equivalents).</span></span>  
  
4.  <span data-ttu-id="07c43-129">Legen Sie im Fenster **Eigenschaften** für **Service1.cs [Entwurf]** oder **Service1.vb [Entwurf]** den <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> und die **(Name)** -Eigenschaft für `Service1` auf **MyNewService**fest, wenn dieser noch nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-129">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> and the **(Name)** property for `Service1` to **MyNewService**, if it's not already set.</span></span>  
  
5.  <span data-ttu-id="07c43-130">Benennen Sie im Projektmappen-Explorer **Service1.cs** in **MyNewService.cs**oder **Service1.vb** in **MyNewService.vb**um.</span><span class="sxs-lookup"><span data-stu-id="07c43-130">In Solution Explorer, rename **Service1.cs** to **MyNewService.cs**, or **Service1.vb** to **MyNewService.vb**.</span></span>  
  
<a name="BK_WriteCode"></a>   
## <a name="adding-features-to-the-service"></a><span data-ttu-id="07c43-131">Hinzufügen von Features zum Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-131">Adding Features to the Service</span></span>  
 <span data-ttu-id="07c43-132">In diesem Abschnitt fügen Sie dem Windows-Dienst ein benutzerdefiniertes Ereignisprotokoll hinzu.</span><span class="sxs-lookup"><span data-stu-id="07c43-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="07c43-133">Ereignisprotokolle sind Windows-Diensten in keiner Weise zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="07c43-133">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="07c43-134">Hier wird die <xref:System.Diagnostics.EventLog> -Komponente als Beispiel für die Art der Komponente verwendet, die Sie einem Windows-Dienst hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="07c43-134">Here the <xref:System.Diagnostics.EventLog> component is used as an example of the type of component you could add to a Windows service.</span></span>  
  
#### <a name="to-add-custom-event-log-functionality-to-your-service"></a><span data-ttu-id="07c43-135">So fügen Sie dem Dienst eine benutzerdefinierte Ereignisprotokollfunktion hinzu</span><span class="sxs-lookup"><span data-stu-id="07c43-135">To add custom event log functionality to your service</span></span>  
  
1.  <span data-ttu-id="07c43-136">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-136">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="07c43-137">Ziehen Sie im **Werkzeugkasten** aus dem Abschnitt **Komponenten**eine <xref:System.Diagnostics.EventLog> -Komponente in den Designer.</span><span class="sxs-lookup"><span data-stu-id="07c43-137">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>  
  
3.  <span data-ttu-id="07c43-138">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-138">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>  
  
4.  <span data-ttu-id="07c43-139">Fügen Sie eine Deklaration für das **EventLog** -Objekt in der `MyNewService` -Klasse direkt nach der Zeile hinzu, die die `components` -Variable deklariert:</span><span class="sxs-lookup"><span data-stu-id="07c43-139">Add a declaration for the **eventLog** object in the `MyNewService` class, right after the line that declares the `components` variable:</span></span>  
  
     [!code-csharp[VbRadconService#16](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#16)]
     [!code-vb[VbRadconService#16](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#16)]  
  
5.  <span data-ttu-id="07c43-140">Fügen Sie den Konstruktor hinzu oder bearbeiten Sie ihn, um ein benutzerdefiniertes Ereignisprotokoll zu definieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-140">Add or edit the constructor to define a custom event log:</span></span>  
  
     [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
     [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]  
  
#### <a name="to-define-what-occurs-when-the-service-starts"></a><span data-ttu-id="07c43-141">So legen Sie fest, was beim Starten des Diensts ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="07c43-141">To define what occurs when the service starts</span></span>  
  
-   <span data-ttu-id="07c43-142">Suchen Sie im Code-Editor die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode, die beim Erstellen des Projekts automatisch überschrieben wurde, und ersetzen Sie den Code durch Folgendes.</span><span class="sxs-lookup"><span data-stu-id="07c43-142">In the Code Editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project, and replace the code with the following.</span></span> <span data-ttu-id="07c43-143">Dadurch wird ein Eintrag in das Ereignisprotokoll beim Starten des Diensts eingefügt:</span><span class="sxs-lookup"><span data-stu-id="07c43-143">This adds an entry to the event log when the service starts running:</span></span>  
  
     [!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
     [!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]  
  
     <span data-ttu-id="07c43-144">Eine Dienstanwendung soll eine lange Laufzeit haben, damit sie in der Regel etwas abfragt oder etwas im System überwacht.</span><span class="sxs-lookup"><span data-stu-id="07c43-144">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="07c43-145">Die Überwachung wird in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="07c43-145">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="07c43-146">Allerdings erfolgt die Überwachung jedoch nicht durch <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="07c43-146">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="07c43-147">Die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode muss zum Betriebssystem zurückkehren, sobald die Ausführung des Dienstes begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="07c43-147">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="07c43-148">Sie darf keine Endlosschleife oder Blöcke ausführen.</span><span class="sxs-lookup"><span data-stu-id="07c43-148">It must not loop forever or block.</span></span> <span data-ttu-id="07c43-149">Wenn Sie einen einfachen Abrufmechanismus einrichten, können Sie die Komponente <xref:System.Timers.Timer?displayProperty=nameWithType> wie folgt verwenden: Klicken Sie In der Methode <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, legen Sie Parameter in der Komponente fest, und setzen Sie dann die Eigenschaft <xref:System.Timers.Timer.Enabled%2A>auf `true`.</span><span class="sxs-lookup"><span data-stu-id="07c43-149">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="07c43-150">Der Zeitgeber löst dann regelmäßig zu der Zeit Ereignisse im Code aus, zu der der Dienst seine Überwachung ausführen könnte.</span><span class="sxs-lookup"><span data-stu-id="07c43-150">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="07c43-151">Sie können hierfür den folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="07c43-151">You can use the following code to do this:</span></span>  
  
    ```csharp  
    // Set up a timer to trigger every minute.  
    System.Timers.Timer timer = new System.Timers.Timer();  
    timer.Interval = 60000; // 60 seconds  
    timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);  
    timer.Start();  
    ```  
  
    ```vb  
    ' Set up a timer to trigger every minute.  
    Dim timer As System.Timers.Timer = New System.Timers.Timer()  
    timer.Interval = 60000 ' 60 seconds  
    AddHandler timer.Elapsed, AddressOf Me.OnTimer  
    timer.Start()  
    ```  
     <span data-ttu-id="07c43-152">Fügen Sie der Klasse eine Membervariable hinzu.</span><span class="sxs-lookup"><span data-stu-id="07c43-152">Add a member variable to the class.</span></span> <span data-ttu-id="07c43-153">Sie enthält den Bezeichner des nächsten Ereignisses, das in das Ereignisprotokoll geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="07c43-153">It will contain the identifier of the next event to write into the event log.</span></span>

    ```csharp
    private int eventId = 1;
    ```

    ```vb
    Private eventId As Integer = 1
    ```

     <span data-ttu-id="07c43-154">Fügen Sie Code zum Bearbeiten des Zeitgeberereignisses hinzu:</span><span class="sxs-lookup"><span data-stu-id="07c43-154">Add code to handle the timer event:</span></span>  
  
    ```csharp  
    public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)  
    {  
        // TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);  
    }  
    ```  
  
    ```vb  
    Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)  
        ' TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)  
        eventId = eventId + 1  
    End Sub  
    ```  
  
     <span data-ttu-id="07c43-155">Möglicherweise möchten Sie Aufgaben mit Arbeitsthreads im Hintergrund statt Ihre Arbeit auf der Haupt-Thread ausführen.</span><span class="sxs-lookup"><span data-stu-id="07c43-155">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="07c43-156">Ein Beispiel hierfür finden Sie unter der <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>-Referenzseite.</span><span class="sxs-lookup"><span data-stu-id="07c43-156">For an example of this, see the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> reference page.</span></span>  
  
#### <a name="to-define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="07c43-157">So legen Sie fest, was ausgeführt wird, wenn der Dienst beendet wurde</span><span class="sxs-lookup"><span data-stu-id="07c43-157">To define what occurs when the service is stopped</span></span>  
  
-   <span data-ttu-id="07c43-158">Ersetzen Sie den Code für die <xref:System.ServiceProcess.ServiceBase.OnStop%2A> -Methode durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="07c43-158">Replace the code for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method with the following.</span></span> <span data-ttu-id="07c43-159">Dadurch wird ein Eintrag in das Ereignisprotokoll beim Starten des Diensts angehalten:</span><span class="sxs-lookup"><span data-stu-id="07c43-159">This adds an entry to the event log when the service is stopped:</span></span>  
  
     [!code-csharp[VbRadconService#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
     [!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]  
  
 <span data-ttu-id="07c43-160">Im nächsten Abschnitt können Sie die Methoden <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, und <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> überschreiben, um zusätzliche Verarbeitungsschritte für die Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-160">In the next section, you can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>  
  
#### <a name="to-define-other-actions-for-the-service"></a><span data-ttu-id="07c43-161">So definieren Sie weitere Aktionen für den Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-161">To define other actions for the service</span></span>  
  
-   <span data-ttu-id="07c43-162">Lokalisieren Sie die betreffende Methode, die Sie bearbeiten möchten, und überschreiben sie, um zu definieren, was ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07c43-162">Locate the method that you want to handle, and override it to define what you want to occur.</span></span>  
  
     <span data-ttu-id="07c43-163">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> -Methode überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-163">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>  
  
     [!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
     [!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]  
  
 <span data-ttu-id="07c43-164">Einige benutzerdefinierte Aktionen müssen eintreten, wenn ein Windows-Dienst von der <xref:System.Configuration.Install.Installer> Klasse installiert wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-164">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="07c43-165">Visual Studio kann diese Installationsprogramme speziell für einen Windows-Dienst erstellen und sie dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07c43-165">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>  
  
<a name="BK_SetStatus"></a>   
## <a name="setting-service-status"></a><span data-ttu-id="07c43-166">Einstellung des Dienststatus</span><span class="sxs-lookup"><span data-stu-id="07c43-166">Setting Service Status</span></span>  
 <span data-ttu-id="07c43-167">Dienste melden ihren Status mit dem Dienststeuerungs-Manager, damit Benutzer erkennen können, ob ein Dienst ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-167">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="07c43-168">Dienste, die von standardmäßig von <xref:System.ServiceProcess.ServiceBase> übernommen werden, melden eine begrenzte Anzahl von Statuseinstellungen, darunter Beendet, Angehalten und Werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="07c43-168">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="07c43-169">Wenn es etwas länger dauert, bis ein Dienst startet, kann es hilfreich sein, einen Status Start ausstehend zu melden.</span><span class="sxs-lookup"><span data-stu-id="07c43-169">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="07c43-170">Sie können auch die Statuseinstellungen Start ausstehend und Stopp ausstehend durch Hinzufügen von Code implementieren, der in Windows die Funktion [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx)aufruft.</span><span class="sxs-lookup"><span data-stu-id="07c43-170">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx).</span></span>  
  
#### <a name="to-implement-service-pending-status"></a><span data-ttu-id="07c43-171">Für die Implementierung des Status Service ausstehend</span><span class="sxs-lookup"><span data-stu-id="07c43-171">To implement service pending status</span></span>  
  
1.  <span data-ttu-id="07c43-172">Fügen Sie eine `using`-Anweisung oder `Imports`-Meldung an die <xref:System.Runtime.InteropServices?displayProperty=nameWithType> -Namespace in der Datei MyNewService.cs oder MyNewService.vb hinzu:</span><span class="sxs-lookup"><span data-stu-id="07c43-172">Add a `using` statement or `Imports` declaration to the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    ```  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    ```  
  
2.  <span data-ttu-id="07c43-173">Fügen Sie folgenden Code zum MyNewService.cs hinzu, um die `ServiceState` Werte zu deklarieren und um eine Struktur für den Status hinzuzufügen, die Sie in einem Plattformaufruf verwenden:</span><span class="sxs-lookup"><span data-stu-id="07c43-173">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>  
  
    ```csharp  
    public enum ServiceState  
      {  
          SERVICE_STOPPED = 0x00000001,  
          SERVICE_START_PENDING = 0x00000002,  
          SERVICE_STOP_PENDING = 0x00000003,  
          SERVICE_RUNNING = 0x00000004,  
          SERVICE_CONTINUE_PENDING = 0x00000005,  
          SERVICE_PAUSE_PENDING = 0x00000006,  
          SERVICE_PAUSED = 0x00000007,  
      }  
  
      [StructLayout(LayoutKind.Sequential)]  
      public struct ServiceStatus  
      {  
          public int dwServiceType;  
          public ServiceState dwCurrentState;  
          public int dwControlsAccepted;  
          public int dwWin32ExitCode;  
          public int dwServiceSpecificExitCode;  
          public int dwCheckPoint;  
          public int dwWaitHint;  
      };  
    ```  
  
    ```vb  
    Public Enum ServiceState  
        SERVICE_STOPPED = 1  
        SERVICE_START_PENDING = 2  
        SERVICE_STOP_PENDING = 3  
        SERVICE_RUNNING = 4  
        SERVICE_CONTINUE_PENDING = 5  
        SERVICE_PAUSE_PENDING = 6  
        SERVICE_PAUSED = 7  
    End Enum  
  
    <StructLayout(LayoutKind.Sequential)>  
    Public Structure ServiceStatus  
        Public dwServiceType As Long  
        Public dwCurrentState As ServiceState  
        Public dwControlsAccepted As Long  
        Public dwWin32ExitCode As Long  
        Public dwServiceSpecificExitCode As Long  
        Public dwCheckPoint As Long  
        Public dwWaitHint As Long  
    End Structure  
    ```  
  
3.  <span data-ttu-id="07c43-174">Deklarieren Sie jetzt in der `MyNewService` -Klasse die Funktion [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) durch einen Plattformaufruf:</span><span class="sxs-lookup"><span data-stu-id="07c43-174">Now, in the `MyNewService` class, declare the [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) by using platform invoke:</span></span>  
  
    ```csharp  
    [DllImport("advapi32.dll", SetLastError=true)]  
            private static extern bool SetServiceStatus(IntPtr handle, ref ServiceStatus serviceStatus);  
    ```  
  
    ```vb  
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean  
    ```  
  
4.  <span data-ttu-id="07c43-175">Um den Status Start ausstehend zu implementieren, fügen Sie den folgenden Code am Anfang der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="07c43-175">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>  
  
    ```csharp  
    // Update the service state to Start Pending.  
    ServiceStatus serviceStatus = new ServiceStatus();  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;  
    serviceStatus.dwWaitHint = 100000;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Start Pending.  
    Dim serviceStatus As ServiceStatus = New ServiceStatus()  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING  
    serviceStatus.dwWaitHint = 100000  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
5.  <span data-ttu-id="07c43-176">Fügen Sie den Code hinzu, um den Status Wird ausgeführt am Ende der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode festzulegen.</span><span class="sxs-lookup"><span data-stu-id="07c43-176">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>  
  
    ```csharp
    // Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
6.  <span data-ttu-id="07c43-177">(Optional) Wiederholen Sie diesen Vorgang für die <xref:System.ServiceProcess.ServiceBase.OnStop%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="07c43-177">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="07c43-178">Das Dialogfeld [Dienststeuerungs-Manager](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) verwendet die Member `dwWaitHint` und `dwCheckpoint` der [SERVICE_STATUS-Struktur](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) , um zu bestimmen, wie lange bis zum Starten oder Herunterfahren eines Windows-Diensts gewartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="07c43-178">The [Service Control Manager](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) to determine how much time to wait for a Windows Service to start or shut down.</span></span> <span data-ttu-id="07c43-179">Wenn Ihre <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> -Methoden eine lange Ausführungszeit haben, kann Ihr Dienst durch das erneute Aufrufen von [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) mit einem erhöhten `dwCheckPoint` -Wert mehr Zeit anfordern.</span><span class="sxs-lookup"><span data-stu-id="07c43-179">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) again with an incremented `dwCheckPoint` value.</span></span>  
  
<a name="BK_AddInstallers"></a>   
## <a name="adding-installers-to-the-service"></a><span data-ttu-id="07c43-180">Hinzufügen von Installern zum Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-180">Adding Installers to the Service</span></span>  
 <span data-ttu-id="07c43-181">Bevor Sie einen Windows-Dienst ausführen können, müssen Sie ihn bei der Installation im Dienststeuerungs-Manager registrieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-181">Before you can run a Windows Service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="07c43-182">Sie können Installationsprogramme dem Projekt hinzufügen, die die Registrierungsdetails behandelt.</span><span class="sxs-lookup"><span data-stu-id="07c43-182">You can add installers to your project that handle the registration details.</span></span>  
  
#### <a name="to-create-the-installers-for-your-service"></a><span data-ttu-id="07c43-183">So erstellen Sie die Installationsprogramme für den Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-183">To create the installers for your service</span></span>  
  
1.  <span data-ttu-id="07c43-184">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-184">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="07c43-185">Klicken Sie auf den Hintergrund des Designers, um den Dienst selbst, nicht Elemente seines Inhalts, zu markieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-185">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>  
  
3.  <span data-ttu-id="07c43-186">Öffnen Sie das Kontextmenü für das Designer-Fenster (wenn Sie ein Zeigegerät verwenden, rechtsklicken Sie in das Fenster) und wählen Sie dann **Installer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="07c43-186">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>  
  
     <span data-ttu-id="07c43-187">Standardmäßig wird dem Projekt eine Komponentenklasse mit zwei Installationsprogrammen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="07c43-187">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="07c43-188">Die Komponente erhält den Namen **ProjectInstaller**; die darin enthaltenen Installationsprogramme sind zum einen das Installationsprogramm für den Dienst und zum andern das Installationsprogramm für den zugeordneten Prozess des Diensts.</span><span class="sxs-lookup"><span data-stu-id="07c43-188">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>  
  
4.  <span data-ttu-id="07c43-189">Klicken Sie in der Ansicht **Entwurf** für **ProjectInstaller**auf **ServiceInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt, bzw. auf **serviceInstaller1** , wenn es sich um ein Visual C#-Projekt handelt.</span><span class="sxs-lookup"><span data-stu-id="07c43-189">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>  
  
5.  <span data-ttu-id="07c43-190">Vergewissern Sie sich im Fenster **Eigenschaften** , dass die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft auf **MyNewService**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-190">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>  
  
6.  <span data-ttu-id="07c43-191">Legen Sie die **Beschreibung** -Eigenschaft auf Text, wie z. B. "Ein Beispieldienst" fest.</span><span class="sxs-lookup"><span data-stu-id="07c43-191">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="07c43-192">Dieser Text wird im Fenster Dienste angezeigt und hilft dem Benutzer den Dienst zu identifizieren, und zu verstehen, wofür er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-192">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>  
  
7.  <span data-ttu-id="07c43-193">Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> -Eigenschaft auf den Text fest, der im Fenster Dienste in der Spalte **Name** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07c43-193">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="07c43-194">Beispielsweise können Sie "MyNewService Display Name" eingeben.</span><span class="sxs-lookup"><span data-stu-id="07c43-194">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="07c43-195">Dieser Name kann sich von der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft unterscheidet, die dem Namen entspricht, der vom System verwendet wird (z. B. bei Verwendung des `net start` -Befehls zum Starten des Dienstes).</span><span class="sxs-lookup"><span data-stu-id="07c43-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>  
  
8.  <span data-ttu-id="07c43-196">Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf <xref:System.ServiceProcess.ServiceStartMode.Automatic> fest.</span><span class="sxs-lookup"><span data-stu-id="07c43-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>  
  
     <span data-ttu-id="07c43-197">![Installer-Eigenschaften für einen Windows-Dienst](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "Windows-Installer-Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="07c43-197">![Installer Properties for a Windows Service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>  
  
9. <span data-ttu-id="07c43-198">Klicken Sie im Designer auf **ServiceProcessInstaller1** , wenn es sich um ein Visual Basic#-Projekt handelt, bzw. auf **serviceProcessInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt.</span><span class="sxs-lookup"><span data-stu-id="07c43-198">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="07c43-199">Legen Sie die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>-Eigenschaft auf <xref:System.ServiceProcess.ServiceAccount.LocalSystem> fest.</span><span class="sxs-lookup"><span data-stu-id="07c43-199">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="07c43-200">Dadurch wird der Dienst installiert und auf einem lokalen Dienstkonto ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="07c43-200">This will cause the service to be installed and to run on a local service account.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="07c43-201">Das Konto <xref:System.ServiceProcess.ServiceAccount.LocalSystem> verfügt über ein breites Berechtigungsspektrum, einschließlich der Berechtigung zum Schreiben in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="07c43-201">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="07c43-202">Bei der Verwendung dieses Kontos ist allerdings Vorsicht geboten, da sich dadurch das Risiko von Malware-Angriffen erhöhen kann.</span><span class="sxs-lookup"><span data-stu-id="07c43-202">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="07c43-203">Für andere Aufgaben sollten Sie das Konto <xref:System.ServiceProcess.ServiceAccount.LocalService> verwenden, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden anonyme Anmeldeinformationen übergeben.</span><span class="sxs-lookup"><span data-stu-id="07c43-203">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="07c43-204">Dieses Beispiel schlägt fehl, wenn Sie versuchen, das <xref:System.ServiceProcess.ServiceAccount.LocalService>-Konto zu verwenden, da zum Schreiben in das Ereignisprotokoll eine Genehmigung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-204">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>  
  
     <span data-ttu-id="07c43-205">Weitere Informationen zu Installern finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="07c43-205">For more information about installers, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
<a name="BK_StartupParameters"></a>   
## <a name="set-startup-parameters"></a><span data-ttu-id="07c43-206">Einstellung der Startparameter</span><span class="sxs-lookup"><span data-stu-id="07c43-206">Set Startup Parameters</span></span>  
 <span data-ttu-id="07c43-207">Ein Windows-Dienst akzeptiert wie jede andere ausführbare Datei Befehlszeilenargumente oder Startparameter.</span><span class="sxs-lookup"><span data-stu-id="07c43-207">A Windows Service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="07c43-208">Wenn Sie einen Code zum Startparameterprozess hinzufügen, können Benutzer den Dienst mithilfe des Fensters "Dienste" in der Windows-Systemsteuerung mit ihren eigenen benutzerdefinierten Startparametern starten.</span><span class="sxs-lookup"><span data-stu-id="07c43-208">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="07c43-209">Diese Startparameter werden jedoch nicht beim nächsten Start des Dienst beibehalten.</span><span class="sxs-lookup"><span data-stu-id="07c43-209">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="07c43-210">Um Startparameter dauerhaft festzulegen, können Sie diese in der Registrierung festlegen, wie in diesem Verfahren dargestellt.</span><span class="sxs-lookup"><span data-stu-id="07c43-210">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07c43-211">Bevor Sie sich entscheiden, die Startparameter hinzuzufügen, ziehen Sie in Betracht, ob dies die beste Möglichkeit für die Übertragung von Informationen an Ihren Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-211">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="07c43-212">Obwohl Startparameter einfach zu verwenden und zu analysieren sind, und sie Benutzer sie leicht überschreiben können, sind sie möglicherweise ohne die Dokumentation schwerer zu erkennen und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="07c43-212">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="07c43-213">In der Regel, wenn der Dienst mehr als nur ein paar Startparameter erfordert, sollten Sie stattdessen die Verwendung des Verzeichnisses oder einer Konfigurationsdatei erwägen.</span><span class="sxs-lookup"><span data-stu-id="07c43-213">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="07c43-214">Jeder Windows-Dienst ist ein Eintrag im Verzeichnis unter HKLM\System\CurrentControlSet\services.</span><span class="sxs-lookup"><span data-stu-id="07c43-214">Every Windows Service has an entry in the registry under HKLM\System\CurrentControlSet\services.</span></span> <span data-ttu-id="07c43-215">Gemäß dem Service-Schlüssel können Sie den Teilschlüssel **Parameter** zum Speichern von Informationen verwenden, auf die Ihr Dienst zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="07c43-215">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="07c43-216">Sie können Konfigurationsdateien für einen Windows-Dienst genauso wie für andere Arten von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="07c43-216">You can use application configuration files for a Windows Service the same way you do for other types of programs.</span></span> <span data-ttu-id="07c43-217">Beispielcode finden Sie unter <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="07c43-217">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>  
  
#### <a name="adding-startup-parameters"></a><span data-ttu-id="07c43-218">Hinzufügen von Startparametern</span><span class="sxs-lookup"><span data-stu-id="07c43-218">Adding startup parameters</span></span>  
  
1.  <span data-ttu-id="07c43-219">In der `Main` -Methode in Program.cs in MyNewService.Designer.vb fügen Sie ein Argument für die Befehlszeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="07c43-219">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an argument for the command line:</span></span>  
  
```csharp  
static void Main(string[] args)
{
    ServiceBase[] ServicesToRun = new ServiceBase[] { new MyNewService(args) };
    ServiceBase.Run(ServicesToRun);
}
```  
  
```vb
Shared Sub Main(ByVal cmdArgs() As String)
    Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
    System.ServiceProcess.ServiceBase.Run(ServicesToRun)
End Sub
```  
  
2.  <span data-ttu-id="07c43-220">Ändern Sie den `MyNewService` -Konstruktor wie folgt:</span><span class="sxs-lookup"><span data-stu-id="07c43-220">Change the `MyNewService` constructor as follows:</span></span>  
  
```csharp  
public MyNewService(string[] args)
{
    InitializeComponent();
    string eventSourceName = "MySource";
    string logName = "MyNewLog";
    if (args.Count() > 0) 
    {
        eventSourceName = args[0];
    }
    if (args.Count() > 1)
    {
        logName = args[1];
    }
    eventLog1 = new System.Diagnostics.EventLog();
    if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
    {
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
    }
    eventLog1.Source = eventSourceName;
    eventLog1.Log = logName;        
}
```  
  
```vb  
Public Sub New(ByVal cmdArgs() As String)
    InitializeComponent()
    Dim eventSourceName As String = "MySource"
    Dim logName As String = "MyNewLog"
    If (cmdArgs.Count() > 0) Then
        eventSourceName = cmdArgs(0)
    End If
    If (cmdArgs.Count() > 1) Then
        logName = cmdArgs(1)
    End If
    eventLog1 = New System.Diagnostics.EventLog()
    If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
    End If
    eventLog1.Source = eventSourceName
    eventLog1.Log = logName
End Sub  
```  
  
<span data-ttu-id="07c43-221">Dieser Code legt die Ereignisquelle und den Protokollnamen gemäß der angegebenen Startparameter fest oder verwendet Standardwerte, wenn keine Argumente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="07c43-221">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>  
  
3. <span data-ttu-id="07c43-222">Um Befehlszeilenargumente anzugeben, fügen Sie den folgenden Code zu der `ProjectInstaller` -Klasse in ProjectInstaller.cs oder ProjectInstaller.vb hinzu:</span><span class="sxs-lookup"><span data-stu-id="07c43-222">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>  
  
```csharp  
protected override void OnBeforeInstall(IDictionary savedState)
{
    string parameter = "MySource1\" \"MyLogFile1";
    Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
    base.OnBeforeInstall(savedState);
}
```

```vb  
Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
    Dim parameter As String = "MySource1"" ""MyLogFile1"
    Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
    MyBase.OnBeforeInstall(savedState)
End Sub  
```  
  
<span data-ttu-id="07c43-223">Dieser Code ändert den **ImagePath** -Registrierungsschlüssel, der in der Regel den vollständigen Pfad der ausführbaren Datei für den Windows-Dienst enthält, indem die Standardwerte für die Parameter hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="07c43-223">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows Service, by adding the default parameter values.</span></span> <span data-ttu-id="07c43-224">Die Anführungszeichen rund um den Pfad (und um jeden einzelnen Parameter) sind erforderlich, um den Dienst korrekt zu starten.</span><span class="sxs-lookup"><span data-stu-id="07c43-224">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="07c43-225">Um die Startparameter für diesen Windows-Dienst zu ändern, können Benutzer die Parameter ändern, die im **ImagePath** -Registrierungsschlüssel angegeben sind, obwohl es besser wäre, ihn programmgesteuert zu ändern und die Funktionalität für Benutzer in einer geeigneten Form (z. B. in einem Dienstprogramm Verwaltung oder Konfiguration) verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="07c43-225">To change the startup parameters for this Windows Service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>  
  
<a name="BK_Build"></a>   
## <a name="building-the-service"></a><span data-ttu-id="07c43-226">Erstellen des Dienstes</span><span class="sxs-lookup"><span data-stu-id="07c43-226">Building the Service</span></span>  
  
#### <a name="to-build-your-service-project"></a><span data-ttu-id="07c43-227">So erstellen Sie ein Dienstprojekt</span><span class="sxs-lookup"><span data-stu-id="07c43-227">To build your service project</span></span>  
  
1.  <span data-ttu-id="07c43-228">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-228">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span> <span data-ttu-id="07c43-229">Die Eigenschaftenseiten für Ihr Projekt werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="07c43-229">The property pages for your project  appear.</span></span>  
  
2.  <span data-ttu-id="07c43-230">Klicken Sie in der Registerkarte Anwendung in der Liste **Startobjekt** auf **MyNewService.Program**.</span><span class="sxs-lookup"><span data-stu-id="07c43-230">On the Application tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>  
  
3.  <span data-ttu-id="07c43-231">Im **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für das Projekt und wählen Sie dann **Erstellen** zum Erstellen des Projekts (Tastatur: STRG + UMSCHALT + B).</span><span class="sxs-lookup"><span data-stu-id="07c43-231">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (Keyboard: Ctrl+Shift+B).</span></span>  
  
<a name="BK_Install"></a>   
## <a name="installing-the-service"></a><span data-ttu-id="07c43-232">Installieren des Dienstes</span><span class="sxs-lookup"><span data-stu-id="07c43-232">Installing the Service</span></span>  
 <span data-ttu-id="07c43-233">Nachdem Sie den Windows-Dienst nun erstellt haben, können Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-233">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="07c43-234">Um einen Windows-Dienst zu installieren, müssen Sie über Administratorberechtigungen für den Computer verfügen, auf dem Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="07c43-234">To install a Windows service, you must have administrative credentials on the computer on which you're installing it.</span></span>  
  
#### <a name="to-install-a-windows-service"></a><span data-ttu-id="07c43-235">So installieren Sie einen Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-235">To install a Windows Service</span></span>  
  
1.  <span data-ttu-id="07c43-236">Öffnen Sie in Windows 7 und Windows Server die **Entwickler-Eingabeaufforderung** unter **Visual Studio Tools** im **Start** -Menü.</span><span class="sxs-lookup"><span data-stu-id="07c43-236">In Windows 7 and Windows Server, open the **Developer Command Prompt** under **Visual Studio Tools** in the **Start** menu.</span></span> <span data-ttu-id="07c43-237">In Windows 8 oder Windows 8.1 wählen Sie die Kachel **Visual Studio-Tools** auf dem **Start** -Bildschirm und führen Sie dann die Entwickler-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="07c43-237">In Windows 8 or Windows 8.1, choose the **Visual Studio Tools** tile on the **Start** screen, and then run Developer Command Prompt with administrative credentials.</span></span> <span data-ttu-id="07c43-238">(Wenn Sie eine Maus verwenden, rechtsklicken Sie auf **Entwickler-Eingabeaufforderung**und wählen Sie dann **als Administrator ausführen**.)</span><span class="sxs-lookup"><span data-stu-id="07c43-238">(If you’re using a mouse, right-click on **Developer Command Prompt**, and then choose **Run as Administrator**.)</span></span>  
  
2.  <span data-ttu-id="07c43-239">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei Ihre Projektausgabe enthält.</span><span class="sxs-lookup"><span data-stu-id="07c43-239">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="07c43-240">Wechseln Sie beispielsweise unter dem Ordner "Eigene Dateien" zu "Visual Studio 2013\Projects\MyNewService\bin\Debug".</span><span class="sxs-lookup"><span data-stu-id="07c43-240">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="07c43-241">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="07c43-241">Enter the following command:</span></span>  
  
    ```  
    installutil.exe MyNewService.exe  
    ```  
  
     <span data-ttu-id="07c43-242">Wenn der Dienst erfolgreich installiert ist, wird dies von installutil.exe gemeldet.</span><span class="sxs-lookup"><span data-stu-id="07c43-242">If the service installs successfully, installutil.exe will report success.</span></span> <span data-ttu-id="07c43-243">Wenn das System InstallUtil.exe nicht finden kann, stellen Sie sicher, dass sie auf Ihrem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-243">If the system could not find InstallUtil.exe, make sure that it exists on your computer.</span></span> <span data-ttu-id="07c43-244">Dieses Tool wird mit dem.NET Framework im Ordner `%WINDIR%\Microsoft.NET\Framework[64]\`*Framework_version*installiert.</span><span class="sxs-lookup"><span data-stu-id="07c43-244">This tool is installed with the .NET Framework to the folder `%WINDIR%\Microsoft.NET\Framework[64]\`*framework_version*.</span></span> <span data-ttu-id="07c43-245">Beispielsweise lautet der Standardpfad für die 32-Bit-Version von der.NET Framework 4, 4.5, 4.5.1 und 4.5.2 `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="07c43-245">For example, the default path for the 32-bit version of the .NET Framework 4, 4.5, 4.5.1, and 4.5.2 is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span>  
  
     <span data-ttu-id="07c43-246">Wenn der Prozess „installutil.exe“ Fehler meldet, überprüfen Sie das Installationsprotokoll, um die Gründe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="07c43-246">If the installutil.exe process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="07c43-247">Standardmäßig befindet sich das Protokoll im gleichen Ordner wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="07c43-247">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="07c43-248">Bei der Installation kann ein Fehler auftreten, wenn die <xref:System.ComponentModel.RunInstallerAttribute>-Klasse nicht in der `ProjectInstaller`-Klasse vorhanden ist, das Attribut nicht auf `true` festgelegt ist oder die `ProjectInstaller`-Klasse nicht `public` ist.</span><span class="sxs-lookup"><span data-stu-id="07c43-248">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, or else the attribute is not set to `true`, or else the `ProjectInstaller` class is not `public`.</span></span>  
  
     <span data-ttu-id="07c43-249">Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="07c43-249">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
<a name="BK_StartService"></a>   
## <a name="starting-and-running-the-service"></a><span data-ttu-id="07c43-250">Starten und Ausführen des Dienstes</span><span class="sxs-lookup"><span data-stu-id="07c43-250">Starting and Running the Service</span></span>  
  
#### <a name="to-start-and-stop-your-service"></a><span data-ttu-id="07c43-251">So starten und beenden Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-251">To start and stop your service</span></span>  
  
1.  <span data-ttu-id="07c43-252">Öffnen Sie in Windows den Bildschirm **Starten** oder das **Start** -Menü, und geben Sie `services.msc`ein.</span><span class="sxs-lookup"><span data-stu-id="07c43-252">In Windows, open the **Start** screen or **Start** menu, and type `services.msc`.</span></span>  
  
     <span data-ttu-id="07c43-253">**MyNewService** müsste jetzt im Fenster **Dienste** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07c43-253">You should now see **MyNewService** listed in the **Services** window.</span></span>  
  
     <span data-ttu-id="07c43-254">![MyNewService im Fenster „Dienste“. ](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "Windows_Fenster „Dienste“")</span><span class="sxs-lookup"><span data-stu-id="07c43-254">![MyNewService in the Services window.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")</span></span>  
  
2.  <span data-ttu-id="07c43-255">Im Fenster **Dienste** öffnen Sie das Kontextmenü für den Dienst und wählen Sie dann **Start**.</span><span class="sxs-lookup"><span data-stu-id="07c43-255">In the **Services** window, open the shortcut menu for your service, and then choose **Start**.</span></span>  
  
3.  <span data-ttu-id="07c43-256">Öffnen Sie das Kontextmenü für den Dienst und wählen Sie dann **Stopp**aus.</span><span class="sxs-lookup"><span data-stu-id="07c43-256">Open the shortcut menu for the service, and then choose **Stop**.</span></span>  
  
4.  <span data-ttu-id="07c43-257">(Optional) An der Befehlszeile können Sie die Befehle `net start``ServiceName` und `net stop``ServiceName` zum Starten und Beenden Ihres Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="07c43-257">(Optional) From the command line, you can use the commands `net start``ServiceName` and `net stop``ServiceName` to start and stop your service.</span></span>  
  
#### <a name="to-verify-the-event-log-output-of-your-service"></a><span data-ttu-id="07c43-258">So überprüfen Sie die Ereignisprotokollausgabe des Diensts</span><span class="sxs-lookup"><span data-stu-id="07c43-258">To verify the event log output of your service</span></span>  
  
1.  <span data-ttu-id="07c43-259">Öffnen Sie in VIsual Studio **Server-Explorer** (Tastatur: STRG+ALT+S) und greifen Sie auf den Knoten **Ereignisprotokolle** für den lokalen Computer zu.</span><span class="sxs-lookup"><span data-stu-id="07c43-259">In Visual Studio, open **Server Explorer** (Keyboard: Ctrl+Alt+S), and access the **Event Logs** node for the local computer.</span></span>  
  
2.  <span data-ttu-id="07c43-260">Suchen Sie den Eintrag für **MyNewLog** (oder **MyLogFile1**, wenn Sie das optionale Verfahren verwenden, um Befehlszeilenargumente hinzuzufügen), und erweitern Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="07c43-260">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you used the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="07c43-261">Sie sehen Einträge für die beiden Aktionen (Start und Stopp), die Ihr Dienst ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="07c43-261">You should see entries for the two actions (start and stop) your service has performed.</span></span>  
  
     <span data-ttu-id="07c43-262">![Verwenden Sie die Ereignisanzeige, um die Einträge im Ereignisprotokoll anzuzeigen.](../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "Windows_Ereignisanzeige")</span><span class="sxs-lookup"><span data-stu-id="07c43-262">![Use the Event Viewer to see the event log entries.](../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")</span></span>  
  
<a name="BK_Uninstall"></a>   
## <a name="uninstalling-a-windows-service"></a><span data-ttu-id="07c43-263">Ein Windowsdienst wird deinstalliert...</span><span class="sxs-lookup"><span data-stu-id="07c43-263">Uninstalling a Windows Service</span></span>  
  
#### <a name="to-uninstall-your-service"></a><span data-ttu-id="07c43-264">So deinstallieren Sie einen Dienst</span><span class="sxs-lookup"><span data-stu-id="07c43-264">To uninstall your service</span></span>  
  
1.  <span data-ttu-id="07c43-265">Öffnen Sie eine Eingabeaufforderung für Entwickler mit administrativen Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="07c43-265">Open a developer command prompt with administrative credentials.</span></span>  
  
2.  <span data-ttu-id="07c43-266">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Datei Ihre Projektausgabe enthält.</span><span class="sxs-lookup"><span data-stu-id="07c43-266">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="07c43-267">Wechseln Sie beispielsweise unter dem Ordner "Eigene Dateien" zu "Visual Studio 2013\Projects\MyNewService\bin\Debug".</span><span class="sxs-lookup"><span data-stu-id="07c43-267">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="07c43-268">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="07c43-268">Enter the following command:</span></span>  
  
    ```  
    installutil.exe /u MyNewService.exe  
    ```  
  
     <span data-ttu-id="07c43-269">Wenn der Dienst erfolgreich deinstalliert ist, meldet installutil.exe, dass der Dienst erfolgreich entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="07c43-269">If the service uninstalls successfully, installutil.exe will report that your service was successfully removed.</span></span> <span data-ttu-id="07c43-270">Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="07c43-270">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="07c43-271">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="07c43-271">Next Steps</span></span>  
 <span data-ttu-id="07c43-272">Sie können ein eigenständiges Setupprogramm erstellen, mit dem andere Ihren Windows-Dienst installieren können, aber es sind zusätzliche Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="07c43-272">You can create a standalone setup program that others can use to install your Windows service, but it requires additional steps.</span></span> <span data-ttu-id="07c43-273">ClickOnce unterstützt Windows-Dienste nicht, deshalb können Sie den Webpublishing-Assistenten nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="07c43-273">ClickOnce doesn't support Windows services, so you can't use the Publish Wizard.</span></span> <span data-ttu-id="07c43-274">Sie können eine Vollversion von InstallShield verwenden, die Microsoft nicht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="07c43-274">You can use a full edition of InstallShield, which Microsoft doesn't provide.</span></span> <span data-ttu-id="07c43-275">Weitere Informationen zu InstallShield finden Sie unter [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition).</span><span class="sxs-lookup"><span data-stu-id="07c43-275">For more information about InstallShield, see [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition).</span></span> <span data-ttu-id="07c43-276">Ein Installationsprogramm für einen Windows-Dienst lässt sich auch mit dem [Windows Installer XML-Toolset](http://go.microsoft.com/fwlink/?LinkId=249067) erstellen.</span><span class="sxs-lookup"><span data-stu-id="07c43-276">You can also use the [Windows Installer XML Toolset](http://go.microsoft.com/fwlink/?LinkId=249067) to create an installer for a Windows service.</span></span>  
  
 <span data-ttu-id="07c43-277">Sie können eine <xref:System.ServiceProcess.ServiceController> -Komponente verwenden, um Befehle an den von Ihnen installierten Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="07c43-277">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you have installed.</span></span>  
  
 <span data-ttu-id="07c43-278">Sie können ein Installationsprogramm verwenden, um ein Ereignisprotokoll während der Installation statt während der Ausführung der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="07c43-278">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="07c43-279">Außerdem wird das Ereignisprotokoll vom Installationsprogramm gelöscht, wenn die Anwendung deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="07c43-279">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="07c43-280">Weitere Informationen finden Sie auf der Referenzseite <xref:System.Diagnostics.EventLogInstaller> .</span><span class="sxs-lookup"><span data-stu-id="07c43-280">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c43-281">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07c43-281">See Also</span></span>  
 [<span data-ttu-id="07c43-282">Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="07c43-282">Windows Service Applications</span></span>](../../../docs/framework/windows-services/index.md)  
 [<span data-ttu-id="07c43-283">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="07c43-283">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="07c43-284">Vorgehensweise: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="07c43-284">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="07c43-285">Dienste (Windows)</span><span class="sxs-lookup"><span data-stu-id="07c43-285">Services (Windows)</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
