---
title: "Ändern des Orts, in den „My.Application.Log“ Informationen schreibt (Visual Basic)"
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
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
caps.latest.revision: 20
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
ms.openlocfilehash: a02307c55283c359ae069170e8038cd1983d495b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="2193d-102">Exemplarische Vorgehensweise: Ändern des Orts, in den "My.Application.Log" Informationen schreibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2193d-102">Walkthrough: Changing Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="2193d-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="2193d-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="2193d-104">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die Standardeinstellungen außer Kraft setzen und das `Log` -Objekt dazu bringen können, in andere Protokolllistener zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2193d-104">This walkthrough shows how to override the default settings and cause the `Log` object to write to other log listeners.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2193d-105">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="2193d-105">Prerequisites</span></span>  
 <span data-ttu-id="2193d-106">Das `Log` -Objekt kann Informationen in verschiedene Protokolllistener schreiben.</span><span class="sxs-lookup"><span data-stu-id="2193d-106">The `Log` object can write information to several log listeners.</span></span> <span data-ttu-id="2193d-107">Sie müssen die aktuelle Konfiguration der Protokolllistener bestimmen, bevor Sie die Konfigurationen ändern können.</span><span class="sxs-lookup"><span data-stu-id="2193d-107">You need to determine the current configuration of the log listeners before changing the configurations.</span></span> <span data-ttu-id="2193d-108">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="2193d-108">For more information, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="2193d-109">Es kann nützlich sein, [Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) oder [Vorgehensweise: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md) durchzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2193d-109">You may want to review [How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) or [How to: Write to an Application Event Log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md).</span></span>  
  
### <a name="to-add-listeners"></a><span data-ttu-id="2193d-110">Hinzufügen von Listenern</span><span class="sxs-lookup"><span data-stu-id="2193d-110">To add listeners</span></span>  
  
1.  <span data-ttu-id="2193d-111">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="2193d-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="2193d-112">\- oder –</span><span class="sxs-lookup"><span data-stu-id="2193d-112">\- or -</span></span>  
  
     <span data-ttu-id="2193d-113">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="2193d-113">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="2193d-114">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2193d-114">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="2193d-115">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="2193d-115">From the **Add New Item** dialog box, select **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="2193d-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2193d-116">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="2193d-117">Suchen Sie den `<listeners>` -Abschnitt unter dem `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="2193d-117">Locate the `<listeners>` section, under the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section.</span></span> <span data-ttu-id="2193d-118">Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="2193d-118">The `<sources>` section is in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="2193d-119">Fügen Sie dem betreffenden `<listeners>` -Abschnitt diese Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="2193d-119">Add these elements to that `<listeners>` section.</span></span>  
  
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
  
4.  <span data-ttu-id="2193d-120">Entfernen Sie die Auskommentierungen der Protokolllistener, die `Log` -Meldungen empfangen sollen.</span><span class="sxs-lookup"><span data-stu-id="2193d-120">Uncomment the log listeners that you want to receive `Log` messages.</span></span>  
  
5.  <span data-ttu-id="2193d-121">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="2193d-121">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="2193d-122">Fügen Sie dem betreffenden `<sharedListeners>` -Abschnitt diese Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="2193d-122">Add these elements to that `<sharedListeners>` section.</span></span>  
  
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
  
7.  <span data-ttu-id="2193d-123">Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:</span><span class="sxs-lookup"><span data-stu-id="2193d-123">The content of the app.config file should be similar to the following XML:</span></span>  
  
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
  
### <a name="to-reconfigure-a-listener"></a><span data-ttu-id="2193d-124">Umkonfigurieren eines Listeners</span><span class="sxs-lookup"><span data-stu-id="2193d-124">To reconfigure a listener</span></span>  
  
1.  <span data-ttu-id="2193d-125">Suchen Sie im Abschnitt `<add>` das `<sharedListeners>` -Element des Listeners.</span><span class="sxs-lookup"><span data-stu-id="2193d-125">Locate the listener's `<add>` element from the `<sharedListeners>` section.</span></span>  
  
2.  <span data-ttu-id="2193d-126">Das `type` -Attribut enthält den Namen des Listenertyps.</span><span class="sxs-lookup"><span data-stu-id="2193d-126">The `type` attribute gives the name of the listener type.</span></span> <span data-ttu-id="2193d-127">Dieser Typ muss von der <xref:System.Diagnostics.TraceListener> -Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="2193d-127">This type must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="2193d-128">Verwenden Sie den starken Typnamen, um sicherzustellen, dass der richtige Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2193d-128">Use the strongly named type name to ensure that the right type is used.</span></span> <span data-ttu-id="2193d-129">Weitere Informationen finden Sie unten im Abschnitt "Verweise auf Typen mit starken Namen".</span><span class="sxs-lookup"><span data-stu-id="2193d-129">For more information, see the "To reference a strongly named type" section below.</span></span>  
  
     <span data-ttu-id="2193d-130">Dies sind einige der Typen, die Sie verwenden können:</span><span class="sxs-lookup"><span data-stu-id="2193d-130">Some types that you can use are:</span></span>  
  
    -   <span data-ttu-id="2193d-131">Ein <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> -Listener, der in eine Protokolldatei schreibt.</span><span class="sxs-lookup"><span data-stu-id="2193d-131">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> listener, which writes to a file log.</span></span>  
  
    -   <span data-ttu-id="2193d-132">Ein <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> -Listener, der Informationen in das Ereignisprotokoll des Computers schreibt, das im `initializeData` -Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2193d-132">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> listener, which writes information to the computer event log specified by the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="2193d-133">Die <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> - und <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> -Listener, die in die Datei schreiben, die im `initializeData` -Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2193d-133">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> listeners, which write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="2193d-134">Ein <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> -Listener, der in die Befehlszeilenkonsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="2193d-134">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> listener, which writes to the command-line console.</span></span>  
  
     <span data-ttu-id="2193d-135">Informationen dazu, wohin andere Typen von Protokolllistenern Informationen schreiben, finden Sie in der Dokumentation zum entsprechenden Typ.</span><span class="sxs-lookup"><span data-stu-id="2193d-135">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
