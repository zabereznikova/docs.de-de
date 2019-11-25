---
title: Bestimmen, wohin „My.Application.Log“ Informationen schreibt
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, output location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: f3fd0ed0388276f1400bf77d0abfb488634a45a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353603"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="11fe1-102">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11fe1-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>

<span data-ttu-id="11fe1-103">Das `My.Application.Log` -Objekt kann Informationen in verschiedene Protokolllistener schreiben.</span><span class="sxs-lookup"><span data-stu-id="11fe1-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="11fe1-104">Die Protokolllistener werden durch die Konfigurationsdatei des Computers konfiguriert und können durch die Konfigurationsdatei einer Anwendung außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="11fe1-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="11fe1-105">Dieses Thema beschreibt die Standardeinstellungen und erläutert, wie Sie die Einstellungen für Ihre Anwendung ermitteln.</span><span class="sxs-lookup"><span data-stu-id="11fe1-105">This topic describes the default settings and how to determine the settings for your application.</span></span>

<span data-ttu-id="11fe1-106">Weitere Informationen zu den Standardausgabeorten finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="11fe1-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>

### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="11fe1-107">Bestimmen der Listener für "My.Application.Log"</span><span class="sxs-lookup"><span data-stu-id="11fe1-107">To determine the listeners for My.Application.Log</span></span>

1. <span data-ttu-id="11fe1-108">Suchen Sie die Konfigurationsdatei der Assembly.</span><span class="sxs-lookup"><span data-stu-id="11fe1-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="11fe1-109">Wenn Sie die Assembly entwickeln, können Sie in Visual Studio im **Projektmappen-Explorer** auf die „app.config“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="11fe1-109">If you are developing the assembly, you can access the app.config in Visual Studio from the **Solution Explorer**.</span></span> <span data-ttu-id="11fe1-110">Andernfalls ist der Name der Konfigurationsdatei der Name der Assembly mit angefügtem ".config" und befindet sich im gleichen Verzeichnis wie die Assembly.</span><span class="sxs-lookup"><span data-stu-id="11fe1-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11fe1-111">Nicht jede Assembly verfügt über eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="11fe1-111">Not every assembly has a configuration file.</span></span>

    <span data-ttu-id="11fe1-112">Bei der Konfigurationsdatei handelt es sich um eine XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="11fe1-112">The configuration file is an XML file.</span></span>

2. <span data-ttu-id="11fe1-113">Suchen Sie den `<listeners>` -Abschnitt, der sich im `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` befindet.</span><span class="sxs-lookup"><span data-stu-id="11fe1-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="11fe1-114">Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="11fe1-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

    <span data-ttu-id="11fe1-115">Wenn diese Abschnitte nicht vorhanden sind, werden die `My.Application.Log` -Protokolllistener möglicherweise durch die Konfigurationsdatei des Computers konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="11fe1-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="11fe1-116">In den folgenden Schritten ist beschrieben, wie Sie bestimmen, was in der Computerkonfigurationsdatei definiert ist:</span><span class="sxs-lookup"><span data-stu-id="11fe1-116">The following steps describe how to determine what the computer configuration file defines:</span></span>

    1. <span data-ttu-id="11fe1-117">Suchen Sie die Datei "machine.config" des Computers.</span><span class="sxs-lookup"><span data-stu-id="11fe1-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="11fe1-118">In der Regel befindet sie sich im Verzeichnis *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG*, wobei `SystemRoot` das Betriebssystemverzeichnis und `frameworkVersion` die Version von .NET Framework ist.</span><span class="sxs-lookup"><span data-stu-id="11fe1-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the .NET Framework.</span></span>

        <span data-ttu-id="11fe1-119">Die Einstellungen in "machine.config" können durch die Konfigurationsdatei einer Anwendung außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="11fe1-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>

        <span data-ttu-id="11fe1-120">Wenn die unten aufgelisteten optionalen Elemente nicht vorhanden sind, können Sie sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="11fe1-120">If the optional elements listed below do not exist, you can create them.</span></span>

    2. <span data-ttu-id="11fe1-121">Suchen Sie den Abschnitt `<listeners>` im Abschnitt `<source>` mit dem `name` -Attribut "DefaultSource" im `<sources>` -Abschnitt im `<system.diagnostics>` -Abschnitt im `<configuration>` -Abschnitt der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="11fe1-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

        <span data-ttu-id="11fe1-122">Wenn diese Abschnitte nicht vorhanden sind, verfügt `My.Application.Log` nur über die standardmäßigen Protokolllistener.</span><span class="sxs-lookup"><span data-stu-id="11fe1-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>

3. <span data-ttu-id="11fe1-123">Suchen Sie die <`add>`-Elemente im <`listeners>`-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="11fe1-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>

     <span data-ttu-id="11fe1-124">Diese Elemente fügen die benannten Protokolllistener zur `My.Application.Log` -Quelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="11fe1-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>

4. <span data-ttu-id="11fe1-125">Suchen Sie die `<add>` -Elemente mit den Namen der Protokolllistener im `<sharedListeners>` -Abschnitt im `<system.diagnostics>` -Abschnitt im `<configuration>` -Abschnitt der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="11fe1-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="11fe1-126">Bei vielen freigegebenen Listenern enthalten die Initialisierungdaten des Listeners eine Beschreibung, wohin der Listener die Daten leitet:</span><span class="sxs-lookup"><span data-stu-id="11fe1-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>

    - <span data-ttu-id="11fe1-127">Ein <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>-Listener schreibt in ein Dateiprotokoll, wie in der Einführung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11fe1-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener writes to a file log, as described in the introduction.</span></span>

    - <span data-ttu-id="11fe1-128">Ein <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>-Listener schreibt Informationen in das Ereignisprotokoll des Computers, das im `initializeData`-Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="11fe1-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="11fe1-129">Zum Anzeigen von Ereignisprotokollen können Sie den **Server-Explorer** oder die **Windows-Ereignisanzeige**verwenden.</span><span class="sxs-lookup"><span data-stu-id="11fe1-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="11fe1-130">Weitere Informationen finden Sie unter [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="11fe1-130">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

    - <span data-ttu-id="11fe1-131">Die <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>- und <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>-Listener schreiben in die Datei, die im `initializeData`-Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="11fe1-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners write to the file specified in the `initializeData` parameter.</span></span>

    - <span data-ttu-id="11fe1-132">Ein <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>-Listener schreibt in die Befehlszeilenkonsole.</span><span class="sxs-lookup"><span data-stu-id="11fe1-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener writes to the command-line console.</span></span>

    - <span data-ttu-id="11fe1-133">Informationen dazu, wohin andere Typen von Protokolllistenern Informationen schreiben, finden Sie in der Dokumentation zum entsprechenden Typ.</span><span class="sxs-lookup"><span data-stu-id="11fe1-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="11fe1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11fe1-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [<span data-ttu-id="11fe1-135">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="11fe1-135">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="11fe1-136">Vorgehensweise: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="11fe1-136">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="11fe1-137">Vorgehensweise: Schreiben von Protokollmeldungen</span><span class="sxs-lookup"><span data-stu-id="11fe1-137">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="11fe1-138">Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="11fe1-138">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="11fe1-139">ETW Events in the .NET Framework (ETW-Ereignisse in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="11fe1-139">ETW Events in the .NET Framework</span></span>](../../../../framework/performance/etw-events.md)
- [<span data-ttu-id="11fe1-140">Problembehandlung: Protokolllistener</span><span class="sxs-lookup"><span data-stu-id="11fe1-140">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
