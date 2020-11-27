---
title: Anzeigen von Nachrichtenprotokollen
ms.date: 03/30/2017
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
ms.openlocfilehash: c8313b14a45051b7828a1ab223a3da63b2e7a153
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291153"
---
# <a name="viewing-message-logs"></a><span data-ttu-id="bb291-102">Anzeigen von Nachrichtenprotokollen</span><span class="sxs-lookup"><span data-stu-id="bb291-102">Viewing Message Logs</span></span>

<span data-ttu-id="bb291-103">In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bb291-103">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="bb291-104">Anzeigen von Nachrichtenprotokollen im Service Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="bb291-104">Viewing Message Logs in the Service Trace Viewer</span></span>  

 <span data-ttu-id="bb291-105">Eine Nachricht wird transformiert, wenn Sie von WCF verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="bb291-105">A message will be transformed as it is processed by WCF.</span></span> <span data-ttu-id="bb291-106">Deshalb spiegelt eine Nachricht, die protokolliert wird, lediglich den Nachrichteninhalt am Protokollierungspunkt wider, nicht den Inhalt der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="bb291-106">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="bb291-107">Da die Ausgabe der Nachrichtenprotokollierung völlig unabhängig vom Übertragungsformat der Nachricht ist, gibt die Nachrichtenprotokollierung stets die decodierte Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="bb291-107">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="bb291-108">Wenn Sie die Nachrichtenprotokollierung ordnungsgemäß konfiguriert haben, sollte jede protokollierte Nachricht als Klartext vorliegen.</span><span class="sxs-lookup"><span data-stu-id="bb291-108">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="bb291-109">Beispielsweise wird das Format (Klartext) der protokollierten Nachrichten nicht durch die Verwendung eines binären Nachrichtenencoders beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="bb291-109">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="bb291-110">Die Ausgabe von XmlWriterTraceListener ist eine Datei, die eine Sequenz von XML-Fragmenten enthält.</span><span class="sxs-lookup"><span data-stu-id="bb291-110">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="bb291-111">Sie sollten beachten, dass die Datei keine gültige XML-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="bb291-111">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="bb291-112">Es wird empfohlen, das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zu verwenden, um die Nachrichtenprotokoll Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb291-112">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="bb291-113">Weitere Informationen zur Verwendung dieses Tools finden [Sie unter Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.</span><span class="sxs-lookup"><span data-stu-id="bb291-113">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="bb291-114">In Service Trace Viewer werden Meldungen auf der Registerkarte **Nachricht** aufgeführt. Nachrichten, die einen Verarbeitungsfehler verursacht haben oder sich darauf beziehen, werden je nach Schweregrad des Fehlers gelb (Warnstufe) oder rot (Fehlerstufe) hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="bb291-114">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="bb291-115">Wenn Sie auf die Nachricht doppelklicken, wird die Nachrichtenablaufverfolgung im Kontext der Verarbeitungsanforderung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bb291-115">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb291-116">Wenn eine Nachricht keinen Header aufweist, wird kein `<header/>`-Tag protokolliert.</span><span class="sxs-lookup"><span data-stu-id="bb291-116">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="bb291-117">Anzeigen von Nachrichten, die von einem Client, einem Relay und einem Dienst protokolliert werden</span><span class="sxs-lookup"><span data-stu-id="bb291-117">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  

 <span data-ttu-id="bb291-118">Ihre Umgebung kann einen Client enthalten, der eine Nachricht an ein Relay sendet, das die Nachricht wiederum an den Dienst weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="bb291-118">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="bb291-119">Wenn die Nachrichten Protokollierung an allen dreispeicher Orten aktiviert ist und alle drei Nachrichten Protokolle gleichzeitig im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden, wird der Austausch der Nachrichten Protokolle fälschlicherweise gerendert.</span><span class="sxs-lookup"><span data-stu-id="bb291-119">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="bb291-120">Dies ist darauf zurückzuführen, dass `CorrelationId` und `ActivityId` im Nachrichtenheader nicht für jedes Absender-Empfängerpaar eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="bb291-120">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="bb291-121">Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="bb291-121">You can use either one of the following methods to resolve this problem.</span></span>  
  
- <span data-ttu-id="bb291-122">Zeigen Sie nur zwei der drei Nachrichten Protokolle im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zu einem beliebigen Zeitpunkt an.</span><span class="sxs-lookup"><span data-stu-id="bb291-122">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
- <span data-ttu-id="bb291-123">Wenn Sie alle drei Protokolle gleichzeitig im [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) anzeigen müssen, können Sie den Relaydienst ändern, indem Sie eine neue- <xref:System.ServiceModel.Channels.Message> Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb291-123">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="bb291-124">Bei dieser Instanz sollte es sich um eine Kopie des Textes der eingehenden Nachricht handeln und zusätzlich um alle Header mit Ausnahme des `ActivityId`-Headers und des `Action`-Headers.</span><span class="sxs-lookup"><span data-stu-id="bb291-124">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="bb291-125">Der folgende Beispielcode veranschaulicht, wie Sie dabei vorgehen:</span><span class="sxs-lookup"><span data-stu-id="bb291-125">The following example code demonstrates how to do this.</span></span>  
  
```csharp
Message outgoingMessage = Message.CreateMessage(incomingMessage.Version, incomingMessage.Headers.Action, incomingMessage.GetReaderAtBodyContents());  
  
for (int i = 0; i < incomingMessage.Headers.Count; i++)  
{  
   if (incomingMessage.Headers[i].Name.Equals("ActivityId", StringComparison.InvariantCultureIgnoreCase) ||  
incomingMessage.Headers[i].Name.Equals("Action", StringComparison.InvariantCultureIgnoreCase))  
   {  
      continue;  
    }  
    outgoingMessage.Headers.CopyHeaderFrom(incomingMessage, i);  
}  
```  
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="bb291-126">Ausnahmefälle für ungenauen Nachrichtenprotokollierungsinhalt</span><span class="sxs-lookup"><span data-stu-id="bb291-126">Exceptional Cases for Inaccurate Message Logging Content</span></span>  

 <span data-ttu-id="bb291-127">Unter den folgenden Bedingungen entsprechen die protokollierten Nachrichten eventuell nicht genau der Darstellung des in der Verbindung vorhandenen octet-Streams.</span><span class="sxs-lookup"><span data-stu-id="bb291-127">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
- <span data-ttu-id="bb291-128">Für BasicHttpBinding werden Umschlagheader für die eingehenden Nachrichten im /adressing/non-Namespace protokolliert.</span><span class="sxs-lookup"><span data-stu-id="bb291-128">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
- <span data-ttu-id="bb291-129">Leerräume können nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bb291-129">White spaces can be mismatched.</span></span>  
  
- <span data-ttu-id="bb291-130">Für eingehende Nachrichten können leere Elemente unterschiedlich dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bb291-130">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="bb291-131">Beispielsweise \<tag> \</tag> anstelle von\<tag/></span><span class="sxs-lookup"><span data-stu-id="bb291-131">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
- <span data-ttu-id="bb291-132">Wenn die bekannte PII-Protokollierung deaktiviert ist, indem standardmäßig oder ausdrücklich enableLoggingKnownPii auf "true" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="bb291-132">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
- <span data-ttu-id="bb291-133">Die Codierung wird für die Transformation in UTF-8 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bb291-133">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb291-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb291-134">See also</span></span>

- [<span data-ttu-id="bb291-135">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="bb291-135">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [<span data-ttu-id="bb291-136">Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="bb291-136">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](./tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="bb291-137">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="bb291-137">Message Logging</span></span>](message-logging.md)
