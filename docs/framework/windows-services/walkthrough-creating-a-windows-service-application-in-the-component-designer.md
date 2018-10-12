---
title: Erstellen einer Windows-Dienstanwendung in Visual Studio
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: 27acdac5d34b96dd04fec1bb763edec9077ff928
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46493606"
---
# <a name="walkthrough-create-a-windows-service-app"></a><span data-ttu-id="284a8-102">Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="284a8-102">Walkthrough: Create a Windows service app</span></span>

<span data-ttu-id="284a8-103">In diesem Artikel wird beschrieben, wie Sie eine einfache Windows-Dienstanwendung in Visual Studio erstellen, die Meldungen in ein Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="284a8-103">This article demonstrates how to create a simple Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="284a8-104">Erstellen eines Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-104">Create a service</span></span>

<span data-ttu-id="284a8-105">Erstellen Sie zunächst das Projekt, und legen Sie die Werte fest, die für die korrekte Funktion des Diensts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="284a8-105">To begin, create the project and set values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="284a8-106">Wählen Sie in Visual Studio auf der Menüleiste **Datei** > **Neu** > **Projekt** aus (oder drücken Sie **STRG**+**UMSCHALT**+**N**), um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="284a8-106">In Visual Studio, on the menu bar, choose **File** > **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** dialog.</span></span>

