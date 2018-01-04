---
title: Serialisieren in Json mit Programmierung auf Nachrichtenebene
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfa8952c54f29d88cb4975c1924b9c3e94c1c226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serialisieren in Json mit Programmierung auf Nachrichtenebene
WCF unterstützt die Serialisierung von Daten im JSON-Format. In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.  
  
## <a name="typed-message-programming"></a>Programmieren typisierter Nachrichten  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird. Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben. Um JSON für Anforderungen und Antworten zu verwenden, legen Sie beide Attribute auf `WebMessageFormat.Json` fest.  JSON erfordert die Verwendung der <xref:System.ServiceModel.WebHttpBinding>, die automatisch das <xref:System.ServiceModel.Description.WebHttpBehavior> konfiguriert. Weitere Informationen zu WCF-Serialisierung finden Sie unter: [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialisierung in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx). Weitere Informationen zu JSON und WCF finden Sie unter [eine Einführung in RESTfull-Dienste mit WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Erstellen von JSON-aktivierten WCF-Diensten in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), und [Übersicht über REST in WCF](http://msdn.microsoft.com/netframework/dd547388).  
  
> [!IMPORTANT]
>  JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen. Dienste, die Kommunikation mit dem <xref:System.ServiceModel.WebHttpBinding> unterstützen keine Verfügbarmachen von Dienstmetadaten, sodass Sie nicht zum Hinzufügen eines Dienstverweises-Funktionalität von Visual Studio oder das Befehlszeilentool "svcutil.exe" verwenden, um einen clientseitigen Proxy zu generieren können. Weitere Informationen, wie Sie programmgesteuert aufrufen können, bei denen Dienste <xref:System.ServiceModel.WebHttpBinding>, finden Sie unter [nutzen REST-Diensten mit WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
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
 [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [Eigenständige JSON-Serialisierung.](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [JSON-Serialisierung](../../../../docs/framework/wcf/samples/json-serialization.md)
