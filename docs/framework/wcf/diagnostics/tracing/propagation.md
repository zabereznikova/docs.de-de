---
title: Weitergabe
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: be010178d8f0face8f6c7e986107e4ea90d91953
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240133"
---
# <a name="propagation"></a><span data-ttu-id="cddf6-102">Weitergabe</span><span class="sxs-lookup"><span data-stu-id="cddf6-102">Propagation</span></span>

<span data-ttu-id="cddf6-103">In diesem Thema wird die Aktivitäts Propagierung im Windows Communication Foundation (WCF)-Ablauf Verfolgungs Modell beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cddf6-103">This topic describes activity propagation in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a><span data-ttu-id="cddf6-104">Verwenden der Weitergabe zur Korrelation von Aktivitäten über Endpunkte hinaus</span><span class="sxs-lookup"><span data-stu-id="cddf6-104">Using Propagation to Correlate Activities Across Endpoints</span></span>  

 <span data-ttu-id="cddf6-105">Die Weitergabe stellt dem Benutzer die direkte und anwendungsendpunktübergreifende Korrelation von Fehlerablaufverfolgungen für die gleiche Verarbeitungseinheit bereit. Ein Beispiel für einen solchen Anwendungsendpunkt wäre eine Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddf6-105">Propagation provides the user with direct correlation of error traces for the same unit of processing across application endpoints, for example, a request.</span></span> <span data-ttu-id="cddf6-106">Fehler, die an unterschiedlichen Endpunkten für die gleiche Verarbeitungseinheit (beispielsweise eine Anforderung) ausgegeben werden, werden in der gleichen Aktivität gruppiert (gilt auch über Anwendungsdomänen hinaus).</span><span class="sxs-lookup"><span data-stu-id="cddf6-106">Errors emitted at different endpoints for the same unit of processing are grouped in the same activity, even across application domains.</span></span> <span data-ttu-id="cddf6-107">Dies wird durch Weitergabe der Aktivitäts-ID in den Nachrichtenheadern bewerkstelligt.</span><span class="sxs-lookup"><span data-stu-id="cddf6-107">This is done through propagation of the activity ID in the message headers.</span></span> <span data-ttu-id="cddf6-108">Tritt also aufgrund eines internen Serverfehlers ein Timeout für einen Client auf, erscheinen beide Fehler bei der direkten Korrelation in der gleichen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cddf6-108">Therefore, if a client times out because of an internal error in the server, both errors appear in the same activity for direct correlation.</span></span>  
  
 <span data-ttu-id="cddf6-109">Verwenden Sie hierzu die `ActivityTracing`-Einstellung (wie im vorherigen Beispiel veranschaulicht).</span><span class="sxs-lookup"><span data-stu-id="cddf6-109">To do this, use the `ActivityTracing` setting as demonstrated in the previous example.</span></span> <span data-ttu-id="cddf6-110">Legen Sie darüber hinaus an allen Endpunkten das `propagateActivity`-Attribut für die `System.ServiceModel`-Ablaufverfolgungsquelle fest.</span><span class="sxs-lookup"><span data-stu-id="cddf6-110">In addition, set the `propagateActivity` attribute for the `System.ServiceModel` trace source at all endpoints.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 <span data-ttu-id="cddf6-111">Die Aktivitäts Weitergabe ist eine konfigurierbare Funktion, die bewirkt, dass WCF einen Header zu ausgehenden Nachrichten hinzufügt, einschließlich der Aktivitäts-ID auf dem TLS.</span><span class="sxs-lookup"><span data-stu-id="cddf6-111">Activity propagation is a configurable capability that causes WCF to add a header to outbound messages, which includes the activity ID on the TLS.</span></span> <span data-ttu-id="cddf6-112">Client- und Dienstaktivitäten können korreliert werden, indem dies bei nachfolgenden Ablaufverfolgungen auf der Serverseite eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="cddf6-112">By including this on subsequent traces on the server side, we can correlate client and server activities.</span></span>  
  
## <a name="propagation-definition"></a><span data-ttu-id="cddf6-113">Weitergabedefinition</span><span class="sxs-lookup"><span data-stu-id="cddf6-113">Propagation Definition</span></span>  

 <span data-ttu-id="cddf6-114">Die gAId von Aktivität M wird an Aktivität N weitergegeben, wenn alle der folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="cddf6-114">Activity M’s gAId is propagated to activity N if all of the following conditions apply.</span></span>  
  
