---
title: Konfigurieren der Ablaufverfolgung des Nachrichtenflusses
ms.date: 03/30/2017
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
ms.openlocfilehash: 6c271c26eb4e57014b3aaebf306b283bd06c7119
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254882"
---
# <a name="configuring-message-flow-tracing"></a><span data-ttu-id="8e62b-102">Konfigurieren der Ablaufverfolgung des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="8e62b-102">Configuring Message Flow Tracing</span></span>

<span data-ttu-id="8e62b-103">Wenn Windows Communication Foundation (WCF)-Aktivitäts Ablauf Verfolgung aktiviert ist, werden End-to-End-Aktivitäts-IDs logischen Aktivitäten im gesamten WCF-Stapel zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8e62b-103">When Windows Communication Foundation (WCF) activity tracing is enabled, End-To-End Activity IDs are assigned to logical activities throughout the WCF stack.</span></span> <span data-ttu-id="8e62b-104">[!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] verfügt jetzt über eine leistungsstärkere Version dieser Funktion, die in Verbindung mit der Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW) verwendet werden kann und als Ablaufverfolgung des Nachrichtenflusses bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8e62b-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], there is now a higher performance version of this feature that works with Event Tracing for Windows (ETW) called message flow tracing.</span></span> <span data-ttu-id="8e62b-105">Bei Aktivierung dieser Funktion werden die End-to-End-Aktivität-IDs von eingehenden Nachrichten verwendet (bzw. bei Bedarf zugewiesen) und für alle Ablaufverfolgungsereignisse übernommen, die ausgegeben werden, nachdem die Nachricht vom Kanal decodiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8e62b-105">When enabled, End-To-End activity IDs are taken from (or assigned to if empty) incoming messages and are propagated to all tracing events that are emitted after the message has been decoded by the channel.</span></span> <span data-ttu-id="8e62b-106">Kunden können diese Funktion zum Wiederherstellen von Nachrichtenflüssen mit Ablaufverfolgungsprotokollen verschiedener Dienste nach der Decodierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e62b-106">Customers can use this feature to reconstruct message flows with trace logs from different services after decoding.</span></span>  
  
 <span data-ttu-id="8e62b-107">Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wurde, und dann wieder deaktiviert werden, nachdem das Problem behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="8e62b-107">Tracing can be enabled after a problem is detected with the application and then disabled once the problem is resolved.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="8e62b-108">Aktivieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8e62b-108">Enabling Tracing</span></span>  

 <span data-ttu-id="8e62b-109">Sie können die Ablaufverfolgung des Nachrichtenflusses aktivieren, in dem Sie das `messageFlowTracing`-Konfigurationselement für .NET Framework 4 auf `true` festlegen. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e62b-109">You can enable message flow tracing by setting the .NET Framework 4 `messageFlowTracing` configuration element to `true`, as shown in the following example.</span></span>  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
> <span data-ttu-id="8e62b-110">Da das `endToEndTracing`-Konfigurationselement in einer Web.config-Datei enthalten ist, kann es nicht wie unter ETW dynamisch konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="8e62b-110">Because the `endToEndTracing` configuration element resides in a Web.config file, it cannot be dynamically configured in the same way as ETW.</span></span> <span data-ttu-id="8e62b-111">Damit das `endToEndTracing`-Konfigurationselement wirksam wird, muss die Anwendung wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e62b-111">For the `endToEndTracing` configuration element to take effect, the application must be recycled.</span></span>  
  
 <span data-ttu-id="8e62b-112">Aktivitäten werden durch den Austausch eines Bezeichners, der sogenannten Aktivitäts-ID, korreliert.</span><span class="sxs-lookup"><span data-stu-id="8e62b-112">Activities are correlated by the interchange of an identifier called the activity ID.</span></span> <span data-ttu-id="8e62b-113">Dieser Bezeichner ist eine GUID und wird von der System.Diagnostics.CorrelationManager-Klasse generiert.</span><span class="sxs-lookup"><span data-stu-id="8e62b-113">This identifier is a GUID, and is generated by the System.Diagnostics.CorrelationManager class.</span></span> <span data-ttu-id="8e62b-114">Wenn Sie System.Diagnostics.Trace.CorrelationManager.ActivityID bearbeiten, vergewissern Sie sich, dass der Wert auf den ursprünglichen Wert festgelegt wird, wenn die Ablaufsteuerung wieder an den WCF-Code übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="8e62b-114">If you manipulate System.Diagnostics.Trace.CorrelationManager.ActivityID, ensure that the value is set to original when execution control transfers back to WCF code.</span></span>  <span data-ttu-id="8e62b-115">Stellen Sie außerdem sicher, dass bei Verwendung eines asynchronen WCF-Programmiermodells System.Diagnostics.Trace.CorrelationManager.ActivityID zwischen den Threads übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="8e62b-115">Also, if you use an asynchronous WCF programming model ensure that System.Diagnostics.Trace.CorrelationManager.ActivityID is transferred between the threads.</span></span>  
  
## <a name="message-flow-tracing-and-rest-services"></a><span data-ttu-id="8e62b-116">Ablaufverfolgung des Nachrichtenflusses und REST-Dienste</span><span class="sxs-lookup"><span data-stu-id="8e62b-116">Message Flow Tracing and REST Services</span></span>  

 <span data-ttu-id="8e62b-117">Die Ablaufverfolgung des Nachrichtenflusses ermöglicht Ihnen die End-to-End-Ablaufverfolgung einer Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8e62b-117">Message flow tracing allows you to trace a request end to end.</span></span>  <span data-ttu-id="8e62b-118">Für SOAP-basierte Dienste wird in einem SOAP-Nachrichtenheader eine Aktivitäts-ID gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e62b-118">With SOAP-based services an Activity ID is sent in a SOAP message header.</span></span> <span data-ttu-id="8e62b-119">Dieser Header ist in REST-Anforderungen nicht enthalten, daher wird stattdessen ein spezieller HTTP-Ereignisheader verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e62b-119">REST requests do not contain this header so a special HTTP event header is used instead.</span></span> <span data-ttu-id="8e62b-120">Der folgende Codeausschnitt veranschaulicht, wie Sie den Wert der Aktivitäts-ID programmgesteuert abrufen können:</span><span class="sxs-lookup"><span data-stu-id="8e62b-120">The following code snippet shows how you can programmatically retrieve the Activity ID value:</span></span>  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 <span data-ttu-id="8e62b-121">Mit dem folgenden Code können Sie den Header programmgesteuert hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8e62b-121">You can programmatically add the header using the following code:</span></span>  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
