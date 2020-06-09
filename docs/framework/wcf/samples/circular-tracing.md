---
title: Zirkuläre Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 1759db28cb024afc04d02c4b128f96d73aefdd87
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585440"
---
# <a name="circular-tracing"></a><span data-ttu-id="ea0dd-102">Zirkuläre Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ea0dd-102">Circular Tracing</span></span>

<span data-ttu-id="ea0dd-103">Dieses Beispiel veranschaulicht die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="ea0dd-104">Ein gängiges Szenario bei Produktionsdiensten besteht darin, dass Dienste vorhanden sind, die für längere Zeiträume verfügbar sind, und dass die Ablaufverfolgung auf einer unteren Ebene aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="ea0dd-105">Diese Dienste belegen viel Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="ea0dd-106">Bei der Problembehandlung sind zum Lösen eines Problems bei einem Dienst die aktuellsten Daten aus dem Ablaufverfolgungsprotokoll relevant.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="ea0dd-107">Dieses Beispiel zeigt die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners, bei der nur die neuesten Ablaufverfolgungen bis zu einer zu konfigurierenden Datenmenge auf der Festplatte aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="ea0dd-108">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md) Schritten und umfasst einen benutzerdefinierten Ablaufverfolgungslistener.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-108">This sample is based on the [Getting Started](getting-started-sample.md) and includes a custom tracing listener.</span></span>

> [!NOTE]
> <span data-ttu-id="ea0dd-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="ea0dd-110">In diesem Beispiel wird davon ausgegangen, dass Sie mit dem Beispiel für Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md) vertraut sind und die Dokumentation für das Beispiel Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md) gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-110">This sample assumes that you are familiar with the [Tracing and Message Logging](tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](tracing-and-message-logging.md) sample.</span></span>

## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="ea0dd-111">Zirkulärer Puffer-Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="ea0dd-111">Circular Buffer Trace Listener</span></span>

<span data-ttu-id="ea0dd-112">Die Implementierung des zirkulären Puffer-Ablaufverfolgungslisteners beruht auf dem Konzept, dass zwei Dateien vorhanden sind, von denen jede bis zur Hälfte der gewünschten Ablaufverfolgungsprotokolldaten speichern kann.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="ea0dd-113">Der Listener erstellt eine Datei und schreibt in diese, bis sie den Grenzwert der halben Datengröße erreicht. Dann wechselt der Listener zu einer zweiten Datei.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="ea0dd-114">Wenn der Listener den Grenzwert bei der zweiten Datei erreicht, überschreibt er die erste Datei mit neuen Ablaufverfolgungen.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>

<span data-ttu-id="ea0dd-115">Dieser Listener wird von abgeleitet `XmlWriteTraceListener` und ermöglicht das Anzeigen der Protokolle mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ea0dd-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="ea0dd-116">Beim Anzeigen der Protokolle können die beiden Protokolldateien leicht rekombiniert werden, indem man beide Protokolldateien gleichzeitig im Service Trace Viewer öffnet.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="ea0dd-117">Der Service Trace Viewer erledigt automatisch das Sortieren der Ablaufverfolgungen, so dass diese in der korrekten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>

## <a name="configuration"></a><span data-ttu-id="ea0dd-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ea0dd-118">Configuration</span></span>

<span data-ttu-id="ea0dd-119">Durch Hinzufügen des folgenden Codes für einen Listener und Quellelemente kann ein Dienst zum Verwenden des zirkulären Puffer-Ablaufverfolgungslisteners konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="ea0dd-120">Die maximale Dateigröße wird durch Angeben des `maxFileSizeKB`-Attributs in der Konfiguration des zirkulären Ablaufverfolgungslisteners festlegt.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="ea0dd-121">Dies wird im folgenden Code demonstriert.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-121">This is demonstrated in the following code.</span></span>

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">
      <listeners>
        <add name="CircularTraceListener" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />
  </sharedListeners>
  <trace autoflush="true" />
</system.diagnostics>
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ea0dd-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ea0dd-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ea0dd-123">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="ea0dd-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="ea0dd-125">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea0dd-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea0dd-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ea0dd-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ea0dd-128">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea0dd-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ea0dd-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ea0dd-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`

## <a name="see-also"></a><span data-ttu-id="ea0dd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea0dd-130">See also</span></span>

- <span data-ttu-id="ea0dd-131">[AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ea0dd-131">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
