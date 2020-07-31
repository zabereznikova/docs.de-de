---
title: 'Tutorial: Erstellen einer Windows-Dienst-App'
description: In diesem Tutorial wird beschrieben, wie Sie eine Windows-Dienst-App in Visual Studio erstellen, die Meldungen in ein Ereignisprotokoll schreibt. Features hinzufügen, Status festlegen, Installationsprogramme hinzufügen usw.
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 487a974af2280a02b83fe685324c9464df705585
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925630"
---
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="2dadd-104">Tutorial: Erstellen einer Windows-Dienst-App</span><span class="sxs-lookup"><span data-stu-id="2dadd-104">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="2dadd-105">In diesem Artikel wird beschrieben, wie Sie eine Windows-Dienstanwendung in Visual Studio erstellen, die Meldungen in ein Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-105">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="2dadd-106">Erstellen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-106">Create a service</span></span>

<span data-ttu-id="2dadd-107">Erstellen Sie zunächst das Projekt, und legen Sie die Werte fest, die für die korrekte Funktion des Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2dadd-107">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="2dadd-108">Wählen Sie in Visual Studio auf der Menüleiste **Datei** **Neu** > **Projekt** aus (oder drücken Sie **STRG**+**UMSCHALT**+**N**), um das Fenster **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-108">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="2dadd-109">Navigieren Sie zur Projektvorlage **Windows-Dienst (.NET Framework)** , und wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-109">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="2dadd-110">Sie finden diese, indem Sie **Installiert** und **Visual C#** aufklappen oder **Visual Basic**, und dann **Windows-Desktop** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-110">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="2dadd-111">Alternativ können Sie im Suchfeld oben rechts *Windows-Dienst* eingeben und die **EINGABETASTE** drücken.</span><span class="sxs-lookup"><span data-stu-id="2dadd-111">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Windows-Dienstvorlage im Dialogfeld „Neues Projekt“ in Visual Studio](./media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="2dadd-113">Wenn Sie die Vorlage **Windows-Dienst** nicht finden können, müssen Sie möglicherweise die Workload **.NET-Desktopentwicklung** installieren:</span><span class="sxs-lookup"><span data-stu-id="2dadd-113">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >
   > <span data-ttu-id="2dadd-114">Wählen Sie im Dialogfeld **Neues Projekt** im unteren linken Bereich **Visual Studio-Installer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-114">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="2dadd-115">Wählen Sie die Workload **.NET-Desktopentwicklung** aus, und klicken Sie anschließend auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-115">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="2dadd-116">Geben Sie als \**Name\*\*\*MyNewService* ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-116">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="2dadd-117">Die Registerkarte **Design** wird angezeigt (**Service1.cs [Design]** oder **Service1.vb [Design]** ).</span><span class="sxs-lookup"><span data-stu-id="2dadd-117">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>

   <span data-ttu-id="2dadd-118">Die Projektvorlage beinhaltet eine Komponentenklasse mit dem Namen `Service1`, die von <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erbt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-118">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2dadd-119">Sie enthält einen großen Teil des grundlegenden Dienstcodes, etwa den Code zum Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2dadd-119">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="2dadd-120">Umbenennen des Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-120">Rename the service</span></span>

<span data-ttu-id="2dadd-121">Benennen Sie den Dienst von **Service1** in **MyNewService** um.</span><span class="sxs-lookup"><span data-stu-id="2dadd-121">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="2dadd-122">Wählen Sie im **Projektmappen-Explorer** die Datei **Service1.cs** oder **Service1.vb** aus, und klicken Sie im Kontextmenü auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-122">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="2dadd-123">Nennen Sie die Datei um in **MyNewService.cs** oder **MyNewService.vb**, und drücken Sie dann die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-123">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="2dadd-124">Daraufhin wird ein Popupfenster angezeigt, in dem Sie gefragt werden, ob Sie alle Verweise auf das Codeelement *Service1* umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-124">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="2dadd-125">Wählen Sie im Popupfenster **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-125">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="2dadd-126">![Eingabeaufforderung zum Umbenennen](./media/windows-service-rename.png "Eingabeaufforderung zum Umbenennen eines Windows-Diensts")</span><span class="sxs-lookup"><span data-stu-id="2dadd-126">![Rename prompt](./media/windows-service-rename.png "Windows service rename prompt")</span></span>

3. <span data-ttu-id="2dadd-127">Wählen Sie in der Registerkarte **Design** aus dem Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-127">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="2dadd-128">Ändern Sie im Fenster **Eigenschaften** den Wert für **ServiceName** in *MyNewService*.</span><span class="sxs-lookup"><span data-stu-id="2dadd-128">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="2dadd-129">![Diensteigenschaften](./media/windows-service-properties.png "Eigenschaften des Windows-Diensts")</span><span class="sxs-lookup"><span data-stu-id="2dadd-129">![Service properties](./media/windows-service-properties.png "Windows service properties")</span></span>

4. <span data-ttu-id="2dadd-130">Wählen Sie im Menü **Datei** die Option **Alle speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-130">Select **Save All** from the **File** menu.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="2dadd-131">Hinzufügen von Features zum Dienst</span><span class="sxs-lookup"><span data-stu-id="2dadd-131">Add features to the service</span></span>

<span data-ttu-id="2dadd-132">In diesem Abschnitt fügen Sie dem Windows-Dienst ein benutzerdefiniertes Ereignisprotokoll hinzu.</span><span class="sxs-lookup"><span data-stu-id="2dadd-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="2dadd-133">Die <xref:System.Diagnostics.EventLog>-Komponente wird als Beispiel für die Art von Komponente verwendet, die Sie einem Windows-Dienst hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="2dadd-133">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="2dadd-134">Hinzufügen einer benutzerdefinierten Ereignisprotokollfunktion</span><span class="sxs-lookup"><span data-stu-id="2dadd-134">Add custom event log functionality</span></span>

1. <span data-ttu-id="2dadd-135">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="2dadd-136">Erweitern Sie in der **Toolbox** die Option **Komponenten**, und ziehen Sie dann die **EventLog**-Komponente in eine der Registerkarten **Service1.cs [Design]** oder **Service1.vb [Design]** .</span><span class="sxs-lookup"><span data-stu-id="2dadd-136">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="2dadd-137">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-137">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="2dadd-138">Definieren Sie ein benutzerdefiniertes Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2dadd-138">Define a custom event log.</span></span> <span data-ttu-id="2dadd-139">Für C# bearbeiten Sie den vorhandenen `MyNewService()`-Konstruktor; für Visual Basic wird der `New()`-Konstruktor hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="2dadd-139">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="2dadd-140">Fügen Sie den <xref:System.Diagnostics?displayProperty=nameWithType>-Namespace hinzu, indem Sie (sofern diese nicht bereits vorhanden ist) die `using`-Anweisung in der Datei **MyNewService.cs** bzw. die `Imports`-Anweisung in der Datei **MyNewService.vb** verwenden:</span><span class="sxs-lookup"><span data-stu-id="2dadd-140">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="2dadd-141">Wählen Sie im Menü **Datei** die Option **Alle speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-141">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="2dadd-142">Definieren, was beim Starten des Diensts ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="2dadd-142">Define what occurs when the service starts</span></span>

<span data-ttu-id="2dadd-143">Suchen Sie im Code-Editor für **MyNewService.cs** oder **MyNewService.vb** die <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode; Visual Studio hat beim Erstellen des Projekts automatisch eine leere Methodendefinition erstellt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-143">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="2dadd-144">Fügen Sie Code hinzu, der beim Starten des Diensts einen Eintrag in das Ereignisprotokoll schreibt:</span><span class="sxs-lookup"><span data-stu-id="2dadd-144">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="2dadd-145">Abrufen</span><span class="sxs-lookup"><span data-stu-id="2dadd-145">Polling</span></span>

<span data-ttu-id="2dadd-146">Da eine Dienstanwendung mit langer Laufzeit entworfen wird, fragt sie in der Regel das System ab oder überwacht es. Dies haben Sie in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="2dadd-146">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="2dadd-147">Die `OnStart`-Methode muss zum Betriebssystem zurückkehren, sobald die Ausführung des Dienstes begonnen hat, damit das System nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="2dadd-147">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span>

<span data-ttu-id="2dadd-148">Mit der <xref:System.Timers.Timer?displayProperty=nameWithType>-Komponente können Sie einen einfachen Abrufmechanismus einrichten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-148">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="2dadd-149">Der Timer löst in regelmäßigen Intervallen ein <xref:System.Timers.Timer.Elapsed>-Ereignis aus. Zu diesem Zeitpunkt kann Ihr Dienst die Überwachung durchführen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-149">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="2dadd-150">Sie verwenden die <xref:System.Timers.Timer>-Komponente folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="2dadd-150">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="2dadd-151">Legen Sie die Eigenschaften der <xref:System.Timers.Timer>-Komponente in der `MyNewService.OnStart`-Methode fest.</span><span class="sxs-lookup"><span data-stu-id="2dadd-151">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="2dadd-152">Starten Sie den Timer durch Aufrufen der <xref:System.Timers.Timer.Start%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="2dadd-152">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="2dadd-153">Richten sie den Abrufmechanismus ein.</span><span class="sxs-lookup"><span data-stu-id="2dadd-153">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="2dadd-154">Fügen Sie im `MyNewService.OnStart`-Ereignis den folgenden Code ein, um den Abrufmechanismus einzurichten:</span><span class="sxs-lookup"><span data-stu-id="2dadd-154">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <span data-ttu-id="2dadd-155">Fügen Sie den <xref:System.Timers?displayProperty=nameWithType>-Namespace hinzu, indem Sie die `using`-Anweisung in der Datei **MyNewService.cs** bzw. die `Imports`-Anweisung in der Datei **MyNewService.vb** verwenden:</span><span class="sxs-lookup"><span data-stu-id="2dadd-155">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. <span data-ttu-id="2dadd-156">Fügen Sie der `MyNewService`-Klasse die `OnTimer`-Methode hinzu, um das <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType>-Ereignis zu verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="2dadd-156">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
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

4. <span data-ttu-id="2dadd-157">Fügen Sie der `MyNewService`-Klasse eine Membervariable hinzu.</span><span class="sxs-lookup"><span data-stu-id="2dadd-157">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="2dadd-158">Sie enthält den Bezeichner des nächsten Ereignisses, das in das Ereignisprotokoll geschrieben werden soll:</span><span class="sxs-lookup"><span data-stu-id="2dadd-158">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="2dadd-159">Anstatt alle Aufgaben auf dem Hauptthread auszuführen, können Sie Aufgaben mithilfe von Arbeitsthreads im Hintergrund ausführen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-159">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="2dadd-160">Weitere Informationen finden Sie unter <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2dadd-160">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="2dadd-161">Definieren, was beim Beenden des Diensts ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="2dadd-161">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="2dadd-162">Fügen Sie der Methode <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine Codezeile hinzu, die beim Beenden des Diensts einen Eintrag zum Ereignisprotokoll hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="2dadd-162">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="2dadd-163">Definieren weiterer Aktionen für den Dienst</span><span class="sxs-lookup"><span data-stu-id="2dadd-163">Define other actions for the service</span></span>

<span data-ttu-id="2dadd-164">Sie können die Methoden <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> und <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> überschreiben, um zusätzliche Verarbeitungsschritte für Ihre Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2dadd-164">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>

<span data-ttu-id="2dadd-165">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>-Methode in der `MyNewService`-Klasse überschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="2dadd-165">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a><span data-ttu-id="2dadd-166">Festlegen des Dienststatus</span><span class="sxs-lookup"><span data-stu-id="2dadd-166">Set service status</span></span>

<span data-ttu-id="2dadd-167">Dienste melden ihren Status an den [Dienststeuerungs-Manager](/windows/desktop/Services/service-control-manager), damit Benutzer erkennen können, ob ein Dienst ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2dadd-167">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="2dadd-168">Standardmäßig meldet ein Dienst, der von <xref:System.ServiceProcess.ServiceBase> erbt, eine begrenzte Anzahl von Statuseinstellungen. Dazu gehören SERVICE_STOPPED, SERVICE_PAUSED und SERVICE_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="2dadd-168">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="2dadd-169">Wenn es etwas länger dauert, bis ein Dienst startet, kann es hilfreich sein, den Status SERVICE_START_PENDING zu melden.</span><span class="sxs-lookup"><span data-stu-id="2dadd-169">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span>

<span data-ttu-id="2dadd-170">Sie können auch die Statuseinstellungen SERVICE_START_PENDING und SERVICE_STOP_PENDING durch Hinzufügen von Code implementieren, der in Windows die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) aufruft.</span><span class="sxs-lookup"><span data-stu-id="2dadd-170">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>