2. <span data-ttu-id="284a8-107">Navigieren Sie zur Projektvorlage **Windows-Dienst**.</span><span class="sxs-lookup"><span data-stu-id="284a8-107">Navigate to and select the **Windows Service** project template.</span></span> <span data-ttu-id="284a8-108">Erweitern Sie **Installierte** > [**Visual C#** oder **Visual Basic**] > **Windows-Desktop**, oder geben Sie **Windows-Dienst** in das Suchfeld oben rechts ein.</span><span class="sxs-lookup"><span data-stu-id="284a8-108">Expand **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, or type **Windows Service** in the search box on the upper right.</span></span>

   ![Windows-Dienstvorlage im Dialogfeld „Neues Projekt“ in Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="284a8-110">Wenn Sie die Vorlage **Windows-Dienst** nicht finden können, müssen Sie möglicherweise die Workload **.NET-Desktopentwicklung** installieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-110">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload.</span></span> <span data-ttu-id="284a8-111">Klicken Sie im Dialogfeld **Neues Projekt** auf den Link **Visual Studio-Installer öffnen** unten links.</span><span class="sxs-lookup"><span data-stu-id="284a8-111">In the **New Project** dialog, click the link that says **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="284a8-112">Wählen Sie im **Visual Studio-Installer** die Workload **.NET-Desktopentwicklung** und dann **Ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-112">In **Visual Studio Installer**, select the **.NET desktop development** workload and then choose **Modify**.</span></span>

3. <span data-ttu-id="284a8-113">Benennen Sie das Projekt **MyNewService**, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-113">Name the project **MyNewService**, and then choose **OK**.</span></span>

   <span data-ttu-id="284a8-114">Die Projektvorlage beinhaltet eine Komponentenklasse mit dem Namen `Service1`, die von <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erbt.</span><span class="sxs-lookup"><span data-stu-id="284a8-114">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="284a8-115">Sie enthält einen großen Teil des grundlegenden Dienstcodes, etwa den Code zum Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="284a8-115">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="284a8-116">Umbenennen des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-116">Rename the service</span></span>

<span data-ttu-id="284a8-117">Benennen Sie den Dienst von **Service1** in **MyNewService** um.</span><span class="sxs-lookup"><span data-stu-id="284a8-117">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="284a8-118">Klicken Sie in der **Entwurfsansicht** für „Service1.cs“ (oder „Service1.vb“) auf den Link zum **Wechseln in die Codeansicht**.</span><span class="sxs-lookup"><span data-stu-id="284a8-118">In the **Design** view for Service1.cs (or Service1.vb), click the link to **switch to code view**.</span></span> <span data-ttu-id="284a8-119">Klicken Sie mit der rechten Maustaste auf **Service1**, und wählen Sie im Kontextmenü **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-119">Right-click on **Service1** and select **Rename** from the context menu.</span></span> <span data-ttu-id="284a8-120">Geben Sie **MyNewService** ein, und drücken Sie dann die **EINGABETASTE**, oder klicken Sie auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="284a8-120">Enter **MyNewService** and then press **Enter** or click **Apply**.</span></span>

2. <span data-ttu-id="284a8-121">Ändern Sie im **Eigenschaftenfenster** für **Service1.cs [Entwurf]** oder **Service1.vb [Entwurf]** den Wert von **ServiceName** in **MyNewService**.</span><span class="sxs-lookup"><span data-stu-id="284a8-121">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, change the **ServiceName** value to **MyNewService**.</span></span>

3. <span data-ttu-id="284a8-122">Benennen Sie im **Projektmappen-Explorer** **Service1.cs** in **MyNewService.cs** um, oder benennen Sie **Service1.vb** in **MyNewService.vb** um.</span><span class="sxs-lookup"><span data-stu-id="284a8-122">In **Solution Explorer**, rename **Service1.cs** to **MyNewService.cs**, or rename **Service1.vb** to **MyNewService.vb**.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="284a8-123">Hinzufügen von Features zum Dienst</span><span class="sxs-lookup"><span data-stu-id="284a8-123">Add features to the service</span></span>

<span data-ttu-id="284a8-124">In diesem Abschnitt fügen Sie dem Windows-Dienst ein benutzerdefiniertes Ereignisprotokoll hinzu.</span><span class="sxs-lookup"><span data-stu-id="284a8-124">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="284a8-125">Ereignisprotokolle sind Windows-Diensten in keiner Weise zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="284a8-125">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="284a8-126">Hier wird die <xref:System.Diagnostics.EventLog>-Komponente als Beispiel für die Art von Komponente verwendet, die Sie einem Windows-Dienst hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="284a8-126">The <xref:System.Diagnostics.EventLog> component is used here as an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="284a8-127">Hinzufügen einer benutzerdefinierten Ereignisprotokollfunktion</span><span class="sxs-lookup"><span data-stu-id="284a8-127">Add custom event log functionality</span></span>

1. <span data-ttu-id="284a8-128">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-128">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="284a8-129">Ziehen Sie im **Werkzeugkasten** aus dem Abschnitt **Komponenten**eine <xref:System.Diagnostics.EventLog> -Komponente in den Designer.</span><span class="sxs-lookup"><span data-stu-id="284a8-129">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>

3. <span data-ttu-id="284a8-130">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-130">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>

4. <span data-ttu-id="284a8-131">Bearbeiten Sie den Konstruktor, um ein benutzerdefiniertes Ereignisprotokoll zu definieren:</span><span class="sxs-lookup"><span data-stu-id="284a8-131">Edit the constructor to define a custom event log:</span></span>

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="284a8-132">Definieren, was beim Starten des Diensts ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="284a8-132">Define what occurs when the service starts</span></span>

<span data-ttu-id="284a8-133">Suchen Sie im Code-Editor die Methode <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, die beim Erstellen des Projekts automatisch überschrieben worden war.</span><span class="sxs-lookup"><span data-stu-id="284a8-133">In the code editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project.</span></span> <span data-ttu-id="284a8-134">Fügen Sie eine Codezeile hinzu, die beim Starten des Diensts einen Eintrag in das Ereignisprotokoll schreibt:</span><span class="sxs-lookup"><span data-stu-id="284a8-134">Add a line of code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

<span data-ttu-id="284a8-135">Eine Dienstanwendung soll eine lange Laufzeit haben, damit sie in der Regel etwas abfragt oder etwas im System überwacht.</span><span class="sxs-lookup"><span data-stu-id="284a8-135">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="284a8-136">Die Überwachung wird in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="284a8-136">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="284a8-137">Allerdings erfolgt die Überwachung jedoch nicht durch <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .</span><span class="sxs-lookup"><span data-stu-id="284a8-137">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="284a8-138">Die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode muss zum Betriebssystem zurückkehren, sobald die Ausführung des Dienstes begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="284a8-138">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="284a8-139">Sie darf keine Endlosschleife oder Blöcke ausführen.</span><span class="sxs-lookup"><span data-stu-id="284a8-139">It must not loop forever or block.</span></span> <span data-ttu-id="284a8-140">Wenn Sie einen einfachen Abrufmechanismus einrichten, können Sie die Komponente <xref:System.Timers.Timer?displayProperty=nameWithType> wie folgt verwenden: Klicken Sie In der Methode <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, legen Sie Parameter in der Komponente fest, und setzen Sie dann die Eigenschaft <xref:System.Timers.Timer.Enabled%2A>auf `true`.</span><span class="sxs-lookup"><span data-stu-id="284a8-140">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="284a8-141">Der Zeitgeber löst dann regelmäßig zu der Zeit Ereignisse im Code aus, zu der der Dienst seine Überwachung ausführen könnte.</span><span class="sxs-lookup"><span data-stu-id="284a8-141">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="284a8-142">Sie können hierfür den folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="284a8-142">You can use the following code to do this:</span></span>

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

<span data-ttu-id="284a8-143">Fügen Sie der Klasse eine Membervariable hinzu.</span><span class="sxs-lookup"><span data-stu-id="284a8-143">Add a member variable to the class.</span></span> <span data-ttu-id="284a8-144">Sie enthält den Bezeichner des nächsten Ereignisses, das in das Ereignisprotokoll geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="284a8-144">It contains the identifier of the next event to write into the event log.</span></span>

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

<span data-ttu-id="284a8-145">Fügen Sie eine neue Methode zum Verarbeiten des Zeitgeberereignisses hinzu:</span><span class="sxs-lookup"><span data-stu-id="284a8-145">Add a new method to handle the timer event:</span></span>

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

<span data-ttu-id="284a8-146">Möglicherweise möchten Sie Aufgaben mit Arbeitsthreads im Hintergrund statt Ihre Arbeit auf der Haupt-Thread ausführen.</span><span class="sxs-lookup"><span data-stu-id="284a8-146">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="284a8-147">Weitere Informationen finden Sie unter <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="284a8-147">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="284a8-148">Definieren, was beim Beenden des Diensts ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="284a8-148">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="284a8-149">Fügen Sie der Methode <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine Codezeile hinzu, die beim Beenden des Diensts einen Eintrag zum Ereignisprotokoll hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="284a8-149">Add a line of code to the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="284a8-150">Definieren weiterer Aktionen für den Dienst</span><span class="sxs-lookup"><span data-stu-id="284a8-150">Define other actions for the service</span></span>

<span data-ttu-id="284a8-151">Sie können die Methoden <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> und <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> überschreiben, um zusätzliche Verarbeitungsschritte für Ihre Komponente zu definieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-151">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> <span data-ttu-id="284a8-152">Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> -Methode überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-152">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

<span data-ttu-id="284a8-153">Einige benutzerdefinierte Aktionen müssen eintreten, wenn ein Windows-Dienst von der <xref:System.Configuration.Install.Installer> Klasse installiert wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-153">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="284a8-154">Visual Studio kann diese Installationsprogramme speziell für einen Windows-Dienst erstellen und sie dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="284a8-154">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>

## <a name="set-service-status"></a><span data-ttu-id="284a8-155">Festlegen des Dienststatus</span><span class="sxs-lookup"><span data-stu-id="284a8-155">Set service status</span></span>

<span data-ttu-id="284a8-156">Dienste melden ihren Status mit dem Dienststeuerungs-Manager, damit Benutzer erkennen können, ob ein Dienst ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-156">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="284a8-157">Dienste, die von standardmäßig von <xref:System.ServiceProcess.ServiceBase> übernommen werden, melden eine begrenzte Anzahl von Statuseinstellungen, darunter Beendet, Angehalten und Werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="284a8-157">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="284a8-158">Wenn es etwas länger dauert, bis ein Dienst startet, kann es hilfreich sein, einen Status Start ausstehend zu melden.</span><span class="sxs-lookup"><span data-stu-id="284a8-158">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="284a8-159">Sie können auch die Statuseinstellungen Start ausstehend und Stopp ausstehend durch Hinzufügen von Code implementieren, der in Windows die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) aufruft.</span><span class="sxs-lookup"><span data-stu-id="284a8-159">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span></span>

<span data-ttu-id="284a8-160">Zum Implementieren des Dienststatus „ausstehend“:</span><span class="sxs-lookup"><span data-stu-id="284a8-160">To implement service pending status:</span></span>

1. <span data-ttu-id="284a8-161">Fügen Sie eine `using`-Anweisung oder eine `Imports`-Deklaration für den <xref:System.Runtime.InteropServices?displayProperty=nameWithType>-Namespace zur Datei MyNewService.cs oder MyNewService.vb hinzu:</span><span class="sxs-lookup"><span data-stu-id="284a8-161">Add a `using` statement or `Imports` declaration for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="284a8-162">Fügen Sie folgenden Code zum MyNewService.cs hinzu, um die `ServiceState` Werte zu deklarieren und um eine Struktur für den Status hinzuzufügen, die Sie in einem Plattformaufruf verwenden:</span><span class="sxs-lookup"><span data-stu-id="284a8-162">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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

3. <span data-ttu-id="284a8-163">Deklarieren Sie nun in der Klasse `MyNewService` die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mithilfe eines [Plattformaufrufs](../interop/consuming-unmanaged-dll-functions.md):</span><span class="sxs-lookup"><span data-stu-id="284a8-163">Now, in the `MyNewService` class, declare the [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="284a8-164">Um den Status Start ausstehend zu implementieren, fügen Sie den folgenden Code am Anfang der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="284a8-164">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="284a8-165">Fügen Sie den Code hinzu, um den Status Wird ausgeführt am Ende der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode festzulegen.</span><span class="sxs-lookup"><span data-stu-id="284a8-165">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>

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

6. <span data-ttu-id="284a8-166">(Optional) Wiederholen Sie diesen Vorgang für die <xref:System.ServiceProcess.ServiceBase.OnStop%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="284a8-166">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="284a8-167">Das Dialogfeld [Dienststeuerungs-Manager](/windows/desktop/Services/service-control-manager) verwendet die Member `dwWaitHint` und `dwCheckpoint` der [SERVICE_STATUS-Struktur](/windows/desktop/api/winsvc/ns-winsvc-_service_status), um zu bestimmen, wie lange bis zum Starten oder Herunterfahren eines Windows-Diensts gewartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="284a8-167">The [Service Control Manager](/windows/desktop/Services/service-control-manager) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="284a8-168">Wenn Ihre Methoden <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine lange Ausführungszeit haben, kann Ihr Dienst durch das erneute Aufrufen von [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mit einem erhöhten `dwCheckPoint`-Wert mehr Zeit anfordern.</span><span class="sxs-lookup"><span data-stu-id="284a8-168">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) again with an incremented `dwCheckPoint` value.</span></span>

## <a name="add-installers-to-the-service"></a><span data-ttu-id="284a8-169">Hinzufügen von Installern zum Dienst</span><span class="sxs-lookup"><span data-stu-id="284a8-169">Add installers to the service</span></span>

<span data-ttu-id="284a8-170">Bevor Sie einen Windows-Dienst ausführen können, müssen Sie ihn bei der Installation im Dienststeuerungs-Manager registrieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-170">Before you can run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="284a8-171">Sie können Installationsprogramme dem Projekt hinzufügen, die die Registrierungsdetails behandelt.</span><span class="sxs-lookup"><span data-stu-id="284a8-171">You can add installers to your project that handle the registration details.</span></span>

1. <span data-ttu-id="284a8-172">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-172">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="284a8-173">Klicken Sie auf den Hintergrund des Designers, um den Dienst selbst, nicht Elemente seines Inhalts, zu markieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-173">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>

3. <span data-ttu-id="284a8-174">Öffnen Sie das Kontextmenü für das Designer-Fenster (wenn Sie ein Zeigegerät verwenden, rechtsklicken Sie in das Fenster) und wählen Sie dann **Installer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="284a8-174">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>

   <span data-ttu-id="284a8-175">Standardmäßig wird dem Projekt eine Komponentenklasse mit zwei Installationsprogrammen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="284a8-175">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="284a8-176">Die Komponente erhält den Namen **ProjectInstaller**; die darin enthaltenen Installationsprogramme sind zum einen das Installationsprogramm für den Dienst und zum andern das Installationsprogramm für den zugeordneten Prozess des Diensts.</span><span class="sxs-lookup"><span data-stu-id="284a8-176">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>

4. <span data-ttu-id="284a8-177">Klicken Sie in der Ansicht **Entwurf** für **ProjectInstaller**auf **ServiceInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt, bzw. auf **serviceInstaller1** , wenn es sich um ein Visual C#-Projekt handelt.</span><span class="sxs-lookup"><span data-stu-id="284a8-177">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>

5. <span data-ttu-id="284a8-178">Vergewissern Sie sich im Fenster **Eigenschaften** , dass die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft auf **MyNewService**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="284a8-178">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="284a8-179">Legen Sie die **Beschreibung** -Eigenschaft auf Text, wie z. B. "Ein Beispieldienst" fest.</span><span class="sxs-lookup"><span data-stu-id="284a8-179">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="284a8-180">Dieser Text wird im Fenster Dienste angezeigt und hilft dem Benutzer den Dienst zu identifizieren, und zu verstehen, wofür er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-180">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>

7. <span data-ttu-id="284a8-181">Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> -Eigenschaft auf den Text fest, der im Fenster Dienste in der Spalte **Name** angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="284a8-181">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="284a8-182">Beispielsweise können Sie "MyNewService Display Name" eingeben.</span><span class="sxs-lookup"><span data-stu-id="284a8-182">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="284a8-183">Dieser Name kann sich von der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft unterscheidet, die dem Namen entspricht, der vom System verwendet wird (z. B. bei Verwendung des `net start` -Befehls zum Starten des Dienstes).</span><span class="sxs-lookup"><span data-stu-id="284a8-183">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>

8. <span data-ttu-id="284a8-184">Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>-Eigenschaft auf <xref:System.ServiceProcess.ServiceStartMode.Automatic> fest.</span><span class="sxs-lookup"><span data-stu-id="284a8-184">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>

     <span data-ttu-id="284a8-185">![Installer-Eigenschaften für einen Windows-Dienst](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_Installereigenschaften")</span><span class="sxs-lookup"><span data-stu-id="284a8-185">![Installer Properties for a Windows service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>

9. <span data-ttu-id="284a8-186">Klicken Sie im Designer auf **ServiceProcessInstaller1** , wenn es sich um ein Visual Basic#-Projekt handelt, bzw. auf **serviceProcessInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt.</span><span class="sxs-lookup"><span data-stu-id="284a8-186">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="284a8-187">Legen Sie die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>-Eigenschaft auf <xref:System.ServiceProcess.ServiceAccount.LocalSystem> fest.</span><span class="sxs-lookup"><span data-stu-id="284a8-187">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="284a8-188">Dies bewirkt, dass der Dienst installiert und mit dem lokalen Systemkonto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-188">This causes the service to be installed and to run using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="284a8-189">Das Konto <xref:System.ServiceProcess.ServiceAccount.LocalSystem> verfügt über ein breites Berechtigungsspektrum, einschließlich der Berechtigung zum Schreiben in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="284a8-189">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="284a8-190">Bei der Verwendung dieses Kontos ist allerdings Vorsicht geboten, da sich dadurch das Risiko von Malware-Angriffen erhöhen kann.</span><span class="sxs-lookup"><span data-stu-id="284a8-190">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="284a8-191">Für andere Aufgaben sollten Sie das Konto <xref:System.ServiceProcess.ServiceAccount.LocalService> verwenden, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden anonyme Anmeldeinformationen übergeben.</span><span class="sxs-lookup"><span data-stu-id="284a8-191">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="284a8-192">Dieses Beispiel schlägt fehl, wenn Sie versuchen, das <xref:System.ServiceProcess.ServiceAccount.LocalService>-Konto zu verwenden, da zum Schreiben in das Ereignisprotokoll eine Genehmigung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-192">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="284a8-193">Weitere Informationen zu Installern finden Sie unter [Gewusst wie: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="284a8-193">For more information about installers, see [How to: Add Installers to Your service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="284a8-194">(Optional) Festlegen der Startparameter</span><span class="sxs-lookup"><span data-stu-id="284a8-194">(Optional) Set startup parameters</span></span>

<span data-ttu-id="284a8-195">Ein Windows-Dienst akzeptiert wie jede andere ausführbare Datei Befehlszeilenargumente oder Startparameter.</span><span class="sxs-lookup"><span data-stu-id="284a8-195">A Windows service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="284a8-196">Wenn Sie einen Code zum Startparameterprozess hinzufügen, können Benutzer den Dienst mithilfe des Fensters "Dienste" in der Windows-Systemsteuerung mit ihren eigenen benutzerdefinierten Startparametern starten.</span><span class="sxs-lookup"><span data-stu-id="284a8-196">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="284a8-197">Diese Startparameter werden jedoch nicht beim nächsten Start des Dienst beibehalten.</span><span class="sxs-lookup"><span data-stu-id="284a8-197">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="284a8-198">Um Startparameter dauerhaft festzulegen, können Sie diese in der Registrierung festlegen, wie in diesem Verfahren dargestellt.</span><span class="sxs-lookup"><span data-stu-id="284a8-198">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="284a8-199">Bevor Sie sich entscheiden, die Startparameter hinzuzufügen, ziehen Sie in Betracht, ob dies die beste Möglichkeit für die Übertragung von Informationen an Ihren Dienst ist.</span><span class="sxs-lookup"><span data-stu-id="284a8-199">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="284a8-200">Obwohl Startparameter einfach zu verwenden und zu analysieren sind, und sie Benutzer sie leicht überschreiben können, sind sie möglicherweise ohne die Dokumentation schwerer zu erkennen und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="284a8-200">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="284a8-201">In der Regel, wenn der Dienst mehr als nur ein paar Startparameter erfordert, sollten Sie stattdessen die Verwendung des Verzeichnisses oder einer Konfigurationsdatei erwägen.</span><span class="sxs-lookup"><span data-stu-id="284a8-201">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="284a8-202">Jeder Windows-Dienst ist ein Eintrag im Verzeichnis unter **HKLM\System\CurrentControlSet\services**.</span><span class="sxs-lookup"><span data-stu-id="284a8-202">Every Windows service has an entry in the registry under **HKLM\System\CurrentControlSet\services**.</span></span> <span data-ttu-id="284a8-203">Gemäß dem Service-Schlüssel können Sie den Teilschlüssel **Parameter** zum Speichern von Informationen verwenden, auf die Ihr Dienst zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="284a8-203">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="284a8-204">Sie können Konfigurationsdateien für einen Windows-Dienst genauso wie für andere Arten von Programmen verwenden.</span><span class="sxs-lookup"><span data-stu-id="284a8-204">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="284a8-205">Beispielcode finden Sie unter <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span><span class="sxs-lookup"><span data-stu-id="284a8-205">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>

<span data-ttu-id="284a8-206">So fügen Sie Startparameter hinzu:</span><span class="sxs-lookup"><span data-stu-id="284a8-206">To add startup parameters:</span></span>

1. <span data-ttu-id="284a8-207">Fügen Sie in der `Main`-Methode in Program.cs oder in MyNewService.Designer.vb einen Eingabeparameter hinzu, um den Dienstkonstruktor zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="284a8-207">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an input parameter to pass to the service constructor:</span></span>

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. <span data-ttu-id="284a8-208">Ändern Sie den `MyNewService` -Konstruktor wie folgt:</span><span class="sxs-lookup"><span data-stu-id="284a8-208">Change the `MyNewService` constructor as follows:</span></span>

   ```csharp
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

   <span data-ttu-id="284a8-209">Dieser Code legt die Ereignisquelle und den Protokollnamen gemäß der angegebenen Startparameter fest oder verwendet Standardwerte, wenn keine Argumente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="284a8-209">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>

3. <span data-ttu-id="284a8-210">Um Befehlszeilenargumente anzugeben, fügen Sie den folgenden Code zu der `ProjectInstaller` -Klasse in ProjectInstaller.cs oder ProjectInstaller.vb hinzu:</span><span class="sxs-lookup"><span data-stu-id="284a8-210">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>

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

   <span data-ttu-id="284a8-211">Dieser Code ändert den **ImagePath** -Registrierungsschlüssel, der in der Regel den vollständigen Pfad der ausführbaren Datei für den Windows-Dienst enthält, indem er ihm die Standardwerte für die Parameter hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="284a8-211">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows service, by adding the default parameter values.</span></span> <span data-ttu-id="284a8-212">Die Anführungszeichen rund um den Pfad (und um jeden einzelnen Parameter) sind erforderlich, um den Dienst korrekt zu starten.</span><span class="sxs-lookup"><span data-stu-id="284a8-212">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="284a8-213">Um die Startparameter für diesen Windows-Dienst zu ändern, können Benutzer die Parameter ändern, die im **ImagePath** -Registrierungsschlüssel angegeben sind, obwohl es besser wäre, ihn programmgesteuert zu ändern und die Funktionalität für Benutzer in einer geeigneten Form (z. B. in einem Dienstprogramm Verwaltung oder Konfiguration) verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="284a8-213">To change the startup parameters for this Windows service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>

## <a name="build-the-service"></a><span data-ttu-id="284a8-214">Erstellen des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-214">Build the service</span></span>

1. <span data-ttu-id="284a8-215">Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-215">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span>

   <span data-ttu-id="284a8-216">Die Eigenschaftenseiten für Ihr Projekt werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="284a8-216">The property pages for your project appear.</span></span>

2. <span data-ttu-id="284a8-217">Klicken Sie in der Registerkarte **Anwendung** in der Liste **Startobjekt** auf **MyNewService.Program**.</span><span class="sxs-lookup"><span data-stu-id="284a8-217">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>

3. <span data-ttu-id="284a8-218">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt und wählen Sie dann **Erstellen** aus, um das Projekt zu erstellen (oder drücken Sie **STRG**+**UMSCHALT**+**B**).</span><span class="sxs-lookup"><span data-stu-id="284a8-218">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="284a8-219">Installieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-219">Install the service</span></span>

<span data-ttu-id="284a8-220">Nachdem Sie den Windows-Dienst nun erstellt haben, können Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-220">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="284a8-221">Um einen Windows-Dienst zu installieren, müssen Sie über Administratorberechtigungen für den Computer verfügen, auf dem Sie ihn installieren.</span><span class="sxs-lookup"><span data-stu-id="284a8-221">To install a Windows service, you must have administrator credentials on the computer on which you're installing it.</span></span>

1. <span data-ttu-id="284a8-222">Öffnen Sie die **Developer-Eingabeaufforderung für Visual Studio** mit Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="284a8-222">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span> <span data-ttu-id="284a8-223">Wenn Sie eine Maus verwenden, klicken Sie mit der rechten Maustaste im Windows-Startmenü auf **Developer-Eingabeaufforderung für VS 2017**, und wählen Sie dann **Mehr** > **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-223">If you’re using a mouse, right-click on **Developer Command Prompt for VS 2017** in the Windows Start menu, and then choose **More** > **Run as Administrator**.</span></span>

2. <span data-ttu-id="284a8-224">Navigieren Sie im Fenster **Developer-Eingabeaufforderung** zu dem Ordner, der die Ausgabe Ihres Projekts enthält (standardmäßig das Unterverzeichnis *\bin\Debug* Ihres Projekts).</span><span class="sxs-lookup"><span data-stu-id="284a8-224">In the **Developer Command Prompt** window, navigate to the folder that contains your project's output (by default, it's the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="284a8-225">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="284a8-225">Enter the following command:</span></span>

    ```shell
    installutil.exe MyNewService.exe
    ```

    <span data-ttu-id="284a8-226">Wenn der Dienst erfolgreich installiert wird, meldet **installutil.exe** Erfolg.</span><span class="sxs-lookup"><span data-stu-id="284a8-226">If the service installs successfully, **installutil.exe** reports success.</span></span> <span data-ttu-id="284a8-227">Wenn das System **InstallUtil.exe** nicht finden kann, stellen Sie sicher, dass sie auf Ihrem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="284a8-227">If the system could not find **InstallUtil.exe**, make sure that it exists on your computer.</span></span> <span data-ttu-id="284a8-228">Dieses Tool wird mit dem .NET Framework im Ordner *%windir%\Microsoft.NET\Framework[64]\\[Frameworkversion]* installiert.</span><span class="sxs-lookup"><span data-stu-id="284a8-228">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\[framework version]*.</span></span> <span data-ttu-id="284a8-229">Der Standardpfad für die 32-Bit-Version lautet beispielsweise *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="284a8-229">For example, the default path for the 32-bit version is *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="284a8-230">Wenn der Prozess **installutil.exe** Fehler meldet, überprüfen Sie das Installationsprotokoll, um die Gründe zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="284a8-230">If the **installutil.exe** process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="284a8-231">Standardmäßig befindet sich das Protokoll im gleichen Ordner wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="284a8-231">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="284a8-232">Bei der Installation kann ein Fehler auftreten, wenn die <xref:System.ComponentModel.RunInstallerAttribute>-Klasse nicht in der `ProjectInstaller`-Klasse vorhanden ist, das Attribut nicht auf **true** festgelegt ist oder die `ProjectInstaller`-Klasse nicht als **public** gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="284a8-232">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, if the attribute is not set to **true**, or if the `ProjectInstaller` class is not marked **public**.</span></span>

<span data-ttu-id="284a8-233">Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="284a8-233">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="284a8-234">Starten und Ausführen des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-234">Start and run the service</span></span>

1. <span data-ttu-id="284a8-235">Öffnen Sie in Windows die Desktop-App **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="284a8-235">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="284a8-236">Drücken Sie **Windows**+**R**, um das Feld **Ausführen** zu öffnen, geben Sie dann **services.msc** ein, und drücken Sie die **EINGABETASTE**, oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="284a8-236">Press **Windows**+**R** to open the **Run** box, and then enter **services.msc** and press **Enter** or click **OK**.</span></span>

     <span data-ttu-id="284a8-237">Ihr Dienst sollte in **Dienste** alphabetisch nach dem Anzeigenamen aufgeführt sein, den Sie für ihn festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="284a8-237">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![MyNewService im Fenster "Dienste".](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="284a8-239">Öffnen Sie in **Dienste** das Kontextmenü für den Dienst, und wählen Sie dann **Start** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-239">In **Services**, open the shortcut menu for your service, and then choose **Start**.</span></span>

3. <span data-ttu-id="284a8-240">Um den Dienst zu beenden, öffnen Sie das Kontextmenü für den Dienst, und wählen Sie **Beenden** aus.</span><span class="sxs-lookup"><span data-stu-id="284a8-240">To stop the service, open the shortcut menu for the service, and then choose **Stop**.</span></span>

4. <span data-ttu-id="284a8-241">(Optional) An der Befehlszeile können Sie die Befehle `net start ServiceName` und `net stop ServiceName` zum Starten und Beenden Ihres Diensts verwenden.</span><span class="sxs-lookup"><span data-stu-id="284a8-241">(Optional) From the command line, you can use the commands `net start ServiceName` and `net stop ServiceName` to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="284a8-242">Überprüfen der Ereignisprotokollausgabe des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-242">Verify the event log output of your service</span></span>

1. <span data-ttu-id="284a8-243">Öffnen Sie die **Ereignisanzeige**, indem Sie mit der Eingabe von **Ereignisanzeige** im Suchfeld in der Windows-Taskleiste beginnen und dann in den Suchergebnissen **Ereignisanzeige** auswählen.</span><span class="sxs-lookup"><span data-stu-id="284a8-243">Open **Event Viewer** by starting to type **Event Viewer** in the search box on the Windows task bar, and then selecting **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="284a8-244">In Visual Studio können Sie auf Ereignisprotokolle zugreifen, indem Sie den **Server-Explorer** öffnen (Tastatur: **STRG**+**ALT**+**S**) und den Knoten **Ereignisprotokolle** für den lokalen Computer aufklappen.</span><span class="sxs-lookup"><span data-stu-id="284a8-244">In Visual Studio, you can access event logs by opening **Server Explorer** (Keyboard: **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="284a8-245">Klappen Sie in der **Ereignisanzeige** **Anwendungs- und Dienstprotokolle** auf.</span><span class="sxs-lookup"><span data-stu-id="284a8-245">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="284a8-246">Suchen Sie den Eintrag für **MyNewLog** (oder **MyLogFile1**, wenn Sie das optionale Verfahren befolgt haben, um Befehlszeilenargumente hinzuzufügen), und klappen Sie ihn auf.</span><span class="sxs-lookup"><span data-stu-id="284a8-246">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you followed the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="284a8-247">Sie sehen Einträge für die beiden Aktionen (Starten und Beenden), die Ihr Dienst ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="284a8-247">You should see entries for the two actions (start and stop) that your service performed.</span></span>

     ![Verwenden der Ereignisanzeige zum Anzeigen von Einträgen im Ereignisprotokoll](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a><span data-ttu-id="284a8-249">Deinstallieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="284a8-249">Uninstall the service</span></span>

1. <span data-ttu-id="284a8-250">Öffnen Sie die **Developer-Eingabeaufforderung für Visual Studio** mit Administratoranmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="284a8-250">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="284a8-251">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Ausgabe Ihres Projekts enthält.</span><span class="sxs-lookup"><span data-stu-id="284a8-251">In the command prompt window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="284a8-252">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="284a8-252">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="284a8-253">Wenn der Dienst erfolgreich deinstalliert ist, meldet **installutil.exe**, dass der Dienst erfolgreich entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="284a8-253">If the service uninstalls successfully, **installutil.exe** reports that your service was successfully removed.</span></span> <span data-ttu-id="284a8-254">Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="284a8-254">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="284a8-255">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="284a8-255">Next steps</span></span>

<span data-ttu-id="284a8-256">Jetzt, da Sie den Dienst erstellt haben, kann es sinnvoll sein, ein eigenständiges Setupprogramm zu erstellen, das von anderen für die Installation Ihres Windows-Diensts verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="284a8-256">Now that you've created the service, you might want to create a standalone setup program that others can use to install your Windows service.</span></span> <span data-ttu-id="284a8-257">ClickOnce unterstützt keine Windows-Dienste, aber Sie können das [WiX-Toolset](http://wixtoolset.org/) verwenden, um ein Installationsprogramm für einen Windows-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="284a8-257">ClickOnce doesn't support Windows services, but you can use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="284a8-258">Weitere Ideen finden Sie unter [Erstellen eines Installationspakets](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span><span class="sxs-lookup"><span data-stu-id="284a8-258">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>

<span data-ttu-id="284a8-259">Sie können die Verwendung einer <xref:System.ServiceProcess.ServiceController>-Komponente untersuchen, die es Ihnen ermöglicht, Befehle an den installierten Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="284a8-259">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

<span data-ttu-id="284a8-260">Sie können ein Installationsprogramm verwenden, um ein Ereignisprotokoll während der Installation statt während der Ausführung der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="284a8-260">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="284a8-261">Außerdem wird das Ereignisprotokoll vom Installationsprogramm gelöscht, wenn die Anwendung deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="284a8-261">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="284a8-262">Weitere Informationen finden Sie auf der Referenzseite <xref:System.Diagnostics.EventLogInstaller> .</span><span class="sxs-lookup"><span data-stu-id="284a8-262">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>

## <a name="see-also"></a><span data-ttu-id="284a8-263">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="284a8-263">See also</span></span>

- [<span data-ttu-id="284a8-264">Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="284a8-264">Windows service applications</span></span>](../../../docs/framework/windows-services/index.md)
- [<span data-ttu-id="284a8-265">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="284a8-265">Introduction to Windows service applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="284a8-266">Gewusst wie: Debuggen von Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="284a8-266">How to: Debug Windows service applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="284a8-267">Dienste (Windows)</span><span class="sxs-lookup"><span data-stu-id="284a8-267">Services (Windows)</span></span>](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
