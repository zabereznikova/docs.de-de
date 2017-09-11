---
title: "Filterung der Ausgaben von „My.Application.Log“ (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a19bd71f1346be292dcc7b143a0080ac1cf11ec0
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="eac79-102">Exemplarische Vorgehensweise: Filterung der Ausgaben von "My.Application.Log" (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eac79-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>
<span data-ttu-id="eac79-103">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie das standardmäßige Filtern von Protokollen für das `My.Application.Log`-Objekt ändern, um zu steuern, welche Informationen vom `Log`-Objekt an die Listener übergeben werden und welche Informationen von den Listenern geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="eac79-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="eac79-104">Sie können das Protokollierungsverhalten auch nach dem Erstellen der Anwendung ändern, da die Konfigurationsinformationen in der Konfigurationsdatei der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="eac79-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="eac79-105">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="eac79-105">Getting Started</span></span>  
 <span data-ttu-id="eac79-106">Alle Nachrichten, die von `My.Application.Log` geschrieben werden, haben einen zugeordneten Schweregrad, den die Filtermechanismen verwenden, um die Protokollausgabe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="eac79-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="eac79-107">Diese Beispielanwendung verwendet `My.Application.Log`-Methoden zum Schreiben mehrerer Protokollmeldungen mit unterschiedlichen Schweregraden.</span><span class="sxs-lookup"><span data-stu-id="eac79-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>  
  
#### <a name="to-build-the-sample-application"></a><span data-ttu-id="eac79-108">So installieren Sie die Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="eac79-108">To build the sample application</span></span>  
  
1.  <span data-ttu-id="eac79-109">Öffnen Sie ein neues [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="eac79-109">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="eac79-110">Fügen Sie eine Schaltfläche mit dem Namen „Button1“ zu „Form1“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="eac79-110">Add a button named Button1 to Form1.</span></span>  
  
3.  <span data-ttu-id="eac79-111">Fügen Sie im <xref:System.Windows.Forms.Control.Click>-Ereignishandler den folgenden Code für „Button1“ hinzu:</span><span class="sxs-lookup"><span data-stu-id="eac79-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>  
  
     <span data-ttu-id="eac79-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eac79-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span></span>  
  
4.  <span data-ttu-id="eac79-113">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-113">Run the application in the debugger.</span></span>  
  
5.  <span data-ttu-id="eac79-114">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="eac79-114">Press **Button1**.</span></span>  
  
     <span data-ttu-id="eac79-115">Die Anwendung schreibt die folgenden Informationen in die Debugausgabe und die Protokolldatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eac79-115">The application writes the following information to the application's debug output and log file.</span></span>  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  <span data-ttu-id="eac79-116">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eac79-116">Close the application.</span></span>  
  
     <span data-ttu-id="eac79-117">Informationen zum Anzeigen des Ausgabefensters der Anwendung finden Sie unter [Ausgabefenster](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="eac79-117">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="eac79-118">Informationen zum Speicherort der Protokolldatei der Anwendung finden Sie unter [Walkthrough: Determining Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="eac79-118">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eac79-119">Standardmäßig leert die Anwendung die Ausgabe der Protokolldatei, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="eac79-119">By default, the application flushes the log-file output when the application closes.</span></span>  
  
     <span data-ttu-id="eac79-120">Im oben stehenden Beispiel erzeugt der zweite Aufruf der <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>-Methode und der Aufruf der <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>-Methode eine Protokollausgabe, während dies bei dem ersten und letzten Aufruf der `WriteEntry`-Methode nicht passiert.</span><span class="sxs-lookup"><span data-stu-id="eac79-120">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="eac79-121">Dies liegt daran, dass die Schweregrade von `WriteEntry` und `WriteException` „Information“ und „Error“ sind, die beide durch das standardmäßige Filtern von Protokollen des Objekts `My.Application.Log` zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="eac79-121">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="eac79-122">Bei Ereignissen mit den Schweregraden „Start“ und „Stop“ wird das Erzeugen von Protokollausgaben verhindert.</span><span class="sxs-lookup"><span data-stu-id="eac79-122">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="eac79-123">Filterung für alle „My.Application.Log“-Listener</span><span class="sxs-lookup"><span data-stu-id="eac79-123">Filtering for All My.Application.Log Listeners</span></span>  
 <span data-ttu-id="eac79-124">Das `My.Application.Log`-Objekt verwendet einen <xref:System.Diagnostics.SourceSwitch> mit dem Namen `DefaultSwitch`, um zu steuern, welche Meldungen von den Methoden `WriteEntry` und `WriteException` an die Protokolllistener übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="eac79-124">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="eac79-125">Sie können `DefaultSwitch` in der Konfigurationsdatei der Anwendung konfigurieren, indem Sie dessen Wert auf einen der <xref:System.Diagnostics.SourceLevels>-Enumerationswerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="eac79-125">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="eac79-126">Standardmäßig ist der Wert „Information“.</span><span class="sxs-lookup"><span data-stu-id="eac79-126">By default, its value is "Information".</span></span>  
  
 <span data-ttu-id="eac79-127">In dieser Tabelle werden die Schweregrade gezeigt, die von Protokollen für das Schreiben einer Nachricht an die Listener in einer bestimmten `DefaultSwitch`-Einstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="eac79-127">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>  
  
|<span data-ttu-id="eac79-128">DefaultSwitch-Wert</span><span class="sxs-lookup"><span data-stu-id="eac79-128">DefaultSwitch Value</span></span>|<span data-ttu-id="eac79-129">Für die Ausgabe benötigter Schweregrad der Nachrichten</span><span class="sxs-lookup"><span data-stu-id="eac79-129">Message severity required for output</span></span>|  
|---|---| 
|`Critical`|`Critical`|  
|`Error`|<span data-ttu-id="eac79-130">`Critical` oder `Error`</span><span class="sxs-lookup"><span data-stu-id="eac79-130">`Critical` or `Error`</span></span>|  
|`Warning`|<span data-ttu-id="eac79-131">`Critical`, `Error` oder `Warning`</span><span class="sxs-lookup"><span data-stu-id="eac79-131">`Critical`, `Error`, or `Warning`</span></span>|  
|`Information`|<span data-ttu-id="eac79-132">`Critical`, `Error`, `Warning` oder `Information`</span><span class="sxs-lookup"><span data-stu-id="eac79-132">`Critical`, `Error`, `Warning`, or `Information`</span></span>|  
|`Verbose`|<span data-ttu-id="eac79-133">`Critical`, `Error`, `Warning`, `Information` oder `Verbose`</span><span class="sxs-lookup"><span data-stu-id="eac79-133">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|  
|`ActivityTracing`|<span data-ttu-id="eac79-134">`Start`, `Stop`, `Suspend`, `Resume` oder `Transfer`</span><span class="sxs-lookup"><span data-stu-id="eac79-134">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|  
|`All`|<span data-ttu-id="eac79-135">Alle Nachrichten sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="eac79-135">All messages are allowed.</span></span>|  
|`Off`|<span data-ttu-id="eac79-136">Alle Nachrichten sind blockiert.</span><span class="sxs-lookup"><span data-stu-id="eac79-136">All messages are blocked.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="eac79-137">Die Methoden `WriteEntry` und `WriteException` verfügen beide über eine Überladung, die keinen Schweregrad angibt.</span><span class="sxs-lookup"><span data-stu-id="eac79-137">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="eac79-138">Der implizite Schweregrad für die Überladung `WriteEntry` ist „Information“, und der implizite Schweregrad für die Überladung `WriteException` ist „Error“.</span><span class="sxs-lookup"><span data-stu-id="eac79-138">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>  
  
 <span data-ttu-id="eac79-139">In dieser Tabelle wird die im vorherigen Beispiel gezeigte Protokollausgabe erklärt: Mit der Standardeinstellung `DefaultSwitch` von „Information“ erzeugt nur der zweite Aufruf der Methode `WriteEntry` und der Aufruf der Methode `WriteException` eine Protokollausgabe.</span><span class="sxs-lookup"><span data-stu-id="eac79-139">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="eac79-140">So protokollieren Sie nur Aktivitätsablauf-Verfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="eac79-140">To log only activity tracing events</span></span>  
  
1.  <span data-ttu-id="eac79-141">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-141">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>  
  
     <span data-ttu-id="eac79-142">- oder - </span><span class="sxs-lookup"><span data-stu-id="eac79-142">-or-</span></span>  
  
     <span data-ttu-id="eac79-143">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="eac79-143">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="eac79-144">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eac79-144">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="eac79-145">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-145">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="eac79-146">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eac79-146">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="eac79-147">Suchen Sie den Abschnitt `<switches>`, der sich im Abschnitt `<system.diagnostics>` im Abschnitt `<configuration>` der obersten Ebene befindet.</span><span class="sxs-lookup"><span data-stu-id="eac79-147">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="eac79-148">Suchen Sie das Element, das `DefaultSwitch` zur Auflistung von Schaltern hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="eac79-148">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="eac79-149">Es sollte in etwa wie dieses Element aussehen:</span><span class="sxs-lookup"><span data-stu-id="eac79-149">It should look similar to this element:</span></span>  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  <span data-ttu-id="eac79-150">Ändern Sie den Wert des `value`-Attributs zu „ActivityTracing“.</span><span class="sxs-lookup"><span data-stu-id="eac79-150">Change the value of the `value` attribute to "ActivityTracing".</span></span>  
  
5.  <span data-ttu-id="eac79-151">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="eac79-151">The content of the app.config file should be similar to the following XML:</span></span>  
  
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
  
6.  <span data-ttu-id="eac79-152">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-152">Run the application in the debugger.</span></span>  
  
7.  <span data-ttu-id="eac79-153">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="eac79-153">Press **Button1**.</span></span>  
  
     <span data-ttu-id="eac79-154">Die Anwendung schreibt die folgenden Informationen in die Debugausgabe und die Protokolldatei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="eac79-154">The application writes the following information to the application's debug output and log file:</span></span>  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  <span data-ttu-id="eac79-155">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eac79-155">Close the application.</span></span>  
  
9. <span data-ttu-id="eac79-156">Ändern Sie den Wert des `value`-Attributs zurück zu „Information“.</span><span class="sxs-lookup"><span data-stu-id="eac79-156">Change the value of the `value` attribute back to "Information".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eac79-157">Die Einstellung des Schalters `DefaultSwitch` steuert nur `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="eac79-157">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="eac79-158">Das Verhalten der Klassen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], <xref:System.Diagnostics.Trace?displayProperty=fullName> und <xref:System.Diagnostics.Debug?displayProperty=fullName> wird dadurch nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="eac79-158">It does not change how the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> and <xref:System.Diagnostics.Debug?displayProperty=fullName> classes behave.</span></span>  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="eac79-159">Einzelne Filterung für alle „My.Application.Log“-Listener</span><span class="sxs-lookup"><span data-stu-id="eac79-159">Individual Filtering For My.Application.Log Listeners</span></span>  
 <span data-ttu-id="eac79-160">Im vorherige Beispiel wurde gezeigt, wie Sie die Filterung für alle `My.Application.Log`-Ausgaben ändern können.</span><span class="sxs-lookup"><span data-stu-id="eac79-160">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="eac79-161">In diesem Beispiel wird veranschaulicht, wie Sie einen einzelnen Protokolllistener filtern.</span><span class="sxs-lookup"><span data-stu-id="eac79-161">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="eac79-162">Standardmäßig verwendet eine Anwendung zwei Listener, die in die Debugausgabe und die Protokolldatei der Anwendung schreiben.</span><span class="sxs-lookup"><span data-stu-id="eac79-162">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>  
  
 <span data-ttu-id="eac79-163">Die Konfigurationsdatei steuert das Verhalten der Protokolllistener durch Zulassen eines Filters für jeden Listener, vergleichbar mit einem Schalter für `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="eac79-163">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="eac79-164">Ein Protokolllistener gibt nur eine Meldung aus, wenn der Schweregrad der Meldung durch den `DefaultSwitch` des Protokolls und den Filter des Protokolllisteners zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="eac79-164">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>  
  
 <span data-ttu-id="eac79-165">In diesem Beispiel wird veranschaulicht, wie Sie eine Filterung für einen neuen Debuglistener konfigurieren und zum `Log`-Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eac79-165">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="eac79-166">Der standardmäßige Debuglistener sollte aus dem `Log`-Objekt entfernt werden. Hierdurch wird deutlich gemacht, dass die Debugmeldungen direkt vom neuen Debuglistener stammen.</span><span class="sxs-lookup"><span data-stu-id="eac79-166">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="eac79-167">So protokollieren Sie nur Aktivitätsablaufverfolgungs-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="eac79-167">To log only activity-tracing events</span></span>  
  
1.  <span data-ttu-id="eac79-168">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-168">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="eac79-169">- oder - </span><span class="sxs-lookup"><span data-stu-id="eac79-169">-or-</span></span>  
  
     <span data-ttu-id="eac79-170">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="eac79-170">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="eac79-171">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eac79-171">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="eac79-172">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-172">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="eac79-173">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eac79-173">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="eac79-174">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“.</span><span class="sxs-lookup"><span data-stu-id="eac79-174">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="eac79-175">Wählen Sie **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-175">Choose **Open**.</span></span>  
  
3.  <span data-ttu-id="eac79-176">Suchen Sie den Abschnitt `<listeners>` im Abschnitt `<source>` mit dem `name`-Attribut „DefaultSource“, das sich im Abschnitt `<sources>` befindet.</span><span class="sxs-lookup"><span data-stu-id="eac79-176">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="eac79-177">Der Abschnitt `<sources>` befindet sich im Abschnitt `<system.diagnostics>` im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="eac79-177">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
4.  <span data-ttu-id="eac79-178">Fügen Sie dem Abschnitt `<listeners>` dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="eac79-178">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  <span data-ttu-id="eac79-179">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="eac79-179">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="eac79-180">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="eac79-180">Add this element to that `<sharedListeners>` section:</span></span>  
  
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
  
     <span data-ttu-id="eac79-181">Der <xref:System.Diagnostics.EventTypeFilter>-Filter akzeptiert einen der <xref:System.Diagnostics.SourceLevels>-Enumerationswerte als sein `initializeData`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="eac79-181">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>  
  
7.  <span data-ttu-id="eac79-182">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="eac79-182">The content of the app.config file should be similar to the following XML:</span></span>  
  
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
  
8.  <span data-ttu-id="eac79-183">Führen Sie die Anwendung im Debugger aus.</span><span class="sxs-lookup"><span data-stu-id="eac79-183">Run the application in the debugger.</span></span>  
  
9. <span data-ttu-id="eac79-184">Drücken Sie **Button1**.</span><span class="sxs-lookup"><span data-stu-id="eac79-184">Press **Button1**.</span></span>  
  
     <span data-ttu-id="eac79-185">Die Anwendung schreibt die folgenden Informationen in die Protokolldatei der Anwendung:</span><span class="sxs-lookup"><span data-stu-id="eac79-185">The application writes the following information to the application's log file:</span></span>  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     <span data-ttu-id="eac79-186">Die Anwendung schreibt aufgrund der restriktiveren Filterung weniger Informationen in die Debugausgabe.</span><span class="sxs-lookup"><span data-stu-id="eac79-186">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>  
  
     `Default Error   2   Error`  
  
10. <span data-ttu-id="eac79-187">Schließen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eac79-187">Close the application.</span></span>  
  
 <span data-ttu-id="eac79-188">Weitere Informationen zum Ändern der Protokolleinstellungen nach der Bereitstellung finden Sie unter [Working with Application Logs (Arbeiten mit Anwendungsprotokollen)](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="eac79-188">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac79-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eac79-189">See Also</span></span>  
 <span data-ttu-id="eac79-190">[Walkthrough: Determining Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="eac79-190">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="eac79-191">[Walkthrough: Changing Where My.Application.Log Writes Information (Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="eac79-191">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="eac79-192">[Walkthrough: Creating Custom Log Listeners (Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span><span class="sxs-lookup"><span data-stu-id="eac79-192">[Walkthrough: Creating Custom Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span></span>  
 <span data-ttu-id="eac79-193">[How to: Write Log Messages (Vorgehensweise: Schreiben von Protokollmeldungen)](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="eac79-193">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="eac79-194">[Trace Switches (Ablaufverfolgungsschalter)](../../../../framework/debug-trace-profile/trace-switches.md) </span><span class="sxs-lookup"><span data-stu-id="eac79-194">[Trace Switches](../../../../framework/debug-trace-profile/trace-switches.md) </span></span>  
 [<span data-ttu-id="eac79-195">Protokollieren von Informationen aus der Anwendung</span><span class="sxs-lookup"><span data-stu-id="eac79-195">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)

