---
title: Serialisieren in Json mit Programmierung auf Nachrichtenebene
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 129b39051e5955181c33e6486ec3193383177e60
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546262"
---
# <a name="serializing-in-json-with-message-level-programming"></a>Serialisieren in Json mit Programmierung auf Nachrichtenebene
WCF unterstützt die Serialisierung von Daten im JSON-Format. In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.  
  
## <a name="typed-message-programming"></a>Programmieren typisierter Nachrichten  
 Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird. Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben. Um JSON für Anforderungen und Antworten zu verwenden. Legen Sie beide Optionen auf fest `WebMessageFormat.Json` .  Um JSON zu verwenden, müssen Sie das verwenden <xref:System.ServiceModel.WebHttpBinding> , das automatisch konfiguriert <xref:System.ServiceModel.Description.WebHttpBehavior> . Weitere Informationen zur WCF-Serialisierung finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md). Weitere Informationen zu JSON und WCF finden Sie unter [Service Station-eine Einführung in Rest-Dienste mit WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).  
  
> [!IMPORTANT]
> JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen. Dienste, die mit kommunizieren, <xref:System.ServiceModel.WebHttpBinding> unterstützen das verfügbar machen von Dienst Metadaten nicht, sodass Sie die Dienstverweis hinzufügen Funktionen von Visual Studio oder das Befehlszeilen Tool Svcutil nicht verwenden können, um einen Client seitigen Proxy zu generieren. Weitere Informationen dazu, wie Sie Dienste, die verwenden, Programm gesteuert aufzurufen, finden Sie unter Verwenden von <xref:System.ServiceModel.WebHttpBinding> [Rest-Diensten mit WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).  
  
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

- [AJAX-Integration und JSON-Unterstützung](ajax-integration-and-json-support.md)
- [Eigenständige JSON-Serialisierung.](stand-alone-json-serialization.md)
- [JSON-Serialisierung](../samples/json-serialization.md)
