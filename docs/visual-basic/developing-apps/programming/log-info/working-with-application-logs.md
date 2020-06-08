---
title: Arbeiten mit Anwendungsprotokollen
ms.date: 07/20/2015
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
ms.openlocfilehash: e33efac8f65832c87d5c9271eba25c2ca1d1803b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387594"
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="74c42-102">Arbeiten mit Anwendungsprotokollen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74c42-102">Working with Application Logs in Visual Basic</span></span>

<span data-ttu-id="74c42-103">Mithilfe der `My.Application.Log` - und `My.Log` -Objekte ist es einfach, Protokollierungs- und Ablaufverfolgungsinformationen in Protokolle zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="74c42-103">The `My.Application.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>

## <a name="how-messages-are-logged"></a><span data-ttu-id="74c42-104">Protokollierung von Meldungen</span><span class="sxs-lookup"><span data-stu-id="74c42-104">How Messages are Logged</span></span>

<span data-ttu-id="74c42-105">Zuerst wird der Schweregrad der Meldung mithilfe der <xref:System.Diagnostics.TraceSource.Switch%2A> -Eigenschaft der <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> -Eigenschaft des Protokolls überprüft.</span><span class="sxs-lookup"><span data-stu-id="74c42-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="74c42-106">Standardmäßig werden nur Meldungen vom Schweregrad "Information" und höher an die Nachverfolgungslistener übergeben, die in der `TraceListener` -Auflistung des Protokolls angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="74c42-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="74c42-107">Anschließend vergleicht jeder Listener den Schweregrad der Meldung mit der Eigenschaft <xref:System.Diagnostics.TraceSource.Switch%2A> des Listeners.</span><span class="sxs-lookup"><span data-stu-id="74c42-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="74c42-108">Wenn der Schweregrad der Meldung ausreichend hoch ist, schreibt der Listener die Meldung.</span><span class="sxs-lookup"><span data-stu-id="74c42-108">If the message's severity is high enough, the listener writes out the message.</span></span>

<span data-ttu-id="74c42-109">Im folgenden Diagramm ist dargestellt, wie eine in die `WriteEntry` -Methode geschriebene Meldung an die `WriteLine` -Methoden der Ablaufverfolgungslistener des Protokolls übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="74c42-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>

![Abbildung, die den My-Protokollaufruf zeigt.](./media/working-with-application-logs/my-log-call-messages.png)

<span data-ttu-id="74c42-111">Das Verhalten von Protokoll und Ablaufverfolgungslistener lässt sich durch Ändern der Konfigurationsdatei der Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="74c42-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="74c42-112">Das folgende Diagramm stellt die Entsprechung zwischen den Teilen des Protokolls und der Konfigurationsdatei dar.</span><span class="sxs-lookup"><span data-stu-id="74c42-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>

![Abbildung, die die My-Protokollkonfiguration zeigt.](./media/working-with-application-logs/my-log-configuration.png)

## <a name="where-messages-are-logged"></a><span data-ttu-id="74c42-114">Protokollspeicherorte von Meldungen</span><span class="sxs-lookup"><span data-stu-id="74c42-114">Where Messages are Logged</span></span>

<span data-ttu-id="74c42-115">Wenn die Assembly keine Konfigurationsdatei aufweist, schreiben die Objekte `My.Application.Log` und `My.Log` in die Debugausgabe der Anwendung (mithilfe der <xref:System.Diagnostics.DefaultTraceListener> -Klasse).</span><span class="sxs-lookup"><span data-stu-id="74c42-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="74c42-116">Darüber hinaus schreibt das `My.Application.Log` -Objekt in die Protokolldatei der Assembly (mithilfe der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse), während das `My.Log` -Objekt in die Ausgabe der ASP.NET-Webseite schreibt (mithilfe der <xref:System.Web.WebPageTraceListener> -Klasse).</span><span class="sxs-lookup"><span data-stu-id="74c42-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>

<span data-ttu-id="74c42-117">Die Debugausgabe kann beim Ausführen der Anwendung im Debugmodus im Visual Studio-Fenster **Ausgabe** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="74c42-117">The debug output can be viewed in the Visual Studio **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="74c42-118">Klicken Sie zum Öffnen des Fensters **Ausgabe** auf das Menüelement **Debug** , zeigen Sie auf **Fenster**, und klicken Sie dann auf **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="74c42-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="74c42-119">Wählen Sie im Fenster **Ausgabe** im Feld **Ausgabe anzeigen von** den Wert **Debug** aus.</span><span class="sxs-lookup"><span data-stu-id="74c42-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>

<span data-ttu-id="74c42-120">Standardmäßig schreibt `My.Application.Log` die Protokolldatei in den Pfad für die Anwendungsdaten des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="74c42-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="74c42-121">Diesen Pfad können Sie aus der Eigenschaft <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> des <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> -Objekts abrufen.</span><span class="sxs-lookup"><span data-stu-id="74c42-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="74c42-122">Das Format des Pfades ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="74c42-122">The format of that path is as follows:</span></span>

`BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`

<span data-ttu-id="74c42-123">Ein typischer Wert für `BasePath` ist etwa dieser:</span><span class="sxs-lookup"><span data-stu-id="74c42-123">A typical value for `BasePath` is as follows.</span></span>

<span data-ttu-id="74c42-124">C:\Dokumente und Einstellungen\\`username`\Anwendungsdaten</span><span class="sxs-lookup"><span data-stu-id="74c42-124">C:\Documents and Settings\\`username`\Application Data</span></span>

<span data-ttu-id="74c42-125">Die Werte von `CompanyName`, `ProductName`und `ProductVersion` stammen aus den Assemblyinformationen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="74c42-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="74c42-126">Der Name der Protokolldatei hat die Form " *AssemblyName*.log", wobei *AssemblyName* der Dateiname der Assembly ohne Erweiterung ist.</span><span class="sxs-lookup"><span data-stu-id="74c42-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="74c42-127">Wenn mehr als eine Protokolldatei erforderlich ist, etwa wenn die ursprüngliche Protokolldatei zu dem Zeitpunkt, da die Anwendung versucht, in es zu schreiben, nicht verfügbar ist, hat der Name der Protokolldatei die Form " *AssemblyName*-*iteration*.log", wobei `iteration` ein positiver `Integer`.</span><span class="sxs-lookup"><span data-stu-id="74c42-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>

<span data-ttu-id="74c42-128">Sie können das Standardverhalten außer Kraft setzen, indem Sie die Konfigurationsdateien des Computers und der Anwendung hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="74c42-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="74c42-129">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="74c42-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](walkthrough-changing-where-my-application-log-writes-information.md).</span></span>

## <a name="configuring-log-settings"></a><span data-ttu-id="74c42-130">Konfigurieren von Protokolleinstellungen</span><span class="sxs-lookup"><span data-stu-id="74c42-130">Configuring Log Settings</span></span>

<span data-ttu-id="74c42-131">Die Standardimplementierung des `Log` -Objekts funktioniert ohne Anwendungskonfigurationsdatei, "app.config". Um die Standardwerte zu ändern, müssen Sie eine Konfigurationsdatei mit den neuen Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="74c42-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="74c42-132">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Filterung der Ausgabe von „My.Application.Log“](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="74c42-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

<span data-ttu-id="74c42-133">Die Protokollkonfigurationsabschnitte befinden sich im `<system.diagnostics>` -Knoten im `<configuration>` -Hauptknoten der app.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="74c42-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="74c42-134">Die Protokollinformationen sind in mehreren Knoten definiert:</span><span class="sxs-lookup"><span data-stu-id="74c42-134">Log information is defined in several nodes:</span></span>

- <span data-ttu-id="74c42-135">Die Listener für das `Log` -Objekt sind in dem `<sources>` -Knoten mit dem Namen "DefaultSource" definiert.</span><span class="sxs-lookup"><span data-stu-id="74c42-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>

- <span data-ttu-id="74c42-136">Der Schweregradfilter für das `Log` -Objekt ist in dem `<switches>` -Knoten mit dem Namen "DefaultSwitch" definiert.</span><span class="sxs-lookup"><span data-stu-id="74c42-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>

- <span data-ttu-id="74c42-137">Die Protokolllistener sind im `<sharedListeners>` -Knoten definiert.</span><span class="sxs-lookup"><span data-stu-id="74c42-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>

 <span data-ttu-id="74c42-138">Beispiele für `<sources>`-, `<switches>`- und `<sharedListeners>` -Knoten sind im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="74c42-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="DefaultSource" switchName="DefaultSwitch">
        <listeners>
          <add name="FileLog"/>
        </listeners>
      </source>
    </sources>
    <switches>
      <add name="DefaultSwitch" value="Information" />
    </switches>
    <sharedListeners>
      <add name="FileLog"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"
        initializeData="FileLogWriter"
      />
    </sharedListeners>
  </system.diagnostics>
</configuration>
```

## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="74c42-139">Ändern der Protokolleinstellungen nach der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="74c42-139">Changing Log Settings after Deployment</span></span>

<span data-ttu-id="74c42-140">Beim Entwickeln einer Anwendung werden deren Konfigurationseinstellungen in der app.config-Datei gespeichert, wie in den Beispielen oben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="74c42-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="74c42-141">Nach dem Bereitstellen der Anwendung kann das Protokoll durch Bearbeiten der Konfigurationsdatei weiterhin konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="74c42-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="74c42-142">In einer Windows-basierten Anwendung ist der Name dieser Datei " *applicationName*.exe.config", und sie muss sich im gleichen Ordner wie die Programmdatei befinden.</span><span class="sxs-lookup"><span data-stu-id="74c42-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="74c42-143">Für eine Webanwendung ist dies die "Web.config"-Datei, die dem Projekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="74c42-143">For a Web application, this is the Web.config file associated with the project.</span></span>

<span data-ttu-id="74c42-144">Wenn die Anwendung den Code, der eine Instanz einer Klasse erstellt, zum ersten Mal ausführt, prüft sie die Konfigurationsdatei auf Informationen zum Objekt.</span><span class="sxs-lookup"><span data-stu-id="74c42-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="74c42-145">Für das `Log` -Objekt geschieht das beim ersten Zugriff auf das `Log` -Objekt.</span><span class="sxs-lookup"><span data-stu-id="74c42-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="74c42-146">Das System durchsucht die Konfigurationsdatei für jedes Objekt nur ein Mal – wenn die Anwendung das Objekt erstmalig erstellt.</span><span class="sxs-lookup"><span data-stu-id="74c42-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="74c42-147">Daher müssen Sie ggf. die Anwendung erneut starten, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="74c42-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>