### <a name="implement-service-pending-status"></a><span data-ttu-id="2dadd-171">Implementieren des Dienststatus SERVICE_PENDING</span><span class="sxs-lookup"><span data-stu-id="2dadd-171">Implement service pending status</span></span>

1. <span data-ttu-id="2dadd-172">Fügen Sie den <xref:System.Runtime.InteropServices?displayProperty=nameWithType>-Namespace hinzu, indem Sie die `using`-Anweisung in der Datei **MyNewService.cs** bzw. die `Imports`-Anweisung in der Datei **MyNewService.vb** verwenden:</span><span class="sxs-lookup"><span data-stu-id="2dadd-172">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="2dadd-173">Fügen Sie **MyNewService.cs** bzw. **MyNewService.vb** folgenden Code hinzu, um die `ServiceState`-Werte zu deklarieren und um eine Struktur für den Status hinzuzufügen, die Sie in einem Plattformaufruf verwenden:</span><span class="sxs-lookup"><span data-stu-id="2dadd-173">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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

    > [!NOTE]
    > <span data-ttu-id="2dadd-174">Der Dienststeuerungs-Manager verwendet die Member `dwWaitHint` und `dwCheckpoint` der [SERVICE_STATUS-Struktur](/windows/win32/api/winsvc/ns-winsvc-service_status), um zu bestimmen, wie lange bis zum Starten oder Herunterfahren eines Windows-Diensts gewartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="2dadd-174">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/win32/api/winsvc/ns-winsvc-service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="2dadd-175">Wenn Ihre Methoden `OnStart` und `OnStop` eine lange Ausführungszeit haben, kann Ihr Dienst durch das erneute Aufrufen von `SetServiceStatus` mit einem erhöhten `dwCheckPoint`-Wert mehr Zeit anfordern.</span><span class="sxs-lookup"><span data-stu-id="2dadd-175">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

