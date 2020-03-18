---
title: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: bdee0a91360580b156c1734ef4c82139b18ce2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74336736"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="85a32-102">Exemplarische Vorgehensweise: Ändern des Orts, in den "My.Application.Log" Informationen schreibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85a32-102">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="85a32-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="85a32-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="85a32-104">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die Standardeinstellungen außer Kraft setzen und das `Log` -Objekt dazu bringen können, in andere Protokolllistener zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="85a32-104">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85a32-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="85a32-105">Prerequisites</span></span>

<span data-ttu-id="85a32-106">Das `Log` -Objekt kann Informationen in mehrere Protokolllistener schreiben.</span><span class="sxs-lookup"><span data-stu-id="85a32-106">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="85a32-107">Sie müssen die aktuelle Konfiguration der Protokolllistener bestimmen, bevor Sie die Konfigurationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="85a32-107">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="85a32-108">Weitere Informationen finden Sie unter [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="85a32-108">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>

<span data-ttu-id="85a32-109">Es kann nützlich sein, [Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) oder [Vorgehensweise: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md) durchzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="85a32-109">You may want to review [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span></span>

### <a name="to-add-listeners"></a><span data-ttu-id="85a32-110">Hinzufügen von Listenern</span><span class="sxs-lookup"><span data-stu-id="85a32-110">To add listeners</span></span>

1. <span data-ttu-id="85a32-111">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="85a32-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="85a32-112">\- oder -</span><span class="sxs-lookup"><span data-stu-id="85a32-112">\- or -</span></span>

     <span data-ttu-id="85a32-113">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="85a32-113">If there is no app.config file:</span></span>

    1. <span data-ttu-id="85a32-114">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="85a32-114">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="85a32-115">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="85a32-115">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>

    3. <span data-ttu-id="85a32-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="85a32-116">Click **Add**.</span></span>

2. <span data-ttu-id="85a32-117">Suchen Sie den `<listeners>` -Abschnitt unter dem `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="85a32-117">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="85a32-118">Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="85a32-118">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="85a32-119">Fügen Sie dem betreffenden `<listeners>` -Abschnitt diese Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="85a32-119">Add these elements to that `<listeners>` section.</span></span>

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. <span data-ttu-id="85a32-120">Entfernen Sie die Auskommentierungen der Protokolllistener, die `Log` -Meldungen empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="85a32-120">Uncomment the log listeners that you want to receive `Log` messages.</span></span>

5. <span data-ttu-id="85a32-121">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="85a32-121">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

6. <span data-ttu-id="85a32-122">Fügen Sie dem betreffenden `<sharedListeners>` -Abschnitt diese Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="85a32-122">Add these elements to that `<sharedListeners>` section.</span></span>

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. <span data-ttu-id="85a32-123">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="85a32-123">The content of the app.config file should be similar to the following XML:</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
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
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="85a32-124">Umkonfigurieren eines Listeners</span><span class="sxs-lookup"><span data-stu-id="85a32-124">To reconfigure a listener</span></span>

1. <span data-ttu-id="85a32-125">Suchen Sie im Abschnitt `<add>` das `<sharedListeners>` -Element des Listeners.</span><span class="sxs-lookup"><span data-stu-id="85a32-125">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>

2. <span data-ttu-id="85a32-126">Das `type` -Attribut enthält den Namen des Listenertyps.</span><span class="sxs-lookup"><span data-stu-id="85a32-126">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="85a32-127">Dieser Typ muss von der <xref:System.Diagnostics.TraceListener> -Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="85a32-127">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="85a32-128">Verwenden Sie den starken Typnamen, um sicherzustellen, dass der richtige Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85a32-128">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="85a32-129">Weitere Informationen finden Sie unten im Abschnitt "Verweise auf Typen mit starken Namen".</span><span class="sxs-lookup"><span data-stu-id="85a32-129">For more information, see the "To reference a strongly named type" section below.</span></span>

     <span data-ttu-id="85a32-130">Dies sind einige der Typen, die Sie verwenden können:</span><span class="sxs-lookup"><span data-stu-id="85a32-130">Some types that you can use are:</span></span>

    - <span data-ttu-id="85a32-131">Ein <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> -Listener, der in eine Protokolldatei schreibt.</span><span class="sxs-lookup"><span data-stu-id="85a32-131">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener, which writes to a file log.</span></span>

    - <span data-ttu-id="85a32-132">Ein <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> -Listener, der Informationen in das Ereignisprotokoll des Computers schreibt, das im `initializeData` -Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="85a32-132">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>

    - <span data-ttu-id="85a32-133">Die <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> - und <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> -Listener, die in die Datei schreiben, die im `initializeData` -Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="85a32-133">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners, which write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="85a32-134">Ein <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> -Listener, der in die Befehlszeilenkonsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="85a32-134">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener, which writes to the command-line console.</span></span>

     <span data-ttu-id="85a32-135">Informationen dazu, wohin andere Typen von Protokolllistenern Informationen schreiben, finden Sie in der Dokumentation zum entsprechenden Typ.</span><span class="sxs-lookup"><span data-stu-id="85a32-135">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

3. <span data-ttu-id="85a32-136">Wenn die Anwendung das Protokolllistenerobjekt erstellt, übergibt sie das `initializeData` -Attribut als Konstruktorparameter.</span><span class="sxs-lookup"><span data-stu-id="85a32-136">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="85a32-137">Die Bedeutung des `initializeData` -Attributs hängt vom Ablaufverfolgungslistener ab.</span><span class="sxs-lookup"><span data-stu-id="85a32-137">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>

4. <span data-ttu-id="85a32-138">Nach dem Erstellen des Protokolllisteners legt die Anwendung die Eigenschaften des Listeners fest.</span><span class="sxs-lookup"><span data-stu-id="85a32-138">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="85a32-139">Diese Eigenschaften werden durch die anderen Attribute im `<add>` -Element definiert.</span><span class="sxs-lookup"><span data-stu-id="85a32-139">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="85a32-140">Weitere Informationen zu den Eigenschaften für einen bestimmten Listener finden Sie in der Dokumentation für den betreffenden Listenertyp.</span><span class="sxs-lookup"><span data-stu-id="85a32-140">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>

### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="85a32-141">Verweise auf Typen mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="85a32-141">To reference a strongly named type</span></span>

1. <span data-ttu-id="85a32-142">Um sicherzustellen, dass der richtige Typ für Ihren Protokolllistener verwendet wird, achten Sie darauf, den vollqualifizierten Typnamen und den starken Assemblynamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="85a32-142">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="85a32-143">Die Syntax für einen Typ mit starkem Namen ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="85a32-143">The syntax of a strongly named type is as follows:</span></span>

     <span data-ttu-id="85a32-144">\<*Typname*>, \<*Assemblyname*>, \<*Versionsnummer*>, \<*Kultur*>, \<*starker Name*></span><span class="sxs-lookup"><span data-stu-id="85a32-144">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>

2. <span data-ttu-id="85a32-145">Dieses Codebeispiel zeigt, wie Sie den starken Typnamen für einen vollqualifizierten Typ bestimmen – in diesem Fall "System.Diagnostics.FileLogTraceListener".</span><span class="sxs-lookup"><span data-stu-id="85a32-145">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     <span data-ttu-id="85a32-146">Dies ist die Ausgabe, und sie kann verwendet werden, um eindeutig auf einen Typ mit starkem Namen zu verweisen, wie in der Verfahrensweise "Hinzufügen von Listenern" oben.</span><span class="sxs-lookup"><span data-stu-id="85a32-146">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a><span data-ttu-id="85a32-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85a32-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [<span data-ttu-id="85a32-148">Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="85a32-148">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [<span data-ttu-id="85a32-149">Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="85a32-149">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)
