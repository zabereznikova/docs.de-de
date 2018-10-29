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
ms.openlocfilehash: 79447ede354de104607117f657182023a2e57127
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123669"
---
# <a name="walkthrough-create-a-windows-service-app"></a>Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung

In diesem Artikel wird beschrieben, wie Sie eine einfache Windows-Dienstanwendung in Visual Studio erstellen, die Meldungen in ein Ereignisprotokoll schreibt.

## <a name="create-a-service"></a>Erstellen eines Diensts

Erstellen Sie zunächst das Projekt, und legen Sie die Werte fest, die für die korrekte Funktion des Diensts erforderlich sind.

1. Wählen Sie in Visual Studio auf der Menüleiste **Datei** > **Neu** > **Projekt** aus (oder drücken Sie **STRG**+**UMSCHALT**+**N**), um das Dialogfeld **Neues Projekt** zu öffnen.

2. Navigieren Sie zur Projektvorlage **Windows-Dienst**. Erweitern Sie **Installierte** > [**Visual C#** oder **Visual Basic**] > **Windows-Desktop**, oder geben Sie **Windows-Dienst** in das Suchfeld oben rechts ein.

   ![Windows-Dienstvorlage im Dialogfeld „Neues Projekt“ in Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > Wenn Sie die Vorlage **Windows-Dienst** nicht finden können, müssen Sie möglicherweise die Workload **.NET-Desktopentwicklung** installieren. Klicken Sie im Dialogfeld **Neues Projekt** auf den Link **Visual Studio-Installer öffnen** unten links. Wählen Sie im **Visual Studio-Installer** die Workload **.NET-Desktopentwicklung** und dann **Ändern** aus.

3. Benennen Sie das Projekt **MyNewService**, und wählen Sie dann **OK** aus.

   Die Projektvorlage beinhaltet eine Komponentenklasse mit dem Namen `Service1`, die von <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> erbt. Sie enthält einen großen Teil des grundlegenden Dienstcodes, etwa den Code zum Starten des Diensts.

## <a name="rename-the-service"></a>Umbenennen des Diensts

Benennen Sie den Dienst von **Service1** in **MyNewService** um.

1. Klicken Sie in der **Entwurfsansicht** für „Service1.cs“ (oder „Service1.vb“) auf den Link zum **Wechseln in die Codeansicht**. Klicken Sie mit der rechten Maustaste auf **Service1**, und wählen Sie im Kontextmenü **Umbenennen** aus. Geben Sie **MyNewService** ein, und drücken Sie dann die **EINGABETASTE**, oder klicken Sie auf **Übernehmen**.

2. Ändern Sie im **Eigenschaftenfenster** für **Service1.cs [Entwurf]** oder **Service1.vb [Entwurf]** den Wert von **ServiceName** in **MyNewService**.

3. Benennen Sie im **Projektmappen-Explorer** **Service1.cs** in **MyNewService.cs** um, oder benennen Sie **Service1.vb** in **MyNewService.vb** um.

## <a name="add-features-to-the-service"></a>Hinzufügen von Features zum Dienst

In diesem Abschnitt fügen Sie dem Windows-Dienst ein benutzerdefiniertes Ereignisprotokoll hinzu. Ereignisprotokolle sind Windows-Diensten in keiner Weise zugeordnet. Hier wird die <xref:System.Diagnostics.EventLog>-Komponente als Beispiel für die Art von Komponente verwendet, die Sie einem Windows-Dienst hinzufügen können.

### <a name="add-custom-event-log-functionality"></a>Hinzufügen einer benutzerdefinierten Ereignisprotokollfunktion

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.

2. Ziehen Sie im **Werkzeugkasten** aus dem Abschnitt **Komponenten**eine <xref:System.Diagnostics.EventLog> -Komponente in den Designer.

3. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Code anzeigen**aus.

4. Bearbeiten Sie den Konstruktor, um ein benutzerdefiniertes Ereignisprotokoll zu definieren:

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

### <a name="define-what-occurs-when-the-service-starts"></a>Definieren, was beim Starten des Diensts ausgeführt wird

Suchen Sie im Code-Editor die Methode <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, die beim Erstellen des Projekts automatisch überschrieben worden war. Fügen Sie eine Codezeile hinzu, die beim Starten des Diensts einen Eintrag in das Ereignisprotokoll schreibt:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

Eine Dienstanwendung soll eine lange Laufzeit haben, damit sie in der Regel etwas abfragt oder etwas im System überwacht. Die Überwachung wird in der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode eingerichtet. Allerdings erfolgt die Überwachung jedoch nicht durch <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Die <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode muss zum Betriebssystem zurückkehren, sobald die Ausführung des Dienstes begonnen hat. Sie darf keine Endlosschleife oder Blöcke ausführen. Wenn Sie einen einfachen Abrufmechanismus einrichten, können Sie die Komponente <xref:System.Timers.Timer?displayProperty=nameWithType> wie folgt verwenden: Legen Sie in der Methode <xref:System.ServiceProcess.ServiceBase.OnStart%2A> die Parameter für die Komponente fest, und legen Sie dann die Eigenschaft <xref:System.Timers.Timer.Enabled%2A> auf `true`. Der Zeitgeber löst dann regelmäßig zu der Zeit Ereignisse im Code aus, zu der der Dienst seine Überwachung ausführen könnte. Sie können hierfür den folgenden Code verwenden:

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

Fügen Sie der Klasse eine Membervariable hinzu. Sie enthält den Bezeichner des nächsten Ereignisses, das in das Ereignisprotokoll geschrieben werden soll.

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

Fügen Sie eine neue Methode zum Verarbeiten des Zeitgeberereignisses hinzu:

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

Möglicherweise möchten Sie Aufgaben mit Arbeitsthreads im Hintergrund statt Ihre Arbeit auf der Haupt-Thread ausführen. Weitere Informationen finden Sie unter <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Definieren, was beim Beenden des Diensts ausgeführt wird

Fügen Sie der Methode <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine Codezeile hinzu, die beim Beenden des Diensts einen Eintrag zum Ereignisprotokoll hinzufügt:

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Definieren weiterer Aktionen für den Dienst

Sie können die Methoden <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> und <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> überschreiben, um zusätzliche Verarbeitungsschritte für Ihre Komponente zu definieren. Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> -Methode überschrieben wird.

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

Einige benutzerdefinierte Aktionen müssen eintreten, wenn ein Windows-Dienst von der <xref:System.Configuration.Install.Installer> Klasse installiert wird. Visual Studio kann diese Installationsprogramme speziell für einen Windows-Dienst erstellen und sie dem Projekt hinzufügen.

## <a name="set-service-status"></a>Festlegen des Dienststatus

Dienste melden ihren Status mit dem Dienststeuerungs-Manager, damit Benutzer erkennen können, ob ein Dienst ordnungsgemäß ausgeführt wird. Dienste, die von standardmäßig von <xref:System.ServiceProcess.ServiceBase> übernommen werden, melden eine begrenzte Anzahl von Statuseinstellungen, darunter Beendet, Angehalten und Werden ausgeführt. Wenn es etwas länger dauert, bis ein Dienst startet, kann es hilfreich sein, einen Status Start ausstehend zu melden. Sie können auch die Statuseinstellungen Start ausstehend und Stopp ausstehend durch Hinzufügen von Code implementieren, der in Windows die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) aufruft.

Zum Implementieren des Dienststatus „ausstehend“:

1. Fügen Sie eine `using`-Anweisung oder eine `Imports`-Deklaration für den <xref:System.Runtime.InteropServices?displayProperty=nameWithType>-Namespace zur Datei MyNewService.cs oder MyNewService.vb hinzu:

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. Fügen Sie folgenden Code zum MyNewService.cs hinzu, um die `ServiceState` Werte zu deklarieren und um eine Struktur für den Status hinzuzufügen, die Sie in einem Plattformaufruf verwenden:

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

3. Deklarieren Sie nun in der Klasse `MyNewService` die Funktion [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mithilfe eines [Plattformaufrufs](../interop/consuming-unmanaged-dll-functions.md):

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. Um den Status Start ausstehend zu implementieren, fügen Sie den folgenden Code am Anfang der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> Methode hinzu:

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

5. Fügen Sie den Code hinzu, um den Status Wird ausgeführt am Ende der <xref:System.ServiceProcess.ServiceBase.OnStart%2A> -Methode festzulegen.

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

6. (Optional) Wiederholen Sie diesen Vorgang für die <xref:System.ServiceProcess.ServiceBase.OnStop%2A> Methode.

> [!NOTE]
> Das Dialogfeld [Dienststeuerungs-Manager](/windows/desktop/Services/service-control-manager) verwendet die Member `dwWaitHint` und `dwCheckpoint` der [SERVICE_STATUS-Struktur](/windows/desktop/api/winsvc/ns-winsvc-_service_status), um zu bestimmen, wie lange bis zum Starten oder Herunterfahren eines Windows-Diensts gewartet werden muss. Wenn Ihre Methoden <xref:System.ServiceProcess.ServiceBase.OnStart%2A> und <xref:System.ServiceProcess.ServiceBase.OnStop%2A> eine lange Ausführungszeit haben, kann Ihr Dienst durch das erneute Aufrufen von [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mit einem erhöhten `dwCheckPoint`-Wert mehr Zeit anfordern.

## <a name="add-installers-to-the-service"></a>Hinzufügen von Installern zum Dienst

Bevor Sie einen Windows-Dienst ausführen können, müssen Sie ihn bei der Installation im Dienststeuerungs-Manager registrieren. Sie können Installationsprogramme dem Projekt hinzufügen, die die Registrierungsdetails behandelt.

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für **MyNewService.cs** oder **MyNewService.vb**, und wählen Sie dann **Designer anzeigen**aus.

2. Klicken Sie auf den Hintergrund des Designers, um den Dienst selbst, nicht Elemente seines Inhalts, zu markieren.

3. Öffnen Sie das Kontextmenü für das Designer-Fenster (wenn Sie ein Zeigegerät verwenden, rechtsklicken Sie in das Fenster) und wählen Sie dann **Installer hinzufügen**.

   Standardmäßig wird dem Projekt eine Komponentenklasse mit zwei Installationsprogrammen hinzugefügt. Die Komponente erhält den Namen **ProjectInstaller**; die darin enthaltenen Installationsprogramme sind zum einen das Installationsprogramm für den Dienst und zum andern das Installationsprogramm für den zugeordneten Prozess des Diensts.

4. Klicken Sie in der Ansicht **Entwurf** für **ProjectInstaller**auf **ServiceInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt, bzw. auf **serviceInstaller1** , wenn es sich um ein Visual C#-Projekt handelt.

5. Vergewissern Sie sich im Fenster **Eigenschaften** , dass die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft auf **MyNewService**festgelegt ist.

6. Legen Sie die **Beschreibung** -Eigenschaft auf Text, wie z. B. "Ein Beispieldienst" fest. Dieser Text wird im Fenster Dienste angezeigt und hilft dem Benutzer den Dienst zu identifizieren, und zu verstehen, wofür er verwendet wird.

7. Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> -Eigenschaft auf den Text fest, der im Fenster Dienste in der Spalte **Name** angezeigt werden soll. Beispielsweise können Sie "MyNewService Display Name" eingeben. Dieser Name kann sich von der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> -Eigenschaft unterscheidet, die dem Namen entspricht, der vom System verwendet wird (z. B. bei Verwendung des `net start` -Befehls zum Starten des Dienstes).

8. Legen Sie die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> -Eigenschaft auf <xref:System.ServiceProcess.ServiceStartMode.Automatic>fest.

     ![Installer-Eigenschaften für einen Windows-Dienst](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_Installereigenschaften")

9. Klicken Sie im Designer auf **ServiceProcessInstaller1** , wenn es sich um ein Visual Basic#-Projekt handelt, bzw. auf **serviceProcessInstaller1** , wenn es sich um ein Visual Basic-Projekt handelt. Legen Sie die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> -Eigenschaft auf <xref:System.ServiceProcess.ServiceAccount.LocalSystem>fest. Dies bewirkt, dass der Dienst installiert und mit dem lokalen Systemkonto ausgeführt wird.

    > [!IMPORTANT]
    > Das Konto <xref:System.ServiceProcess.ServiceAccount.LocalSystem> verfügt über ein breites Berechtigungsspektrum, einschließlich der Berechtigung zum Schreiben in das Ereignisprotokoll. Bei der Verwendung dieses Kontos ist allerdings Vorsicht geboten, da sich dadurch das Risiko von Malware-Angriffen erhöhen kann. Für andere Aufgaben sollten Sie das Konto <xref:System.ServiceProcess.ServiceAccount.LocalService> verwenden, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden anonyme Anmeldeinformationen übergeben. Dieses Beispiel schlägt fehl, wenn Sie versuchen, das <xref:System.ServiceProcess.ServiceAccount.LocalService> -Konto zu verwenden, da zum Schreiben in das Ereignisprotokoll eine Genehmigung benötigt wird.

Weitere Informationen zu Installern finden Sie unter [Gewusst wie: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).

## <a name="optional-set-startup-parameters"></a>(Optional) Festlegen der Startparameter

Ein Windows-Dienst akzeptiert wie jede andere ausführbare Datei Befehlszeilenargumente oder Startparameter. Wenn Sie einen Code zum Startparameterprozess hinzufügen, können Benutzer den Dienst mithilfe des Fensters "Dienste" in der Windows-Systemsteuerung mit ihren eigenen benutzerdefinierten Startparametern starten. Diese Startparameter werden jedoch nicht beim nächsten Start des Dienst beibehalten. Um Startparameter dauerhaft festzulegen, können Sie diese in der Registrierung festlegen, wie in diesem Verfahren dargestellt.

> [!NOTE]
> Bevor Sie sich entscheiden, die Startparameter hinzuzufügen, ziehen Sie in Betracht, ob dies die beste Möglichkeit für die Übertragung von Informationen an Ihren Dienst ist. Obwohl Startparameter einfach zu verwenden und zu analysieren sind, und sie Benutzer sie leicht überschreiben können, sind sie möglicherweise ohne die Dokumentation schwerer zu erkennen und zu verwenden. In der Regel, wenn der Dienst mehr als nur ein paar Startparameter erfordert, sollten Sie stattdessen die Verwendung des Verzeichnisses oder einer Konfigurationsdatei erwägen. Jeder Windows-Dienst ist ein Eintrag im Verzeichnis unter **HKLM\System\CurrentControlSet\services**. Gemäß dem Service-Schlüssel können Sie den Teilschlüssel **Parameter** zum Speichern von Informationen verwenden, auf die Ihr Dienst zugreifen kann. Sie können Konfigurationsdateien für einen Windows-Dienst genauso wie für andere Arten von Programmen verwenden. Beispielcode finden Sie unter <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.

So fügen Sie Startparameter hinzu:

1. Fügen Sie in der `Main`-Methode in Program.cs oder in MyNewService.Designer.vb einen Eingabeparameter hinzu, um den Dienstkonstruktor zu übergeben:

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

2. Ändern Sie den `MyNewService` -Konstruktor wie folgt:

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

   Dieser Code legt die Ereignisquelle und den Protokollnamen gemäß der angegebenen Startparameter fest oder verwendet Standardwerte, wenn keine Argumente angegeben werden.

3. Um Befehlszeilenargumente anzugeben, fügen Sie den folgenden Code zu der `ProjectInstaller` -Klasse in ProjectInstaller.cs oder ProjectInstaller.vb hinzu:

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

   Dieser Code ändert den **ImagePath** -Registrierungsschlüssel, der in der Regel den vollständigen Pfad der ausführbaren Datei für den Windows-Dienst enthält, indem er ihm die Standardwerte für die Parameter hinzufügt. Die Anführungszeichen rund um den Pfad (und um jeden einzelnen Parameter) sind erforderlich, um den Dienst korrekt zu starten. Um die Startparameter für diesen Windows-Dienst zu ändern, können Benutzer die Parameter ändern, die im **ImagePath** -Registrierungsschlüssel angegeben sind, obwohl es besser wäre, ihn programmgesteuert zu ändern und die Funktionalität für Benutzer in einer geeigneten Form (z. B. in einem Dienstprogramm Verwaltung oder Konfiguration) verfügbar zu machen.

## <a name="build-the-service"></a>Erstellen des Diensts

1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.

   Die Eigenschaftenseiten für Ihr Projekt werden angezeigt.

2. Klicken Sie in der Registerkarte **Anwendung** in der Liste **Startobjekt** auf **MyNewService.Program**.

3. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt und wählen Sie dann **Erstellen** aus, um das Projekt zu erstellen (oder drücken Sie **STRG**+**UMSCHALT**+**B**).

## <a name="install-the-service"></a>Installieren des Diensts

Nachdem Sie den Windows-Dienst nun erstellt haben, können Sie ihn installieren. Um einen Windows-Dienst zu installieren, müssen Sie über Administratorberechtigungen für den Computer verfügen, auf dem Sie ihn installieren.

1. Öffnen Sie die **Developer-Eingabeaufforderung für Visual Studio** mit Administratoranmeldeinformationen. Wenn Sie eine Maus verwenden, klicken Sie mit der rechten Maustaste im Windows-Startmenü auf **Developer-Eingabeaufforderung für VS 2017**, und wählen Sie dann **Mehr** > **Als Administrator ausführen** aus.

2. Navigieren Sie im Fenster **Developer-Eingabeaufforderung** zu dem Ordner, der die Ausgabe Ihres Projekts enthält (standardmäßig das Unterverzeichnis *\bin\Debug* Ihres Projekts).

3. Geben Sie folgenden Befehl ein:

    ```shell
    installutil.exe MyNewService.exe
    ```

    Wenn der Dienst erfolgreich installiert wird, meldet **installutil.exe** Erfolg. Wenn das System **InstallUtil.exe** nicht finden kann, stellen Sie sicher, dass sie auf Ihrem Computer vorhanden ist. Dieses Tool wird mit dem .NET Framework im Ordner *%windir%\Microsoft.NET\Framework[64]\\[Frameworkversion]* installiert. Der Standardpfad für die 32-Bit-Version lautet beispielsweise *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.

    Wenn der Prozess **installutil.exe** Fehler meldet, überprüfen Sie das Installationsprotokoll, um die Gründe zu bestimmen. Standardmäßig befindet sich das Protokoll im gleichen Ordner wie die ausführbare Datei. Bei der Installation kann ein Fehler auftreten, wenn die <xref:System.ComponentModel.RunInstallerAttribute>-Klasse nicht in der `ProjectInstaller`-Klasse vorhanden ist, das Attribut nicht auf **true** festgelegt ist oder die `ProjectInstaller`-Klasse nicht als **public** gekennzeichnet ist.

Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="start-and-run-the-service"></a>Starten und Ausführen des Diensts

1. Öffnen Sie in Windows die Desktop-App **Dienste**. Drücken Sie **Windows**+**R**, um das Feld **Ausführen** zu öffnen, geben Sie dann **services.msc** ein, und drücken Sie die **EINGABETASTE**, oder klicken Sie auf **OK**.

     Ihr Dienst sollte in **Dienste** alphabetisch nach dem Anzeigenamen aufgeführt sein, den Sie für ihn festgelegt haben.

     ![MyNewService im Fenster "Dienste".](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. Öffnen Sie in **Dienste** das Kontextmenü für den Dienst, und wählen Sie dann **Start** aus.

3. Um den Dienst zu beenden, öffnen Sie das Kontextmenü für den Dienst, und wählen Sie **Beenden** aus.

4. (Optional) An der Befehlszeile können Sie die Befehle `net start ServiceName` und `net stop ServiceName` zum Starten und Beenden Ihres Diensts verwenden.

### <a name="verify-the-event-log-output-of-your-service"></a>Überprüfen der Ereignisprotokollausgabe des Diensts

1. Öffnen Sie die **Ereignisanzeige**, indem Sie mit der Eingabe von **Ereignisanzeige** im Suchfeld in der Windows-Taskleiste beginnen und dann in den Suchergebnissen **Ereignisanzeige** auswählen.

   > [!TIP]
   > In Visual Studio können Sie auf Ereignisprotokolle zugreifen, indem Sie den **Server-Explorer** öffnen (Tastatur: **STRG**+**ALT**+**S**) und den Knoten **Ereignisprotokolle** für den lokalen Computer aufklappen.

2. Klappen Sie in der **Ereignisanzeige** **Anwendungs- und Dienstprotokolle** auf.

3. Suchen Sie den Eintrag für **MyNewLog** (oder **MyLogFile1**, wenn Sie das optionale Verfahren befolgt haben, um Befehlszeilenargumente hinzuzufügen), und klappen Sie ihn auf. Sie sehen Einträge für die beiden Aktionen (Starten und Beenden), die Ihr Dienst ausgeführt hat.

     ![Verwenden der Ereignisanzeige zum Anzeigen von Einträgen im Ereignisprotokoll](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a>Deinstallieren des Diensts

1. Öffnen Sie die **Developer-Eingabeaufforderung für Visual Studio** mit Administratoranmeldeinformationen.

2. Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, der die Ausgabe Ihres Projekts enthält.

3. Geben Sie folgenden Befehl ein:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Wenn der Dienst erfolgreich deinstalliert ist, meldet **installutil.exe**, dass der Dienst erfolgreich entfernt wurde. Weitere Informationen finden Sie unter [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="next-steps"></a>Nächste Schritte

Jetzt, da Sie den Dienst erstellt haben, kann es sinnvoll sein, ein eigenständiges Setupprogramm zu erstellen, das von anderen für die Installation Ihres Windows-Diensts verwendet werden kann. ClickOnce unterstützt keine Windows-Dienste, aber Sie können das [WiX-Toolset](http://wixtoolset.org/) verwenden, um ein Installationsprogramm für einen Windows-Dienst zu erstellen. Weitere Ideen finden Sie unter [Erstellen eines Installationspakets](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

Sie können die Verwendung einer <xref:System.ServiceProcess.ServiceController>-Komponente untersuchen, die es Ihnen ermöglicht, Befehle an den installierten Dienst zu senden.

Sie können ein Installationsprogramm verwenden, um ein Ereignisprotokoll während der Installation statt während der Ausführung der Anwendung zu erstellen. Außerdem wird das Ereignisprotokoll vom Installationsprogramm gelöscht, wenn die Anwendung deinstalliert wird. Weitere Informationen finden Sie auf der Referenzseite <xref:System.Diagnostics.EventLogInstaller> .

## <a name="see-also"></a>Siehe auch

- [Windows-Dienstanwendungen](../../../docs/framework/windows-services/index.md)
- [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Gewusst wie: Debuggen von Windows-Dienstanwendungen](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Dienste (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
