---
title: Weitergabe
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: 680f732fa4e75eb1eaa82a861f0a0021dc9c974c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686334"
---
# <a name="propagation"></a>Weitergabe
Dieses Thema beschreibt die Aktivitätsweitergabe im ablaufverfolgungsmodell Windows Communication Foundation (WCF).  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a>Verwenden der Weitergabe zur Korrelation von Aktivitäten über Endpunkte hinaus  
 Die Weitergabe stellt dem Benutzer die direkte und anwendungsendpunktübergreifende Korrelation von Fehlerablaufverfolgungen für die gleiche Verarbeitungseinheit bereit. Ein Beispiel für einen solchen Anwendungsendpunkt wäre eine Anforderung. Fehler, die an unterschiedlichen Endpunkten für die gleiche Verarbeitungseinheit (beispielsweise eine Anforderung) ausgegeben werden, werden in der gleichen Aktivität gruppiert (gilt auch über Anwendungsdomänen hinaus). Dies wird durch Weitergabe der Aktivitäts-ID in den Nachrichtenheadern bewerkstelligt. Tritt also aufgrund eines internen Serverfehlers ein Timeout für einen Client auf, erscheinen beide Fehler bei der direkten Korrelation in der gleichen Aktivität.  
  
 Verwenden Sie hierzu die `ActivityTracing`-Einstellung (wie im vorherigen Beispiel veranschaulicht). Legen Sie darüber hinaus an allen Endpunkten das `propagateActivity`-Attribut für die `System.ServiceModel`-Ablaufverfolgungsquelle fest.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 Aktivitätsweitergabe handelt es sich um eine konfigurierbare Funktion, die WCF zum Hinzufügen eines Headers zu ausgehenden Nachrichten wird die Aktivitäts-ID auf dem TLS enthält. Client- und Dienstaktivitäten können korreliert werden, indem dies bei nachfolgenden Ablaufverfolgungen auf der Serverseite eingeschlossen wird.  
  
## <a name="propagation-definition"></a>Weitergabedefinition  
 Die gAId von Aktivität M wird an Aktivität N weitergegeben, wenn alle der folgenden Bedingungen erfüllt sind:  
  
-   N wird aufgrund von M erstellt.  
  
-   Die gAId von M ist N bekannt.  
  
-   Die gAId von N entspricht der gAId von M.  
  
 Die gAId wird über den ActivityId-Nachrichtenheader weitergegeben (wie im folgenden XML-Schema gezeigt):  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 Im Folgenden finden Sie ein Beispiel für den Nachrichtenheader:  
  
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
  
## <a name="propagation-and-activity-boundaries"></a>Weitergabe und Aktivitätsgrenzen  
 Wird die Aktivitäts-ID für die Korrelation über Endpunkte hinaus weitergegeben, gibt der Nachrichtenempfänger Start- und Stop-Ablaufverfolgungen mit dieser (weitergegebenen) Aktivitäts-ID aus. Daher ist für jede Ablaufverfolgungsquelle eine Start- und Stop-Ablaufverfolgung mit dieser gAId vorhanden. Befinden sich die Endpunkte im gleichen Prozess und nutzen sie den gleichen Ablaufverfolgungsquellennamen, werden mehrere Start- und Stop-Prozesse mit der gleichen lAId erstellt (gleiche gAId, gleiche Ablaufverfolgungsquelle, gleicher Prozess).  
  
## <a name="synchronization"></a>Synchronisierung  
 Um Ereignisse über Endpunkte hinaus zu synchronisieren, die auf unterschiedlichen Computern laufen, wird eine CorrelationID zum Header der AcitivityId hinzugefügt, der in Nachrichten weitergegeben wird. Tools können diese ID verwenden, um Ereignisse über Computer mit Uhrabweichungen hinaus zu synchronisieren. Insbesondere das Tool Service Trace Viewer nutzt diese ID, um Nachrichtenflüsse zwischen Endpunkten anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch
- [Konfigurieren der Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [End-to-End-Ablaufverfolgungsszenarien](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
