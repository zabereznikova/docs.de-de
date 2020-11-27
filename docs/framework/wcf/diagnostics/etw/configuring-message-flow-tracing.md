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
# <a name="configuring-message-flow-tracing"></a>Konfigurieren der Ablaufverfolgung des Nachrichtenflusses

Wenn Windows Communication Foundation (WCF)-Aktivitäts Ablauf Verfolgung aktiviert ist, werden End-to-End-Aktivitäts-IDs logischen Aktivitäten im gesamten WCF-Stapel zugewiesen. [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] verfügt jetzt über eine leistungsstärkere Version dieser Funktion, die in Verbindung mit der Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW) verwendet werden kann und als Ablaufverfolgung des Nachrichtenflusses bezeichnet wird. Bei Aktivierung dieser Funktion werden die End-to-End-Aktivität-IDs von eingehenden Nachrichten verwendet (bzw. bei Bedarf zugewiesen) und für alle Ablaufverfolgungsereignisse übernommen, die ausgegeben werden, nachdem die Nachricht vom Kanal decodiert wurde. Kunden können diese Funktion zum Wiederherstellen von Nachrichtenflüssen mit Ablaufverfolgungsprotokollen verschiedener Dienste nach der Decodierung verwenden.  
  
 Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wurde, und dann wieder deaktiviert werden, nachdem das Problem behoben wurde.  
  
## <a name="enabling-tracing"></a>Aktivieren der Ablaufverfolgung  

 Sie können die Ablaufverfolgung des Nachrichtenflusses aktivieren, in dem Sie das `messageFlowTracing`-Konfigurationselement für .NET Framework 4 auf `true` festlegen. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
> Da das `endToEndTracing`-Konfigurationselement in einer Web.config-Datei enthalten ist, kann es nicht wie unter ETW dynamisch konfiguriert werden. Damit das `endToEndTracing`-Konfigurationselement wirksam wird, muss die Anwendung wiederverwendet werden.  
  
 Aktivitäten werden durch den Austausch eines Bezeichners, der sogenannten Aktivitäts-ID, korreliert. Dieser Bezeichner ist eine GUID und wird von der System.Diagnostics.CorrelationManager-Klasse generiert. Wenn Sie System.Diagnostics.Trace.CorrelationManager.ActivityID bearbeiten, vergewissern Sie sich, dass der Wert auf den ursprünglichen Wert festgelegt wird, wenn die Ablaufsteuerung wieder an den WCF-Code übertragen wird.  Stellen Sie außerdem sicher, dass bei Verwendung eines asynchronen WCF-Programmiermodells System.Diagnostics.Trace.CorrelationManager.ActivityID zwischen den Threads übertragen wird.  
  
## <a name="message-flow-tracing-and-rest-services"></a>Ablaufverfolgung des Nachrichtenflusses und REST-Dienste  

 Die Ablaufverfolgung des Nachrichtenflusses ermöglicht Ihnen die End-to-End-Ablaufverfolgung einer Anforderung.  Für SOAP-basierte Dienste wird in einem SOAP-Nachrichtenheader eine Aktivitäts-ID gesendet. Dieser Header ist in REST-Anforderungen nicht enthalten, daher wird stattdessen ein spezieller HTTP-Ereignisheader verwendet. Der folgende Codeausschnitt veranschaulicht, wie Sie den Wert der Aktivitäts-ID programmgesteuert abrufen können:  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 Mit dem folgenden Code können Sie den Header programmgesteuert hinzufügen:  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
