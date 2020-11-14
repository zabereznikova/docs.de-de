---
title: Filtern der Ausgabe von „My.Application.Log“
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
ms.openlocfilehash: e77a56b2be33555bc02157c8e643ac655b083bc3
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282211"
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="bc658-102">Exemplarische Vorgehensweise: Filterung der Ausgaben von "My.Application.Log" (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc658-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>

<span data-ttu-id="bc658-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie das standardmäßige Filtern von Protokollen für das `My.Application.Log`-Objekt ändern, um zu steuern, welche Informationen vom `Log`-Objekt an die Listener übergeben werden und welche Informationen von den Listenern geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="bc658-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="bc658-104">Sie können das Protokollierungsverhalten auch nach dem Erstellen der Anwendung ändern, da die Konfigurationsinformationen in der Konfigurationsdatei der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="bc658-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>

## <a name="getting-started"></a><span data-ttu-id="bc658-105">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="bc658-105">Getting Started</span></span>

<span data-ttu-id="bc658-106">Alle Nachrichten, die von `My.Application.Log` geschrieben werden, haben einen zugeordneten Schweregrad, den die Filtermechanismen verwenden, um die Protokollausgabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bc658-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="bc658-107">Diese Beispielanwendung verwendet `My.Application.Log`-Methoden zum Schreiben mehrerer Protokollmeldungen mit unterschiedlichen Schweregraden.</span><span class="sxs-lookup"><span data-stu-id="bc658-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>

#### <a name="to-build-the-sample-application"></a><span data-ttu-id="bc658-108">So installieren Sie die Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="bc658-108">To build the sample application</span></span>

1. <span data-ttu-id="bc658-109">Öffnen Sie ein neues Visual Basic-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="bc658-109">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="bc658-110">Fügen Sie eine Schaltfläche mit dem Namen „Button1“ zu „Form1“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc658-110">Add a button named Button1 to Form1.</span></span>

3. <span data-ttu-id="bc658-111">Fügen Sie im <xref:System.Windows.Forms.Control.Click>-Ereignishandler den folgenden Code für „Button1“ hinzu:</span><span class="sxs-lookup"><span data-stu-id="bc658-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>

     [!code-vb[VbVbcnMyApplicationLogFiltering#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyApplicationLogFiltering/VB/Form1.vb#1)]

4. <span data-ttu-id="bc658-112">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-112">Run the application in the debugger.</span></span>

5. <span data-ttu-id="bc658-113">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="bc658-113">Press **Button1**.</span></span>

     <span data-ttu-id="bc658-114">Die Anwendung schreibt die folgenden Informationen in die Debugausgabe und die Protokolldatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bc658-114">The application writes the following information to the application's debug output and log file.</span></span>

     `DefaultSource Information: 0 : In Button1_Click`

     `DefaultSource Error: 2 : Error in the application.`

6. <span data-ttu-id="bc658-115">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bc658-115">Close the application.</span></span>

     <span data-ttu-id="bc658-116">Informationen zum Anzeigen des Ausgabefensters der Anwendung finden Sie unter [Ausgabefenster](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="bc658-116">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="bc658-117">Informationen zum Speicherort der Protokolldatei der Anwendung finden Sie unter [Walkthrough: Determining Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt)](walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="bc658-117">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc658-118">Standardmäßig leert die Anwendung die Ausgabe der Protokolldatei, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="bc658-118">By default, the application flushes the log-file output when the application closes.</span></span>

     <span data-ttu-id="bc658-119">Im oben stehenden Beispiel erzeugt der zweite Aufruf der <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>-Methode und der Aufruf der <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>-Methode eine Protokollausgabe, während dies bei dem ersten und letzten Aufruf der `WriteEntry`-Methode nicht passiert.</span><span class="sxs-lookup"><span data-stu-id="bc658-119">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="bc658-120">Dies liegt daran, dass die Schweregrade von `WriteEntry` und `WriteException` „Information“ und „Error“ sind, die beide durch das standardmäßige Filtern von Protokollen des Objekts `My.Application.Log` zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="bc658-120">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="bc658-121">Bei Ereignissen mit den Schweregraden „Start“ und „Stop“ wird das Erzeugen von Protokollausgaben verhindert.</span><span class="sxs-lookup"><span data-stu-id="bc658-121">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>

## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="bc658-122">Filterung für alle „My.Application.Log“-Listener</span><span class="sxs-lookup"><span data-stu-id="bc658-122">Filtering for All My.Application.Log Listeners</span></span>

<span data-ttu-id="bc658-123">Das `My.Application.Log`-Objekt verwendet einen <xref:System.Diagnostics.SourceSwitch> mit dem Namen `DefaultSwitch`, um zu steuern, welche Meldungen von den Methoden `WriteEntry` und `WriteException` an die Protokolllistener übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="bc658-123">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="bc658-124">Sie können `DefaultSwitch` in der Konfigurationsdatei der Anwendung konfigurieren, indem Sie dessen Wert auf einen der <xref:System.Diagnostics.SourceLevels>-Enumerationswerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="bc658-124">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="bc658-125">Standardmäßig ist der Wert „Information“.</span><span class="sxs-lookup"><span data-stu-id="bc658-125">By default, its value is "Information".</span></span>

<span data-ttu-id="bc658-126">In dieser Tabelle werden die Schweregrade gezeigt, die von Protokollen für das Schreiben einer Nachricht an die Listener in einer bestimmten `DefaultSwitch`-Einstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="bc658-126">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>

|<span data-ttu-id="bc658-127">DefaultSwitch-Wert</span><span class="sxs-lookup"><span data-stu-id="bc658-127">DefaultSwitch Value</span></span>|<span data-ttu-id="bc658-128">Für die Ausgabe benötigter Schweregrad der Nachrichten</span><span class="sxs-lookup"><span data-stu-id="bc658-128">Message severity required for output</span></span>|
|---|---|
|`Critical`|`Critical`|
|`Error`|<span data-ttu-id="bc658-129">`Critical` oder `Error`</span><span class="sxs-lookup"><span data-stu-id="bc658-129">`Critical` or `Error`</span></span>|
|`Warning`|<span data-ttu-id="bc658-130">`Critical`, `Error`oder `Warning`</span><span class="sxs-lookup"><span data-stu-id="bc658-130">`Critical`, `Error`, or `Warning`</span></span>|
|`Information`|<span data-ttu-id="bc658-131">`Critical`, `Error`, `Warning`oder `Information`</span><span class="sxs-lookup"><span data-stu-id="bc658-131">`Critical`, `Error`, `Warning`, or `Information`</span></span>|
|`Verbose`|<span data-ttu-id="bc658-132">`Critical`, `Error`, `Warning`, `Information` oder `Verbose`</span><span class="sxs-lookup"><span data-stu-id="bc658-132">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|
|`ActivityTracing`|<span data-ttu-id="bc658-133">`Start`, `Stop`, `Suspend`, `Resume` oder `Transfer`</span><span class="sxs-lookup"><span data-stu-id="bc658-133">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|
|`All`|<span data-ttu-id="bc658-134">Alle Nachrichten sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="bc658-134">All messages are allowed.</span></span>|
|`Off`|<span data-ttu-id="bc658-135">Alle Nachrichten sind blockiert.</span><span class="sxs-lookup"><span data-stu-id="bc658-135">All messages are blocked.</span></span>|

> [!NOTE]
> <span data-ttu-id="bc658-136">Die Methoden `WriteEntry` und `WriteException` verfügen beide über eine Überladung, die keinen Schweregrad angibt.</span><span class="sxs-lookup"><span data-stu-id="bc658-136">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="bc658-137">Der implizite Schweregrad für die Überladung `WriteEntry` ist „Information“, und der implizite Schweregrad für die Überladung `WriteException` ist „Error“.</span><span class="sxs-lookup"><span data-stu-id="bc658-137">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>

<span data-ttu-id="bc658-138">In dieser Tabelle wird die im vorherigen Beispiel gezeigte Protokollausgabe erklärt: Mit der Standardeinstellung `DefaultSwitch` von „Information“ erzeugt nur der zweite Aufruf der Methode `WriteEntry` und der Aufruf der Methode `WriteException` eine Protokollausgabe.</span><span class="sxs-lookup"><span data-stu-id="bc658-138">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>

#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="bc658-139">So protokollieren Sie nur Aktivitätsablauf-Verfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="bc658-139">To log only activity tracing events</span></span>

1. <span data-ttu-id="bc658-140">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-140">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>

     <span data-ttu-id="bc658-141">\- oder -</span><span class="sxs-lookup"><span data-stu-id="bc658-141">-or-</span></span>

     <span data-ttu-id="bc658-142">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="bc658-142">If there is no app.config file:</span></span>

    1. <span data-ttu-id="bc658-143">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc658-143">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="bc658-144">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-144">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="bc658-145">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc658-145">Click **Add**.</span></span>

2. <span data-ttu-id="bc658-146">Suchen Sie den Abschnitt `<switches>`, der sich im Abschnitt `<system.diagnostics>` im Abschnitt `<configuration>` der obersten Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="bc658-146">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="bc658-147">Suchen Sie das Element, das `DefaultSwitch` zur Auflistung von Schaltern hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="bc658-147">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="bc658-148">Es sollte in etwa wie dieses Element aussehen:</span><span class="sxs-lookup"><span data-stu-id="bc658-148">It should look similar to this element:</span></span>

     `<add name="DefaultSwitch" value="Information" />`

4. <span data-ttu-id="bc658-149">Ändern Sie den Wert des `value`-Attributs zu „ActivityTracing“.</span><span class="sxs-lookup"><span data-stu-id="bc658-149">Change the value of the `value` attribute to "ActivityTracing".</span></span>

5. <span data-ttu-id="bc658-150">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="bc658-150">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="ActivityTracing" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

6. <span data-ttu-id="bc658-151">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-151">Run the application in the debugger.</span></span>

7. <span data-ttu-id="bc658-152">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="bc658-152">Press **Button1**.</span></span>

     <span data-ttu-id="bc658-153">Die Anwendung schreibt die folgenden Informationen in die Debugausgabe und die Protokolldatei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="bc658-153">The application writes the following information to the application's debug output and log file:</span></span>

     `DefaultSource Start: 4 : Entering Button1_Click`

     `DefaultSource Stop: 5 : Leaving Button1_Click`

8. <span data-ttu-id="bc658-154">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bc658-154">Close the application.</span></span>

9. <span data-ttu-id="bc658-155">Ändern Sie den Wert des `value`-Attributs zurück zu „Information“.</span><span class="sxs-lookup"><span data-stu-id="bc658-155">Change the value of the `value` attribute back to "Information".</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc658-156">Die Einstellung des Schalters `DefaultSwitch` steuert nur `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="bc658-156">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="bc658-157">Das Verhalten der .NET-Klassen <xref:System.Diagnostics.Trace?displayProperty=nameWithType> und <xref:System.Diagnostics.Debug?displayProperty=nameWithType> wird dadurch nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="bc658-157">It does not change how the .NET <xref:System.Diagnostics.Trace?displayProperty=nameWithType> and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes behave.</span></span>

## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="bc658-158">Einzelne Filterung für alle „My.Application.Log“-Listener</span><span class="sxs-lookup"><span data-stu-id="bc658-158">Individual Filtering For My.Application.Log Listeners</span></span>

<span data-ttu-id="bc658-159">Im vorherige Beispiel wurde gezeigt, wie Sie die Filterung für alle `My.Application.Log`-Ausgaben ändern können.</span><span class="sxs-lookup"><span data-stu-id="bc658-159">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="bc658-160">In diesem Beispiel wird veranschaulicht, wie Sie einen einzelnen Protokolllistener filtern.</span><span class="sxs-lookup"><span data-stu-id="bc658-160">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="bc658-161">Standardmäßig verwendet eine Anwendung zwei Listener, die in die Debugausgabe und die Protokolldatei der Anwendung schreiben.</span><span class="sxs-lookup"><span data-stu-id="bc658-161">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>

<span data-ttu-id="bc658-162">Die Konfigurationsdatei steuert das Verhalten der Protokolllistener durch Zulassen eines Filters für jeden Listener, vergleichbar mit einem Schalter für `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="bc658-162">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="bc658-163">Ein Protokolllistener gibt nur eine Meldung aus, wenn der Schweregrad der Meldung durch den `DefaultSwitch` des Protokolls und den Filter des Protokolllisteners zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="bc658-163">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>

<span data-ttu-id="bc658-164">In diesem Beispiel wird veranschaulicht, wie Sie eine Filterung für einen neuen Debuglistener konfigurieren und zum `Log`-Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc658-164">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="bc658-165">Der standardmäßige Debuglistener sollte aus dem `Log`-Objekt entfernt werden. Hierdurch wird deutlich gemacht, dass die Debugmeldungen direkt vom neuen Debuglistener stammen.</span><span class="sxs-lookup"><span data-stu-id="bc658-165">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>

#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="bc658-166">So protokollieren Sie nur Aktivitätsablaufverfolgungs-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bc658-166">To log only activity-tracing events</span></span>

1. <span data-ttu-id="bc658-167">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-167">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="bc658-168">\- oder -</span><span class="sxs-lookup"><span data-stu-id="bc658-168">\-or-</span></span>

     <span data-ttu-id="bc658-169">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="bc658-169">If there is no app.config file:</span></span>

    1. <span data-ttu-id="bc658-170">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc658-170">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="bc658-171">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-171">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="bc658-172">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bc658-172">Click **Add**.</span></span>

2. <span data-ttu-id="bc658-173">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“.</span><span class="sxs-lookup"><span data-stu-id="bc658-173">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="bc658-174">Wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-174">Choose **Open**.</span></span>

3. <span data-ttu-id="bc658-175">Suchen Sie den Abschnitt `<listeners>` im Abschnitt `<source>` mit dem `name`-Attribut „DefaultSource“, das sich im Abschnitt `<sources>` befindet.</span><span class="sxs-lookup"><span data-stu-id="bc658-175">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="bc658-176">Der Abschnitt `<sources>` befindet sich im Abschnitt `<system.diagnostics>` im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="bc658-176">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

4. <span data-ttu-id="bc658-177">Fügen Sie dem Abschnitt `<listeners>` dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="bc658-177">Add this element to the `<listeners>` section:</span></span>

    ```xml
    <!-- Remove the default debug listener. -->
    <remove name="Default"/>
    <!-- Add a filterable debug listener. -->
    <add name="NewDefault"/>
    ```

5. <span data-ttu-id="bc658-178">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="bc658-178">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="bc658-179">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="bc658-179">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="NewDefault"
         type="System.Diagnostics.DefaultTraceListener,
               System, Version=2.0.0.0, Culture=neutral,
               PublicKeyToken=b77a5c561934e089,
               processorArchitecture=MSIL">
        <filter type="System.Diagnostics.EventTypeFilter"
                initializeData="Error" />
    </add>
    ```

     <span data-ttu-id="bc658-180">Der <xref:System.Diagnostics.EventTypeFilter>-Filter akzeptiert einen der <xref:System.Diagnostics.SourceLevels>-Enumerationswerte als sein `initializeData`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc658-180">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>

7. <span data-ttu-id="bc658-181">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="bc658-181">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Remove the default debug listener. -->
              <remove name="Default"/>
              <!-- Add a filterable debug listener. -->
              <add name="NewDefault"/>
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="Information" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,
                     processorArchitecture=MSIL"
               initializeData="FileLogWriter"/>
          <add name="NewDefault"
               type="System.Diagnostics.DefaultTraceListener,
                     System, Version=2.0.0.0, Culture=neutral,
                     PublicKeyToken=b77a5c561934e089,
                     processorArchitecture=MSIL">
            <filter type="System.Diagnostics.EventTypeFilter"
                    initializeData="Error" />
          </add>
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

8. <span data-ttu-id="bc658-182">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="bc658-182">Run the application in the debugger.</span></span>

9. <span data-ttu-id="bc658-183">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="bc658-183">Press **Button1**.</span></span>

     <span data-ttu-id="bc658-184">Die Anwendung schreibt die folgenden Informationen in die Protokolldatei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="bc658-184">The application writes the following information to the application's log file:</span></span>

     `Default Information: 0 : In Button1_Click`

     `Default Error: 2 : Error in the application.`

     <span data-ttu-id="bc658-185">Die Anwendung schreibt aufgrund der restriktiveren Filterung weniger Informationen in die Debugausgabe.</span><span class="sxs-lookup"><span data-stu-id="bc658-185">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>

     `Default Error   2   Error`

10. <span data-ttu-id="bc658-186">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bc658-186">Close the application.</span></span>

<span data-ttu-id="bc658-187">Weitere Informationen zum Ändern der Protokolleinstellungen nach der Bereitstellung finden Sie unter [Working with Application Logs (Arbeiten mit Anwendungsprotokollen)](working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="bc658-187">For more information about changing log settings after deployment, see [Working with Application Logs](working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bc658-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc658-188">See also</span></span>

- [<span data-ttu-id="bc658-189">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="bc658-189">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="bc658-190">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="bc658-190">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="bc658-191">Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern</span><span class="sxs-lookup"><span data-stu-id="bc658-191">Walkthrough: Creating Custom Log Listeners</span></span>](walkthrough-creating-custom-log-listeners.md)
- [<span data-ttu-id="bc658-192">Gewusst wie: Schreiben von Protokollmeldungen</span><span class="sxs-lookup"><span data-stu-id="bc658-192">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="bc658-193">Ablaufverfolgungsschalter</span><span class="sxs-lookup"><span data-stu-id="bc658-193">Trace Switches</span></span>](../../../../framework/debug-trace-profile/trace-switches.md)
- [<span data-ttu-id="bc658-194">Protokollieren von Informationen aus der Anwendung</span><span class="sxs-lookup"><span data-stu-id="bc658-194">Logging Information from the Application</span></span>](index.md)