3. <span data-ttu-id="2dadd-176">Deklarieren Sie nun in der Klasse `MyNewService` die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mithilfe eines [Plattformaufrufs](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="2dadd-176">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="2dadd-177">Soll der Status Start SERVICE_START_PENDING implementiert werden, fügen Sie den folgenden Code am Anfang der <xref:System.ServiceProcess.ServiceBase.OnStart%2A>-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="2dadd-177">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="2dadd-178">Fügen Sie am Ende der `OnStart`-Methode Code hinzu, um den Status SERVICE_RUNNING festzulegen:</span><span class="sxs-lookup"><span data-stu-id="2dadd-178">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

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

6. <span data-ttu-id="2dadd-179">(Optional) Wenn <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine Methode mit langer Laufzeit ist, wiederholen Sie diese Prozedur in der Methode `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="2dadd-179">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="2dadd-180">Implementieren Sie den Status SERVICE_STOP_PENDING und geben Sie den SERVICE_STOPPED-Status zurück, bevor die `OnStop`-Methode endet.</span><span class="sxs-lookup"><span data-stu-id="2dadd-180">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="2dadd-181">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2dadd-181">For example:</span></span>

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

## <a name="add-installers-to-the-service"></a><span data-ttu-id="2dadd-182">Hinzufügen von Installern zum Dienst</span><span class="sxs-lookup"><span data-stu-id="2dadd-182">Add installers to the service</span></span>

<span data-ttu-id="2dadd-183">Bevor Sie einen Windows-Dienst ausführen können, müssen Sie ihn bei der Installation im Dienststeuerungs-Manager registrieren.</span><span class="sxs-lookup"><span data-stu-id="2dadd-183">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="2dadd-184">Sie können Ihrem Projekt Installer hinzufügen, um die Registrierungsdetails zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-184">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="2dadd-185">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-185">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="2dadd-186">Wählen Sie in der Ansicht **Design** den Hintergrundbereich aus, und wählen Sie dann im Kontextmenü **Installer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-186">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="2dadd-187">Standardmäßig fügt Visual Studio Ihrem Projekt eine Komponentenklasse namens `ProjectInstaller` hinzu, die zwei Installer beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="2dadd-187">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="2dadd-188">Diese Installer sind für Ihren Dienst und den zum Dienst gehörigen Prozess bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-188">These installers are for your service and for the service's associated process.</span></span>

3. <span data-ttu-id="2dadd-189">Klicken Sie in der Ansicht **Design** für **ProjectInstaller** auf **serviceInstaller1**, wenn es sich um ein Visual C#-Projekt handelt, bzw. auf **ServiceInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt, und wählen Sie dann im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-189">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="2dadd-190">Vergewissern Sie sich im Fenster **Eigenschaften**, dass die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>-Eigenschaft auf **MyNewService** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2dadd-190">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

5. <span data-ttu-id="2dadd-191">Fügen Sie der <xref:System.ServiceProcess.ServiceInstaller.Description%2A>-Eigenschaft Text hinzu, z. B. *Ein Beispieldienst*.</span><span class="sxs-lookup"><span data-stu-id="2dadd-191">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span>

     <span data-ttu-id="2dadd-192">Dieser Text wird im Fenster **Dienste** in der Spalte **Beschreibung** angezeigt und beschreibt den Dienst für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2dadd-192">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="2dadd-193">![Dienstbeschreibung im Fenster „Dienste“](./media/windows-service-description.png "Dienstbeschreibung")</span><span class="sxs-lookup"><span data-stu-id="2dadd-193">![Service description in the Services window.](./media/windows-service-description.png "Service description")</span></span>

6. <span data-ttu-id="2dadd-194">Fügen Sie in der <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A>-Eigenschaft Text hinzu,</span><span class="sxs-lookup"><span data-stu-id="2dadd-194">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="2dadd-195">z. B. *MyNewService-Anzeigename*.</span><span class="sxs-lookup"><span data-stu-id="2dadd-195">For example, *MyNewService Display Name*.</span></span>

     <span data-ttu-id="2dadd-196">Dieser Text wird im Fenster **Dienste** in der Spalte **Anzeigename** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-196">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="2dadd-197">Dieser Name kann sich von der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>-Eigenschaft unterscheiden, die dem Namen entspricht, der vom System verwendet wird (z. B. bei Verwendung des `net start`-Befehls zum Starten des Diensts).</span><span class="sxs-lookup"><span data-stu-id="2dadd-197">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

7. <span data-ttu-id="2dadd-198">Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft über die Dropdownliste auf <xref:System.ServiceProcess.ServiceStartMode.Automatic> fest.</span><span class="sxs-lookup"><span data-stu-id="2dadd-198">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

8. <span data-ttu-id="2dadd-199">Wenn Sie diesen Vorgang abgeschlossen haben, sollte das **Eigenschaften**-Fenster der folgenden Abbildung entsprechen:</span><span class="sxs-lookup"><span data-stu-id="2dadd-199">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="2dadd-200">![Installer-Eigenschaften für einen Windows-Dienst](./media/windows-service-installer-properties.png "Installer-Eigenschaften des Windows-Diensts")</span><span class="sxs-lookup"><span data-stu-id="2dadd-200">![Installer Properties for a Windows service](./media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="2dadd-201">Klicken Sie in der Ansicht **Design** für **ProjectInstaller** auf **serviceProcessInstaller1**, wenn es sich um ein Visual C#-Projekt handelt, bzw. auf **ServiceProcessInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt, und wählen Sie dann im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-201">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="2dadd-202">Legen Sie die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>-Eigenschaft über die Dropdownliste auf <xref:System.ServiceProcess.ServiceAccount.LocalSystem> fest.</span><span class="sxs-lookup"><span data-stu-id="2dadd-202">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span>

     <span data-ttu-id="2dadd-203">Diese Einstellung installiert den Dienst und führt ihn mithilfe des lokalen Systemkontos aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-203">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2dadd-204">Das Konto <xref:System.ServiceProcess.ServiceAccount.LocalSystem> verfügt über ein breites Berechtigungsspektrum, einschließlich der Berechtigung zum Schreiben in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="2dadd-204">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="2dadd-205">Bei der Verwendung dieses Kontos ist allerdings Vorsicht geboten, da sich dadurch das Risiko von Malware-Angriffen erhöhen kann.</span><span class="sxs-lookup"><span data-stu-id="2dadd-205">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="2dadd-206">Für andere Aufgaben sollten Sie das Konto <xref:System.ServiceProcess.ServiceAccount.LocalService> verwenden, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden anonyme Anmeldeinformationen übergeben.</span><span class="sxs-lookup"><span data-stu-id="2dadd-206">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="2dadd-207">Dieses Beispiel schlägt fehl, wenn Sie versuchen, das <xref:System.ServiceProcess.ServiceAccount.LocalService> -Konto zu verwenden, da zum Schreiben in das Ereignisprotokoll eine Genehmigung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="2dadd-207">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="2dadd-208">Weitere Informationen zu Installern finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="2dadd-208">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="2dadd-209">(Optional) Festlegen der Startparameter</span><span class="sxs-lookup"><span data-stu-id="2dadd-209">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="2dadd-210">Bevor Sie sich entscheiden, die Startparameter hinzuzufügen, ziehen Sie in Betracht, ob dies die beste Möglichkeit für die Übertragung von Informationen an Ihren Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="2dadd-210">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="2dadd-211">Obwohl Startparameter einfach zu verwenden und zu analysieren sind, und Benutzer sie leicht überschreiben können, sind sie möglicherweise ohne Dokumentation schwerer zu erkennen und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dadd-211">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="2dadd-212">Wenn der Dienst mehrere Startparameter erfordert, sollten Sie in der Regel stattdessen die Verwendung des Verzeichnisses oder einer Konfigurationsdatei erwägen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-212">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span>

<span data-ttu-id="2dadd-213">Ein Windows-Dienst akzeptiert Befehlszeilenargumente oder Startparameter.</span><span class="sxs-lookup"><span data-stu-id="2dadd-213">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="2dadd-214">Wenn Sie einen Code zum Startparameterprozess hinzufügen, können Benutzer den Dienst mithilfe des Fensters „Diensteigenschaften“ mit ihren eigenen benutzerdefinierten Startparametern starten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-214">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="2dadd-215">Diese Startparameter werden jedoch nicht beim nächsten Start des Dienst beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-215">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="2dadd-216">Wenn Sie Startparameter dauerhaft festlegen möchten, müssen Sie sie im Verzeichnis festlegen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-216">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="2dadd-217">Jeder Windows-Dienst hat einen Verzeichniseintrag unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-217">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="2dadd-218">Verwenden Sie unter dem Unterschlüssel jedes Diensts den Unterschlüssel **Parameter** zum Speichern von Informationen, auf die Ihr Dienst zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="2dadd-218">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="2dadd-219">Sie können Konfigurationsdateien für einen Windows-Dienst genauso wie für andere Arten von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2dadd-219">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="2dadd-220">Beispielcode finden Sie unter <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2dadd-220">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="2dadd-221">Hinzufügen von Startparametern</span><span class="sxs-lookup"><span data-stu-id="2dadd-221">To add startup parameters</span></span>

1. <span data-ttu-id="2dadd-222">Wählen Sie **Program.cs** oder **MyNewService.Designer.vb** aus, und wählen Sie dann im Kontextmenü **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-222">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="2dadd-223">Ändern Sie in der `Main`-Methode den Code, sodass ein Eingabeparameter hinzugefügt wird, und übergeben Sie ihn an den Dienstkonstruktor:</span><span class="sxs-lookup"><span data-stu-id="2dadd-223">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. <span data-ttu-id="2dadd-224">Ändern Sie in **MyNewService.cs** bzw. **MyNewService.vb** den `MyNewService`-Konstruktor, sodass der Eingabeparameter folgendermaßen verarbeitet wird:</span><span class="sxs-lookup"><span data-stu-id="2dadd-224">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

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
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="2dadd-225">Diese Code legt die Ereignisquelle und den Protokollnamen gemäß der Startparameter fest, die der Benutzer angibt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-225">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="2dadd-226">Wenn keine Argumente angegeben werden, werden Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="2dadd-226">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="2dadd-227">Sollen Befehlszeilenargumente angegeben werden, fügen Sie der `ProjectInstaller`-Klasse in **ProjectInstaller.cs** bzw. **ProjectInstaller.vb** den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="2dadd-227">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

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

   <span data-ttu-id="2dadd-228">Dieser Wert enthält in der Regel den vollständigen Pfad zur ausführbaren Datei des Windows-Diensts.</span><span class="sxs-lookup"><span data-stu-id="2dadd-228">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="2dadd-229">Die Anführungszeichen rund um den Pfad und um jeden einzelnen Parameter sind erforderlich, um den Dienst korrekt zu starten.</span><span class="sxs-lookup"><span data-stu-id="2dadd-229">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="2dadd-230">Ein Benutzer kann die Parameter im **ImagePath**-Verzeichniseintrag ändern, um die Startparameter für den Windows-Dienst zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2dadd-230">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="2dadd-231">Besser ist es jedoch, den Wert programmgesteuert zu ändern und die Funktionalität in einer benutzerfreundlichen Weise verfügbar zu machen, z. B. mithilfe eines Verwaltungs- oder Konfigurationshilfsprogramms.</span><span class="sxs-lookup"><span data-stu-id="2dadd-231">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>

## <a name="build-the-service"></a><span data-ttu-id="2dadd-232">Erstellen des Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-232">Build the service</span></span>

1. <span data-ttu-id="2dadd-233">Wählen Sie im **Projektmappen-Explorer** aus dem Kontextmenü des **MyNewService**-Projekts die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-233">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="2dadd-234">Die Eigenschaftenseiten für Ihr Projekt werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-234">The property pages for your project appear.</span></span>

2. <span data-ttu-id="2dadd-235">Klicken Sie in der Registerkarte **Anwendung** in der Liste **Startobjekt** auf **MyNewService.Program**, oder auf **Sub Main**, wenn es sich um ein Visual Basic-Projekt handelt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-235">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="2dadd-236">Wählen Sie im **Projektmappen-Explorer** aus dem Kontextmenü des Projekts **Erstellen** aus, um das Projekt zu erstellen (oder drücken Sie **STRG**+**UMSCHALT**+**B**).</span><span class="sxs-lookup"><span data-stu-id="2dadd-236">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="2dadd-237">Installieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-237">Install the service</span></span>

<span data-ttu-id="2dadd-238">Nachdem Sie den Windows-Dienst nun erstellt haben, können Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="2dadd-238">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="2dadd-239">Soll ein Windows-Dienst installiert werden, müssen Sie über Administratorberechtigungen für den Computer verfügen, auf dem Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="2dadd-239">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="2dadd-240">Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) mit Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-240">Open [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) with administrative credentials.</span></span> <span data-ttu-id="2dadd-241">Wählen Sie im Windows-**Startmenü** im Visual Studio-Ordner **Developer-Eingabeaufforderung für Visual Studio 2017** aus, und klicken Sie dann im Kontextmenü auf **Mehr** > **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-241">From the Windows **Start** menu, select **Developer Command Prompt for VS 2017** in the Visual Studio folder, then select **More** > **Run as Administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="2dadd-242">Navigieren Sie im Fenster **Developer-Eingabeaufforderung für Visual Studio** zu dem Ordner, der die Ausgabe Ihres Projekts enthält (standardmäßig das Unterverzeichnis *\bin\Debug* Ihres Projekts).</span><span class="sxs-lookup"><span data-stu-id="2dadd-242">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="2dadd-243">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2dadd-243">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="2dadd-244">Wenn der Dienst erfolgreich installiert wurde, meldet der Befehl Erfolg.</span><span class="sxs-lookup"><span data-stu-id="2dadd-244">If the service installs successfully, the command reports success.</span></span>

    <span data-ttu-id="2dadd-245">Wenn das System die Datei *installutil.exe* nicht finden kann, stellen Sie sicher, dass sie auf Ihrem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2dadd-245">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="2dadd-246">Dieses Tool wird mit dem .NET Framework im Ordner *%windir%\Microsoft.NET\Framework[64]\\&lt;[Frameworkversion]&gt;* installiert.</span><span class="sxs-lookup"><span data-stu-id="2dadd-246">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="2dadd-247">Der Standardpfad für die 64-Bit-Version lautet beispielsweise *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="2dadd-247">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="2dadd-248">Wenn der Prozess **installutil.exe** fehlschlägt, überprüfen Sie das Installationsprotokoll, um die Gründe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-248">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="2dadd-249">Standardmäßig befindet sich das Protokoll im gleichen Ordner wie die ausführbare Datei des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2dadd-249">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="2dadd-250">Die Installation kann aus folgenden Gründen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="2dadd-250">The installation can fail if:</span></span>
    - <span data-ttu-id="2dadd-251">Die <xref:System.ComponentModel.RunInstallerAttribute>-Klasse ist in der `ProjectInstaller`-Klasse nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2dadd-251">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    - <span data-ttu-id="2dadd-252">Das Attribut ist nicht auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2dadd-252">The attribute isn't set to `true`.</span></span>
    - <span data-ttu-id="2dadd-253">Die `ProjectInstaller`-Klasse ist nicht als `public` definiert.</span><span class="sxs-lookup"><span data-stu-id="2dadd-253">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="2dadd-254">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="2dadd-254">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="2dadd-255">Starten und Ausführen des Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-255">Start and run the service</span></span>

1. <span data-ttu-id="2dadd-256">Öffnen Sie in Windows die Desktop-App **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-256">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="2dadd-257">Drücken Sie **Windows**+**R**, um das Feld **Ausführen** zu öffnen, geben Sie dann *services.msc* ein, und drücken Sie die **EINGABETASTE**, oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-257">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="2dadd-258">Ihr Dienst sollte in **Dienste** alphabetisch nach dem Anzeigenamen aufgeführt sein, den Sie für ihn festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="2dadd-258">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService im Fenster "Dienste".](./media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="2dadd-260">Der Dienst wird gestartet, wenn Sie im Kontextmenü des Diensts **Starten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-260">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="2dadd-261">Der Dienst wird angehalten, wenn Sie im Kontextmenü des Diensts **Stopp** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-261">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="2dadd-262">(Optional) Über die Befehlszeile können Sie die Befehle **net start &lt;Dienstname&gt;** und **net stop &lt;Dienstname&gt;** verwenden, um Ihren Dienst zu starten und zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-262">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="2dadd-263">Überprüfen der Ereignisprotokollausgabe des Diensts</span><span class="sxs-lookup"><span data-stu-id="2dadd-263">Verify the event log output of your service</span></span>

1. <span data-ttu-id="2dadd-264">Öffnen Sie in Windows die Desktop-App **Event Viewer**.</span><span class="sxs-lookup"><span data-stu-id="2dadd-264">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="2dadd-265">Geben Sie in der Windows-Suchleiste *Event Viewer* ein, und wählen Sie dann in den Suchergebnissen **Event Viewer** aus.</span><span class="sxs-lookup"><span data-stu-id="2dadd-265">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="2dadd-266">In Visual Studio können Sie auf Ereignisprotokolle zugreifen, indem Sie über das Menü **Anzeigen** den **Server-Explorer** öffnen (oder **STRG**+**ALT**+**S** drücken) und den Knoten **Ereignisprotokolle** für den lokalen Computer aufklappen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-266">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="2dadd-267">Klappen Sie in der **Ereignisanzeige** **Anwendungs- und Dienstprotokolle** auf.</span><span class="sxs-lookup"><span data-stu-id="2dadd-267">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="2dadd-268">Suchen Sie den Eintrag für **MyNewLog** (oder **MyLogFile1**, wenn Sie das Verfahren befolgt haben, um Befehlszeilenargumente hinzuzufügen), und klappen Sie ihn auf.</span><span class="sxs-lookup"><span data-stu-id="2dadd-268">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="2dadd-269">Sie sollten Einträge für die beiden Aktionen (Starten und Stopp) sehen, die Ihr Dienst ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="2dadd-269">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![Verwenden der Ereignisanzeige zum Anzeigen von Einträgen im Ereignisprotokoll](./media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="2dadd-271">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2dadd-271">Clean up resources</span></span>

<span data-ttu-id="2dadd-272">Wenn Sie die Windows-Dienst-App nicht länger benötigen, können Sie sie entfernen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-272">If you no longer need the Windows service app, you can remove it.</span></span>

1. <span data-ttu-id="2dadd-273">Öffnen Sie die **Developer-Eingabeaufforderung für Visual Studio** mit Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-273">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="2dadd-274">Navigieren Sie im Fenster **Developer-Eingabeaufforderung für Visual Studio** zu dem Ordner, der die Ausgabe Ihres Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="2dadd-274">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="2dadd-275">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2dadd-275">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="2dadd-276">Wenn der Dienst erfolgreich deinstalliert wurde, meldet der Befehl, dass der Dienst erfolgreich entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="2dadd-276">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="2dadd-277">Weitere Informationen finden Sie unter [Vorgehensweise: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="2dadd-277">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2dadd-278">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2dadd-278">Next steps</span></span>

<span data-ttu-id="2dadd-279">Nach der Erstellung des Diensts haben Sie nun folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2dadd-279">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="2dadd-280">Erstellen eines eigenständigen Setupprogramms, damit andere Personen Ihren Windows-Dienst installieren können.</span><span class="sxs-lookup"><span data-stu-id="2dadd-280">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="2dadd-281">Verwenden Sie das [WiX-Toolset](https://wixtoolset.org/), um einen Installer für einen Windows-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-281">Use the [WiX Toolset](https://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="2dadd-282">Weitere Ideen finden Sie unter [Erstellen eines Installationspakets](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="2dadd-282">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="2dadd-283">Sie können die Verwendung einer <xref:System.ServiceProcess.ServiceController>-Komponente untersuchen, die es Ihnen ermöglicht, Befehle an den installierten Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="2dadd-283">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="2dadd-284">Sie können einen Installer verwenden, um ein Ereignisprotokoll während der Installation anstatt während der Ausführung der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2dadd-284">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="2dadd-285">Das Ereignisprotokoll wird vom Installer entfernt, wenn Sie die Anwendung deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="2dadd-285">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="2dadd-286">Weitere Informationen finden Sie unter <xref:System.Diagnostics.EventLogInstaller>.</span><span class="sxs-lookup"><span data-stu-id="2dadd-286">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dadd-287">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dadd-287">See also</span></span>

- [<span data-ttu-id="2dadd-288">Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="2dadd-288">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="2dadd-289">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="2dadd-289">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="2dadd-290">How to: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="2dadd-290">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="2dadd-291">Dienste (Windows)</span><span class="sxs-lookup"><span data-stu-id="2dadd-291">Services (Windows)</span></span>](/windows/desktop/Services/services)