3.  <span data-ttu-id="2193d-136">Wenn die Anwendung das Protokolllistenerobjekt erstellt, übergibt sie das `initializeData` -Attribut als Konstruktorparameter.</span><span class="sxs-lookup"><span data-stu-id="2193d-136">When the application creates the log-listener object, it passes the `initializeData` attribute as the constructor parameter.</span></span> <span data-ttu-id="2193d-137">Die Bedeutung des `initializeData` -Attributs hängt vom Ablaufverfolgungslistener ab.</span><span class="sxs-lookup"><span data-stu-id="2193d-137">The meaning of the `initializeData` attribute depends on the trace listener.</span></span>  
  
4.  <span data-ttu-id="2193d-138">Nach dem Erstellen des Protokolllisteners legt die Anwendung die Eigenschaften des Listeners fest.</span><span class="sxs-lookup"><span data-stu-id="2193d-138">After creating the log listener, the application sets the listener's properties.</span></span> <span data-ttu-id="2193d-139">Diese Eigenschaften werden durch die anderen Attribute im `<add>` -Element definiert.</span><span class="sxs-lookup"><span data-stu-id="2193d-139">These properties are defined by the other attributes in the `<add>` element.</span></span> <span data-ttu-id="2193d-140">Weitere Informationen zu den Eigenschaften für einen bestimmten Listener finden Sie in der Dokumentation für den betreffenden Listenertyp.</span><span class="sxs-lookup"><span data-stu-id="2193d-140">For more information on the properties for a particular listener, see the documentation for that listener's type.</span></span>  
  
### <a name="to-reference-a-strongly-named-type"></a><span data-ttu-id="2193d-141">Verweise auf Typen mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="2193d-141">To reference a strongly named type</span></span>  
  
1.  <span data-ttu-id="2193d-142">Um sicherzustellen, dass der richtige Typ für Ihren Protokolllistener verwendet wird, achten Sie darauf, den vollqualifizierten Typnamen und den starken Assemblynamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2193d-142">To ensure that the right type is used for your log listener, make sure to use the fully qualified type name and the strongly named assembly name.</span></span> <span data-ttu-id="2193d-143">Die Syntax für einen Typ mit starkem Namen ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2193d-143">The syntax of a strongly named type is as follows:</span></span>  
  
     <span data-ttu-id="2193d-144">\<*Typname*>, \<*Assemblyname*>, \<*Versionsnummer*>, \<*Kultur*>, \<*starker Name*></span><span class="sxs-lookup"><span data-stu-id="2193d-144">\<*type name*>, \<*assembly name*>, \<*version number*>, \<*culture*>, \<*strong name*></span></span>  
  
2.  <span data-ttu-id="2193d-145">Dieses Codebeispiel zeigt, wie Sie den starken Typnamen für einen vollqualifizierten Typ bestimmen – in diesem Fall "System.Diagnostics.FileLogTraceListener".</span><span class="sxs-lookup"><span data-stu-id="2193d-145">This code example shows how to determine the strongly named type name for a fully qualified type—"System.Diagnostics.FileLogTraceListener" in this case.</span></span>  
  
     <span data-ttu-id="2193d-146">[!code-vb[VbVbalrMyApplicationLog#15](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-changing-where-my-application-log-writes-information_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2193d-146">[!code-vb[VbVbalrMyApplicationLog#15](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-changing-where-my-application-log-writes-information_1.vb)]</span></span>  
  
     <span data-ttu-id="2193d-147">Dies ist die Ausgabe, und sie kann verwendet werden, um eindeutig auf einen Typ mit starkem Namen zu verweisen, wie in der Verfahrensweise "Hinzufügen von Listenern" oben.</span><span class="sxs-lookup"><span data-stu-id="2193d-147">This is the output, and it can be used to uniquely reference a strongly named type, as in the "To add listeners" procedure above.</span></span>  
  
     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`  
  
## <a name="see-also"></a><span data-ttu-id="2193d-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2193d-148">See Also</span></span>  
 <span data-ttu-id="2193d-149"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2193d-149"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="2193d-150"><xref:System.Diagnostics.TraceListener></span><span class="sxs-lookup"><span data-stu-id="2193d-150"><xref:System.Diagnostics.TraceListener></span></span>   
 <span data-ttu-id="2193d-151"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2193d-151"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName></span></span>   
 <span data-ttu-id="2193d-152"><xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2193d-152"><xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName></span></span>   
 <span data-ttu-id="2193d-153">[Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) </span><span class="sxs-lookup"><span data-stu-id="2193d-153">[How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) </span></span>  
 [<span data-ttu-id="2193d-154">Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="2193d-154">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)

