---
title: HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f72a77e19d04c0dd55887628033f7c975ac3ff25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="http"></a><span data-ttu-id="7281b-102">HTTP</span><span class="sxs-lookup"><span data-stu-id="7281b-102">HTTP</span></span>
<span data-ttu-id="7281b-103">.NET Framework bietet eine umfassende Unterstützung für das HTTP-Protokoll, mit den Großteil alle Internetdatenverkehr, wodurch die <xref:System.Net.HttpWebRequest> und <xref:System.Net.HttpWebResponse> Klassen.</span><span class="sxs-lookup"><span data-stu-id="7281b-103">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="7281b-104">Diese Klassen, die von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet wurden, werden standardmäßig zurückgegeben, wenn die statische Methode <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> eine URI findet, die mit „http“ oder „https“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="7281b-104">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="7281b-105">In den meisten Klassen stellen die Klassen **WebRequest** und **WebResponse** alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die HTTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen in **HttpWebRequest** oder **HttpWebResponse** umwandeln.</span><span class="sxs-lookup"><span data-stu-id="7281b-105">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="7281b-106">**HttpWebRequest** und **HttpWebResponse** kapseln eine Standard-HTTP-Anforderung für Anforderung und Antwort ein und bieten Zugriff auf allgemeine HTTP-Header.</span><span class="sxs-lookup"><span data-stu-id="7281b-106">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="7281b-107">Diese Klassen unterstützen auch die meisten HTTP 1.1-Features, einschließlich der Pipeline, dem Senden und Empfangen von Nachrichten in Segmenten, der Authentifizierung, der Präauthentifizierung, der Verschlüsselung, der Proxyunterstützung, der Überprüfung von Serverzertifikaten und der Verbindungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="7281b-107">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="7281b-108">Benutzerdefinierte Header und Header, die nicht von Eigenschaften bereitgestellt werden, können in der **Header**-Eigenschaft gespeichert und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7281b-108">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="7281b-109">**HttpWebRequest** ist die Standardklasse, die von **WebRequest** verwendet wird und muss nicht registriert werden, bevor Sie eine URI an die Methode **WebRequest.Create** übergeben können.</span><span class="sxs-lookup"><span data-stu-id="7281b-109">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="7281b-110">Ihre Anwendung kann HTTP-Umleitungen automatisch folgen, indem Sie die <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A>-Eigenschaft auf **TRUE** (Standardeinstellung) festlegen.</span><span class="sxs-lookup"><span data-stu-id="7281b-110">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="7281b-111">Die Anwendung leitet dann Anforderungen um, und die <xref:System.Net.HttpWebResponse.ResponseUri%2A>-Eigenschaft von **HttpWebResponse** enthält die tatsächliche Webressource, die auf die Anforderung reagiert hat.</span><span class="sxs-lookup"><span data-stu-id="7281b-111">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="7281b-112">Wenn Sie **AllowAutoRedirect** auf **FALSE** festlegen, muss Ihre Anwendung dazu in der Lage sein, Umleitungen als HTTP-Protokollfehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="7281b-112">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="7281b-113">Anwendungen erhalten HTTP-Protokollfehler, indem Sie <xref:System.Net.WebException> abfangen, wenn <xref:System.Net.WebException.Status%2A> auf <xref:System.Net.WebExceptionStatus> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7281b-113">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="7281b-114">Die <xref:System.Net.WebException.Response%2A>-Eigenschaft enthält **WebResponse**. Dieses wurde vom Server gesendet und gibt den tatsächlich aufgetretenen HTTP-Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7281b-114">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7281b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7281b-115">See Also</span></span>  
 [<span data-ttu-id="7281b-116">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="7281b-116">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="7281b-117">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="7281b-117">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="7281b-118">Vorgehensweise: Zugreifen auf HTTP-spezifische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7281b-118">How to: Access HTTP-Specific Properties</span></span>](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)
