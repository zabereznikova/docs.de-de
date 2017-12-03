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
ms.openlocfilehash: 3967cd7002af8ff9aee4c4f25bd2422d2d0ea1ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="b4fa3-102">Serialisieren in Json mit Programmierung auf Nachrichtenebene</span><span class="sxs-lookup"><span data-stu-id="b4fa3-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="b4fa3-103">WCF unterstützt die Serialisierung von Daten im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="b4fa3-104">In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="b4fa3-105">Programmieren typisierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b4fa3-105">Typed Message Programming</span></span>  
 <span data-ttu-id="b4fa3-106">Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="b4fa3-107">Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="b4fa3-108">Um JSON für Anforderungen und Antworten zu verwenden, legen Sie beide Attribute auf `WebMessageFormat.Json` fest.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="b4fa3-109">JSON erfordert die Verwendung der <xref:System.ServiceModel.WebHttpBinding>, die automatisch das <xref:System.ServiceModel.Description.WebHttpBehavior> konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="b4fa3-110">Weitere Informationen zu WCF-Serialisierung finden Sie unter: [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialisierung in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4fa3-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="b4fa3-111">Weitere Informationen zu JSON und WCF finden Sie unter [eine Einführung in RESTfull-Dienste mit WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Erstellen von JSON-aktivierten WCF-Diensten in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), und [Übersicht über REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="b4fa3-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4fa3-112">JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="b4fa3-113">Dienste, die Kommunikation mit dem <xref:System.ServiceModel.WebHttpBinding> unterstützen keine Verfügbarmachen von Dienstmetadaten, sodass Sie nicht zum Hinzufügen eines Dienstverweises-Funktionalität von Visual Studio oder das Befehlszeilentool "svcutil.exe" verwenden, um einen clientseitigen Proxy zu generieren können.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="b4fa3-114">Weitere Informationen, wie Sie programmgesteuert aufrufen können, bei denen Dienste <xref:System.ServiceModel.WebHttpBinding>, finden Sie unter [nutzen REST-Diensten mit WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4fa3-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="b4fa3-115">Programmieren nicht typisierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b4fa3-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="b4fa3-116">Beim direkten Arbeiten mit nicht typisierten Message-Objekten müssen Sie die Eigenschaften für die nicht typisierte Nachricht explizit festlegen, um sie im JSON-Format zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="b4fa3-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="b4fa3-117">Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="b4fa3-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4fa3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4fa3-118">See Also</span></span>  
 [<span data-ttu-id="b4fa3-119">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="b4fa3-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="b4fa3-120">Eigenständige JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b4fa3-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="b4fa3-121">JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b4fa3-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
