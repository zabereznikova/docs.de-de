---
title: Serialisieren in Json mit Programmierung auf Nachrichtenebene
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 1492ba138b5ae706e3ae70f416e95565d4b60d78
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976109"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serialisieren in Json mit Programmierung auf Nachrichtenebene
WCF unterstützt die Serialisierung von Daten im JSON-Format. In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.  
  
## <a name="typed-message-programming"></a>Programmieren typisierter Nachrichten  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird. Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben. Um JSON für Anforderungen und Antworten zu verwenden. Legen Sie beide Optionen auf `WebMessageFormat.Json`fest.  Um JSON zu verwenden, müssen Sie das <xref:System.ServiceModel.WebHttpBinding>verwenden, das die <xref:System.ServiceModel.Description.WebHttpBehavior>automatisch konfiguriert. Weitere Informationen zur WCF-Serialisierung finden Sie unter [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Weitere Informationen zu JSON und WCF finden Sie unter [Service Station-eine Einführung in Rest-Dienste mit WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen. Dienste, die mit dem <xref:System.ServiceModel.WebHttpBinding> kommunizieren, unterstützen das verfügbar machen von Dienst Metadaten nicht, sodass Sie die Dienstverweis hinzufügen-Funktionalität von Visual Studio oder das Befehlszeilen Tool Svcutil nicht verwenden können, um einen Client seitigen Proxy zu generieren. Weitere Informationen zum programmgesteuerten Abrufen von Diensten, die <xref:System.ServiceModel.WebHttpBinding>verwenden, finden Sie unter Verwenden von [Rest-Diensten mit WCF](https://blogs.msdn.microsoft.com/pedram/2008/04/21/how-to-consume-rest-services-with-wcf/).  
  
## <a name="untyped-message-programming"></a>Programmieren nicht typisierter Nachrichten  
 Beim direkten Arbeiten mit nicht typisierten Message-Objekten müssen Sie die Eigenschaften für die nicht typisierte Nachricht explizit festlegen, um sie im JSON-Format zu serialisieren. Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a>Siehe auch

- [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [Eigenständige JSON-Serialisierung.](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [JSON-Serialisierung](../../../../docs/framework/wcf/samples/json-serialization.md)
