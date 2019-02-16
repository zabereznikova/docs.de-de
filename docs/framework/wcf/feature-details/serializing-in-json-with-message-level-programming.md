---
title: Serialisieren in Json mit Programmierung auf Nachrichtenebene
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 7f4f9a136c3e6261c7e5fca516c42f83c3ea4403
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332909"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serialisieren in Json mit Programmierung auf Nachrichtenebene
WCF unterstützt die Serialisierung von Daten im JSON-Format. In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.  
  
## <a name="typed-message-programming"></a>Programmieren typisierter Nachrichten  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird. Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben. Um JSON für Anforderungen und Antworten zu verwenden, legen Sie beide Attribute auf `WebMessageFormat.Json` fest.  JSON erfordert die Verwendung der <xref:System.ServiceModel.WebHttpBinding>, die automatisch das <xref:System.ServiceModel.Description.WebHttpBehavior> konfiguriert. Weitere Informationen zu WCF-Serialisierung finden Sie unter [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). Weitere Informationen zu JSON und WCF finden Sie unter [eine Einführung in RESTfull-Dienste mit WCF](https://msdn.microsoft.com/magazine/dd315413.aspx) und [erstellen JSON-fähiger WCF-Dienste in .NET 3.5](https://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx).  
  
> [!IMPORTANT]
>  JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen. Dienste, die die Kommunikation mit dem <xref:System.ServiceModel.WebHttpBinding> unterstützen keine Verfügbarmachen von Dienstmetadaten, sodass Sie nicht Visual Studio Dienstverweis hinzufügen oder das Befehlszeilentool Svcutil verwenden, um einen clientseitigen Proxy zu generieren. Weitere Informationen zum programmgesteuerten aufrufen können Dienste, <xref:System.ServiceModel.WebHttpBinding>, finden Sie unter [Verwenden von REST-Diensten mit WCF](https://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## <a name="untyped-message-programming"></a>Programmieren nicht typisierter Nachrichten  
 Beim direkten Arbeiten mit nicht typisierten Message-Objekten müssen Sie die Eigenschaften für die nicht typisierte Nachricht explizit festlegen, um sie im JSON-Format zu serialisieren. Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:  
  
```  
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
