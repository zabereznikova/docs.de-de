---
title: "Serialisieren in Json mit Programmierung auf Nachrichtenebene | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Serialisieren in Json mit Programmierung auf Nachrichtenebene
WCF unterstützt die Serialisierung von Daten im JSON\-Format.In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.  
  
## Programmierung typisierter Nachrichten  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird.Beide Attribute ermöglichen es Ihnen, `RequestFormat` und `ResponseFormat` anzugeben.Um JSON für Anforderungen und Antworten zu verwenden, legen Sie beide auf `WebMessageFormat.Json` fest.Um JSON zu verwenden, müssen Sie <xref:System.ServiceModel.WebHttpBinding> verwenden, durch die <xref:System.ServiceModel.Description.WebHttpBehavior> automatisch konfiguriert wird.Weitere Informationen über die WCF\-Serialisierung finden Sie unter: [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md). [Serialisierung in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx)Weitere Informationen über JSON und WCF finden Sie unter [Eine Einführung in RESTfull\-Dienste mit WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Erstellen JSON\-fähiger WCF\-Dienste in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx) und [Übersicht über REST in WCF](http://msdn.microsoft.com/netframework/dd547388).  
  
> [!IMPORTANT]
>  Die Verwendung von JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP\-Kommunikation unterstützen.Dienste, die mit <xref:System.ServiceModel.WebHttpBinding> kommunizieren, bieten keine Unterstützung für das Verfügbarmachen von Dienstmetadaten, sodass Sie "Dienstverweis hinzufügen" in Visual Studio und das Befehlszeilentool svcutil nicht verwenden können, um einen clientseitigen Proxy zu generieren.Weitere Informationen, wie Sie programmgesteuert Dienste aufrufen können, die <xref:System.ServiceModel.WebHttpBinding> verwenden, finden Sie unter [Konsumieren von REST\-Diensten mit WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).  
  
## Programmierung nicht typisierter Nachrichten  
 Beim direkten Arbeiten mit nicht typisierten Message\-Objekten müssen Sie die Eigenschaften für die nicht typisierte Nachricht explizit festlegen, um sie als JSON zu serialisieren.Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
  
```  
  
## Siehe auch  
 [AJAX\-Integration und JSON\-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)   
 [Eigenständige JSON\-Serialisierung.](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [JSON\-Serialisierung](../../../../docs/framework/wcf/samples/json-serialization.md)