---
title: 'Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll'
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 298d6d85f8b21176b72db8e676617577eb03fada
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410035"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="ab984-102">Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab984-102">How to: Write to an Application Event Log (Visual Basic)</span></span>

<span data-ttu-id="ab984-103">Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu erfassen, die in Ihrer Anwendung auftreten.</span><span class="sxs-lookup"><span data-stu-id="ab984-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="ab984-104">Dieses Beispiel veranschaulicht, wie ein Ereignisprotokolllistener konfiguriert wird, damit `My.Application.Log` Ablaufverfolgungsinformationen in das Anwendungsereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="ab984-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>

<span data-ttu-id="ab984-105">In das Sicherheitsprotokoll kann nicht geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ab984-105">You cannot write to the Security log.</span></span> <span data-ttu-id="ab984-106">Um in das Systemprotokoll zu schreiben, müssen Sie Mitglied des Kontos "LocalSystem" oder "Administrator" sein.</span><span class="sxs-lookup"><span data-stu-id="ab984-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>

<span data-ttu-id="ab984-107">Zum Anzeigen von Ereignisprotokollen können Sie den **Server-Explorer** oder die **Windows-Ereignisanzeige**verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab984-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="ab984-108">Weitere Informationen finden Sie unter [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="ab984-108">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

## <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="ab984-109">Hinzufügen und Konfigurieren des Ereignisprotokolllisteners</span><span class="sxs-lookup"><span data-stu-id="ab984-109">To add and configure the event log listener</span></span>

1. <span data-ttu-id="ab984-110">Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="ab984-110">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

    <span data-ttu-id="ab984-111">\- oder -</span><span class="sxs-lookup"><span data-stu-id="ab984-111">\- or -</span></span>

    <span data-ttu-id="ab984-112">Wenn keine app.config-Datei vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="ab984-112">If there is no app.config file,</span></span>

    1. <span data-ttu-id="ab984-113">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ab984-113">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="ab984-114">Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.</span><span class="sxs-lookup"><span data-stu-id="ab984-114">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="ab984-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ab984-115">Click **Add**.</span></span>

2. <span data-ttu-id="ab984-116">Suchen Sie den Abschnitt `<listeners>` in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ab984-116">Locate the `<listeners>` section in the application configuration file.</span></span>

    <span data-ttu-id="ab984-117">Sie finden den Abschnitt `<listeners>` im `<source>` -Abschnitt mit dem Namensattribut "DefaultSource", der in den `<system.diagnostics>` -Abschnitt verschachtelt ist, der seinerseits in den `<configuration>` -Abschnitt der obersten Ebene verschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="ab984-117">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="ab984-118">Fügen Sie dem `<listeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="ab984-118">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="EventLog"/>
    ```

4. <span data-ttu-id="ab984-119">Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="ab984-119">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="ab984-120">Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="ab984-120">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    <span data-ttu-id="ab984-121">Ersetzen Sie `APPLICATION_NAME` durch den Namen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ab984-121">Replace `APPLICATION_NAME` with the name of your application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab984-122">Normalerweise schreiben Anwendungen nur Fehler in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ab984-122">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="ab984-123">Informationen zum Filtern von Protokollausgaben finden Sie unter [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="ab984-123">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

## <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="ab984-124">Schreiben von Ereignisinformationen in das Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="ab984-124">To write event information to the event log</span></span>

<span data-ttu-id="ab984-125">Verwenden Sie die `My.Application.Log.WriteEntry` - oder die `My.Application.Log.WriteException` -Methode, um Informationen in das Ereignisprotokoll zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ab984-125">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="ab984-126">Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben von Protokollmeldungen](how-to-write-log-messages.md) und [Vorgehensweise: Protokollieren von Ausnahmen](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="ab984-126">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="ab984-127">Nachdem Sie den Ereignisprotokolllistener für eine Assembly konfiguriert haben, empfängt er alle Meldungen, die `My.Application.Log` für die betreffende Assembly schreibt.</span><span class="sxs-lookup"><span data-stu-id="ab984-127">After you configure the event log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab984-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab984-128">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="ab984-129">Arbeiten mit Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="ab984-129">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="ab984-130">Gewusst wie: Protokollieren von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ab984-130">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="ab984-131">Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt</span><span class="sxs-lookup"><span data-stu-id="ab984-131">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