<span data-ttu-id="74c42-148">In einer bereitgestellten Anwendung aktivieren Sie Ablaufverfolgungscode, indem Sie Schalterobjekte neu konfigurieren, bevor die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="74c42-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="74c42-149">Üblicherweise umfasst dies das Aktivieren oder Deaktivieren der Schalterobjekte oder Ändern der Ablaufverfolgungsebenen und dann das Neustarten Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="74c42-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="74c42-150">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="74c42-150">Security Considerations</span></span>

<span data-ttu-id="74c42-151">Berücksichtigen Sie beim Schreiben von Daten in das Protokoll folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="74c42-151">Consider the following when writing data to the log:</span></span>

- <span data-ttu-id="74c42-152">**Vermeiden Sie die Preisgabe von Benutzerinformationen**</span><span class="sxs-lookup"><span data-stu-id="74c42-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="74c42-153">. Stellen Sie sicher, dass die Anwendung nur genehmigte Informationen in das Protokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="74c42-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="74c42-154">Beispielsweise kann es akzeptabel sein, dass ein Anwendungsprotokoll Benutzernamen enthält, in keinem Fall jedoch Benutzerkennwörter.</span><span class="sxs-lookup"><span data-stu-id="74c42-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>

- <span data-ttu-id="74c42-155">**Achten Sie auf sichere Protokollspeicherorte**</span><span class="sxs-lookup"><span data-stu-id="74c42-155">**Make log locations secure.**</span></span> <span data-ttu-id="74c42-156">. Jedes Protokoll, das möglicherweise vertrauliche Informationen enthält, sollte an einem sicheren Ort gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="74c42-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>

- <span data-ttu-id="74c42-157">**Vermeiden Sie irreführende Informationen**</span><span class="sxs-lookup"><span data-stu-id="74c42-157">**Avoid misleading information.**</span></span> <span data-ttu-id="74c42-158">. Im Allgemeinen sollte die Anwendung alle von einem Benutzer eingegeben Daten überprüfen, bevor Sie sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="74c42-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="74c42-159">Dies umfasst auch das Schreiben von Daten in das Anwendungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="74c42-159">This includes writing data to the application log.</span></span>

- <span data-ttu-id="74c42-160">**Vermeiden Sie Dienstverweigerung**</span><span class="sxs-lookup"><span data-stu-id="74c42-160">**Avoid denial of service.**</span></span> <span data-ttu-id="74c42-161">. Wenn die Anwendung zu viele Informationen in das Protokoll schreibt, kann das Protokolls voll werden, oder die Suche nach wichtigen Informationen gestaltet sich schwierig.</span><span class="sxs-lookup"><span data-stu-id="74c42-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>

## <a name="see-also"></a><span data-ttu-id="74c42-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c42-162">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="74c42-163">Protokollieren von Informationen aus der Anwendung</span><span class="sxs-lookup"><span data-stu-id="74c42-163">Logging Information from the Application</span></span>](index.md)
