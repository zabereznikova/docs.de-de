---
title: Serialisieren in Json mit Programmierung auf Nachrichtenebene
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 8343f7a8aa3c01557aae7df420351fa318cbb4b5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253933"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="c2d6d-102">Serialisieren in Json mit Programmierung auf Nachrichtenebene</span><span class="sxs-lookup"><span data-stu-id="c2d6d-102">Serializing in Json with Message Level Programming</span></span>

<span data-ttu-id="c2d6d-103">WCF unterstützt die Serialisierung von Daten im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="c2d6d-104">In diesem Thema wird beschrieben, wie WCF angewiesen wird, Typen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="c2d6d-105">Programmieren typisierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="c2d6d-105">Typed Message Programming</span></span>  

 <span data-ttu-id="c2d6d-106">Der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> wird verwendet, wenn das <xref:System.ServiceModel.Web.WebGetAttribute> oder <xref:System.ServiceModel.Web.WebInvokeAttribute> auf einen Dienstvorgang angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="c2d6d-107">Beide Attribute ermöglichen es Ihnen, das `RequestFormat` und das `ResponseFormat` anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="c2d6d-108">Um JSON für Anforderungen und Antworten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="c2d6d-109">Legen Sie beide Optionen auf fest `WebMessageFormat.Json` .</span><span class="sxs-lookup"><span data-stu-id="c2d6d-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="c2d6d-110">Um JSON zu verwenden, müssen Sie das verwenden <xref:System.ServiceModel.WebHttpBinding> , das automatisch konfiguriert <xref:System.ServiceModel.Description.WebHttpBehavior> .</span><span class="sxs-lookup"><span data-stu-id="c2d6d-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="c2d6d-111">Weitere Informationen zur WCF-Serialisierung finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="c2d6d-111">For more information about WCF serialization, see [Serialization and Deserialization](serialization-and-deserialization.md).</span></span> <span data-ttu-id="c2d6d-112">Weitere Informationen zu JSON und WCF finden Sie unter [Service Station-eine Einführung in Rest-Dienste mit WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="c2d6d-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c2d6d-113">JSON erfordert die Verwendung von <xref:System.ServiceModel.WebHttpBinding> und <xref:System.ServiceModel.Description.WebHttpBehavior>, die keine SOAP-Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="c2d6d-114">Dienste, die mit kommunizieren, <xref:System.ServiceModel.WebHttpBinding> unterstützen das verfügbar machen von Dienst Metadaten nicht, sodass Sie die Dienstverweis hinzufügen Funktionen von Visual Studio oder das Befehlszeilen Tool Svcutil nicht verwenden können, um einen Client seitigen Proxy zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="c2d6d-115">Weitere Informationen dazu, wie Sie Dienste, die verwenden, Programm gesteuert aufzurufen, finden Sie unter Verwenden von <xref:System.ServiceModel.WebHttpBinding> [Rest-Diensten mit WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="c2d6d-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="c2d6d-116">Programmieren nicht typisierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="c2d6d-116">Untyped Message Programming</span></span>  

 <span data-ttu-id="c2d6d-117">Beim direkten Arbeiten mit nicht typisierten Message-Objekten müssen Sie die Eigenschaften für die nicht typisierte Nachricht explizit festlegen, um sie im JSON-Format zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="c2d6d-118">Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="c2d6d-118">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2d6d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2d6d-119">See also</span></span>

- [<span data-ttu-id="c2d6d-120">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c2d6d-120">AJAX Integration and JSON Support</span></span>](ajax-integration-and-json-support.md)
- [<span data-ttu-id="c2d6d-121">Eigenständige JSON-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="c2d6d-121">Stand-Alone JSON Serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="c2d6d-122">JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c2d6d-122">JSON Serialization</span></span>](../samples/json-serialization.md)
