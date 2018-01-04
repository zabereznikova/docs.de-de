---
title: Anzeigen von Nachrichtenprotokollen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3012fa13-f650-45fb-aaea-c5cca8c7d372
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09a26d3580b37ea92bf4ef5708a238396f22eb4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="viewing-message-logs"></a><span data-ttu-id="19c6a-102">Anzeigen von Nachrichtenprotokollen</span><span class="sxs-lookup"><span data-stu-id="19c6a-102">Viewing Message Logs</span></span>
<span data-ttu-id="19c6a-103">In diesem Thema wird beschrieben, wie Sie Nachrichtenprotokolle anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="19c6a-103">This topic describes how you can view message logs.</span></span>  
  
## <a name="viewing-message-logs-in-the-service-trace-viewer"></a><span data-ttu-id="19c6a-104">Anzeigen von Nachrichtenprotokollen im Service Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="19c6a-104">Viewing Message Logs in the Service Trace Viewer</span></span>  
 <span data-ttu-id="19c6a-105">Eine Nachricht wird während ihrer Verarbeitung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="19c6a-105">A message will be transformed as it is processed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="19c6a-106">Deshalb spiegelt eine Nachricht, die protokolliert wird, lediglich den Nachrichteninhalt am Protokollierungspunkt wider, nicht den Inhalt der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="19c6a-106">Therefore, a message being logged reflects only the message's content at the point it was logged, not the content on the wire.</span></span>  
  
 <span data-ttu-id="19c6a-107">Da die Ausgabe der Nachrichtenprotokollierung völlig unabhängig vom Übertragungsformat der Nachricht ist, gibt die Nachrichtenprotokollierung stets die decodierte Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="19c6a-107">Since the output of message logging has no relationship to the transfer format of the message, message logging always outputs the decoded message.</span></span> <span data-ttu-id="19c6a-108">Wenn Sie die Nachrichtenprotokollierung ordnungsgemäß konfiguriert haben, sollte jede protokollierte Nachricht als Klartext vorliegen.</span><span class="sxs-lookup"><span data-stu-id="19c6a-108">If you have configured message logging properly, any logged message should be in plain text.</span></span> <span data-ttu-id="19c6a-109">Beispielsweise wird das Format (Klartext) der protokollierten Nachrichten nicht durch die Verwendung eines binären Nachrichtenencoders beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="19c6a-109">For example, the format (plain text) of the logged messages is not affected by the usage of a binary message encoder.</span></span>  
  
 <span data-ttu-id="19c6a-110">Die Ausgabe von XmlWriterTraceListener ist eine Datei, die eine Sequenz von XML-Fragmenten enthält.</span><span class="sxs-lookup"><span data-stu-id="19c6a-110">The output of the XmlWriterTraceListener is a file that contains a sequence of XML fragments.</span></span> <span data-ttu-id="19c6a-111">Sie sollten beachten, dass die Datei keine gültige XML-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="19c6a-111">You should be aware that the file is not a valid XML file.</span></span> <span data-ttu-id="19c6a-112">Es wird empfohlen, Sie verwenden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen der Protokolldateien der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="19c6a-112">It is recommended that you use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) to view the message log files.</span></span> <span data-ttu-id="19c6a-113">Weitere Informationen zur Verwendung dieses Tools finden Sie unter [mithilfe von Service Trace Viewer für korrelierte Ablaufverfolgungen anzeigen und Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="19c6a-113">For more information on how to use this tool, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="19c6a-114">Im Service Trace Viewer werden Nachrichten aufgeführt, der **Nachricht** Registerkarte. Nachrichten, die einen Verarbeitungsfehler verursacht haben, werden je nach Schweregrad des Fehlers gelb (Warnstufe) oder rot (Fehlerstufe) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="19c6a-114">In the Service Trace Viewer, messages are listed in the **Message** tab. Messages that have caused, or are related to, a processing error are highlighted in yellow (warning level) or red (error level), depending on the severity of the error.</span></span> <span data-ttu-id="19c6a-115">Wenn Sie auf die Nachricht doppelklicken, wird die Nachrichtenablaufverfolgung im Kontext der Verarbeitungsanforderung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="19c6a-115">Double-clicking on the message brings up the message trace in the context of the processing request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c6a-116">Wenn eine Nachricht keinen Header aufweist, wird kein `<header/>`-Tag protokolliert.</span><span class="sxs-lookup"><span data-stu-id="19c6a-116">If a message has no header, no `<header/>` tag is logged.</span></span>  
  
## <a name="viewing-messages-logged-by-a-client-a-relay-and-a-service"></a><span data-ttu-id="19c6a-117">Anzeigen von Nachrichten, die von einem Client, einem Relay und einem Dienst protokolliert werden</span><span class="sxs-lookup"><span data-stu-id="19c6a-117">Viewing Messages Logged by a Client, a Relay, and a Service</span></span>  
 <span data-ttu-id="19c6a-118">Ihre Umgebung kann einen Client enthalten, der eine Nachricht an ein Relay sendet, das die Nachricht wiederum an den Dienst weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="19c6a-118">Your environment may contain a client, which sends a message to a relay, that subsequently forwards the message to the service.</span></span> <span data-ttu-id="19c6a-119">Wenn die nachrichtenprotokollierung auf allen drei Speicherorten aktiviert ist, und alle drei Nachrichtenprotokollen werden angezeigt, [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) gleichzeitig der Protokoll-Nachrichtenaustausch werden nicht ordnungsgemäß gerendert.</span><span class="sxs-lookup"><span data-stu-id="19c6a-119">When message logging is enabled on all three locations, and all three message logs are viewed in [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) simultaneously, the message log exchanges will be incorrectly rendered.</span></span> <span data-ttu-id="19c6a-120">Dies ist darauf zurückzuführen, dass `CorrelationId` und `ActivityId` im Nachrichtenheader nicht für jedes Absender-Empfängerpaar eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="19c6a-120">This is because the `CorrelationId` and `ActivityId` in the Message header are not unique for every send-receive pair.</span></span>  
  
 <span data-ttu-id="19c6a-121">Sie können eine der folgenden Methoden verwenden, um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="19c6a-121">You can use either one of the following methods to resolve this problem.</span></span>  
  
-   <span data-ttu-id="19c6a-122">Nur zwei der drei Nachrichtenprotokollen im Anzeigen der [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="19c6a-122">Only view two of the three message logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) at any time.</span></span>  
  
-   <span data-ttu-id="19c6a-123">Wenn Sie alle drei Protokolle in anzeigen, müssen die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zur gleichen Zeit können Sie den Relaydienst ändern, indem Sie beim Erstellen eines neuen <xref:System.ServiceModel.Channels.Message> Instanz.</span><span class="sxs-lookup"><span data-stu-id="19c6a-123">If you must view all three logs in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) at the same time, you can modify the relay service by creating a new <xref:System.ServiceModel.Channels.Message> instance.</span></span> <span data-ttu-id="19c6a-124">Bei dieser Instanz sollte es sich um eine Kopie des Textes der eingehenden Nachricht handeln und zusätzlich um alle Header mit Ausnahme des `ActivityId`-Headers und des `Action`-Headers.</span><span class="sxs-lookup"><span data-stu-id="19c6a-124">This instance should be a copy of the body of the incoming message, plus all the headers except for the `ActivityId` and `Action` headers.</span></span> <span data-ttu-id="19c6a-125">Der folgende Beispielcode veranschaulicht, wie Sie dabei vorgehen:</span><span class="sxs-lookup"><span data-stu-id="19c6a-125">The following example code demonstrates how to do this.</span></span>  
  