- <span data-ttu-id="cddf6-115">N wird aufgrund von M erstellt.</span><span class="sxs-lookup"><span data-stu-id="cddf6-115">N is created because of M</span></span>  
  
- <span data-ttu-id="cddf6-116">Die gAId von M ist N bekannt.</span><span class="sxs-lookup"><span data-stu-id="cddf6-116">M’s gAId is known to N</span></span>  
  
- <span data-ttu-id="cddf6-117">Die gAId von N entspricht der gAId von M.</span><span class="sxs-lookup"><span data-stu-id="cddf6-117">N's gAId is equal to M’s gAId.</span></span>  
  
 <span data-ttu-id="cddf6-118">Die gAId wird über den ActivityId-Nachrichtenheader weitergegeben (wie im folgenden XML-Schema gezeigt):</span><span class="sxs-lookup"><span data-stu-id="cddf6-118">The gAId is propagated through the ActivityId message header, as illustrated in the following XML schema.</span></span>  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 <span data-ttu-id="cddf6-119">Im Folgenden finden Sie ein Beispiel für den Nachrichtenheader:</span><span class="sxs-lookup"><span data-stu-id="cddf6-119">The following is an example of the message header.</span></span>  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a><span data-ttu-id="cddf6-120">Weitergabe und Aktivitätsgrenzen</span><span class="sxs-lookup"><span data-stu-id="cddf6-120">Propagation and Activity Boundaries</span></span>  

 <span data-ttu-id="cddf6-121">Wird die Aktivitäts-ID für die Korrelation über Endpunkte hinaus weitergegeben, gibt der Nachrichtenempfänger Start- und Stop-Ablaufverfolgungen mit dieser (weitergegebenen) Aktivitäts-ID aus.</span><span class="sxs-lookup"><span data-stu-id="cddf6-121">When the activity ID is propagated across endpoints, the message receiver emits a Start and Stop traces with that (propagated) activity ID.</span></span> <span data-ttu-id="cddf6-122">Daher ist für jede Ablaufverfolgungsquelle eine Start- und Stop-Ablaufverfolgung mit dieser gAId vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cddf6-122">Therefore, there is a Start and Stop trace with that gAId from each trace source.</span></span> <span data-ttu-id="cddf6-123">Befinden sich die Endpunkte im gleichen Prozess und nutzen sie den gleichen Ablaufverfolgungsquellennamen, werden mehrere Start- und Stop-Prozesse mit der gleichen lAId erstellt (gleiche gAId, gleiche Ablaufverfolgungsquelle, gleicher Prozess).</span><span class="sxs-lookup"><span data-stu-id="cddf6-123">If the endpoints are in the same process and use the same trace source name, multiple Start and Stop with the same lAId (same gAId, same trace source, same process) are created.</span></span>  
  
## <a name="synchronization"></a><span data-ttu-id="cddf6-124">Synchronization</span><span class="sxs-lookup"><span data-stu-id="cddf6-124">Synchronization</span></span>  

 <span data-ttu-id="cddf6-125">Um Ereignisse über Endpunkte hinaus zu synchronisieren, die auf unterschiedlichen Computern laufen, wird eine CorrelationID zum Header der AcitivityId hinzugefügt, der in Nachrichten weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cddf6-125">To synchronize events across endpoints that run on different machines, a CorrelationId is added to the ActivityId header that is propagated in messages.</span></span> <span data-ttu-id="cddf6-126">Tools können diese ID verwenden, um Ereignisse über Computer mit Uhrabweichungen hinaus zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="cddf6-126">Tools can use this ID to synchronize events across machines with clock discrepancy.</span></span> <span data-ttu-id="cddf6-127">Insbesondere das Tool Service Trace Viewer nutzt diese ID, um Nachrichtenflüsse zwischen Endpunkten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cddf6-127">Specifically, the Service Trace Viewer tool uses this ID for showing message flows between endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cddf6-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cddf6-128">See also</span></span>

- [<span data-ttu-id="cddf6-129">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="cddf6-129">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="cddf6-130">Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="cddf6-130">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="cddf6-131">End-to-End-Ablaufverfolgungsszenarien</span><span class="sxs-lookup"><span data-stu-id="cddf6-131">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="cddf6-132">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="cddf6-132">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