```  
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
  
## <a name="exceptional-cases-for-inaccurate-message-logging-content"></a><span data-ttu-id="19c6a-126">Ausnahmefälle für ungenauen Nachrichtenprotokollierungsinhalt</span><span class="sxs-lookup"><span data-stu-id="19c6a-126">Exceptional Cases for Inaccurate Message Logging Content</span></span>  
 <span data-ttu-id="19c6a-127">Unter den folgenden Bedingungen entsprechen die protokollierten Nachrichten eventuell nicht genau der Darstellung des in der Verbindung vorhandenen octet-Streams.</span><span class="sxs-lookup"><span data-stu-id="19c6a-127">Under the following conditions, messages being logged might not be the exact representation of the octet stream present on the wire.</span></span>  
  
-   <span data-ttu-id="19c6a-128">Für BasicHttpBinding werden Umschlagheader für die eingehenden Nachrichten im /adressing/non-Namespace protokolliert.</span><span class="sxs-lookup"><span data-stu-id="19c6a-128">For BasicHttpBinding, envelope headers are logged for the incoming messages in the /addressing/none namespace.</span></span>  
  
-   <span data-ttu-id="19c6a-129">Leerräume können unpassend gepaart werden.</span><span class="sxs-lookup"><span data-stu-id="19c6a-129">Whitespaces can be mismatched.</span></span>  
  
-   <span data-ttu-id="19c6a-130">Für eingehende Nachrichten können leere Elemente unterschiedlich dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="19c6a-130">For incoming messages, empty elements can be represented differently.</span></span> <span data-ttu-id="19c6a-131">Beispielsweise \<Tag >\</tag > anstelle von \<Tag / ></span><span class="sxs-lookup"><span data-stu-id="19c6a-131">For example, \<tag>\</tag> instead of  \<tag/></span></span>  
  
-   <span data-ttu-id="19c6a-132">Wenn die bekannte PII-Protokollierung deaktiviert ist, indem standardmäßig oder ausdrücklich enableLoggingKnownPii auf "true" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="19c6a-132">When known PII logging is disabled either by default or explicit setting enableLoggingKnownPii="true".</span></span>  
  
-   <span data-ttu-id="19c6a-133">Die Codierung wird für die Transformation in UTF-8 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19c6a-133">Encoding is enabled for transforming to UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c6a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19c6a-134">See Also</span></span>  
 [<span data-ttu-id="19c6a-135">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="19c6a-135">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="19c6a-136">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)</span><span class="sxs-lookup"><span data-stu-id="19c6a-136">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="19c6a-137">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="19c6a-137">Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/message-logging.md)
