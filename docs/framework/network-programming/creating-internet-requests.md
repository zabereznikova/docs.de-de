---
title: Erstellen von Internetanforderungen
description: Erfahren Sie, wie Anwendungen WebRequest-Instanzen über die Methode WebRequest.Create erstellen, die eine abgeleitete Klasse auf Grundlage des an sie übergebenen URI-Schemas erstellt.
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325641"
---
# <a name="create-internet-requests"></a><span data-ttu-id="64282-103">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="64282-103">Create internet requests</span></span>

<span data-ttu-id="64282-104">Anwendungen erstellen mithilfe der <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Methode <xref:System.Net.WebRequest>-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="64282-104">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="64282-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> ist eine statische Methode, die eine von <xref:System.Net.WebRequest> abgeleitete Klasse basierend auf dem an sie übergebenen URI-Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="64282-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> is a static method that creates a class derived from <xref:System.Net.WebRequest> based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="64282-106">Web- und Dateianforderungen sowie FTP-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64282-106">Web, file, and FTP requests</span></span>

<span data-ttu-id="64282-107">Das .NET Framework stellt die von `WebRequest` abgeleitete Klasse <xref:System.Net.HttpWebRequest> bereit, um HTTP- und HTTPS-Anforderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="64282-107">.NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from `WebRequest`, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="64282-108">In den meisten Fällen stellt die Klasse `WebRequest` alle für eine Anforderung erforderlichen Eigenschaften bereit. Bei Bedarf können Sie jedoch von der Methode `WebRequest.Create` erstellte `WebRequest`-Objekte in den Typ `HttpWebRequest` umwandeln, um auf die HTTP-spezifischen Eigenschaften der Anforderung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="64282-108">In most cases, the `WebRequest` class provides all the properties you need to make a request; however, if necessary, you can cast `WebRequest` objects created by the `WebRequest.Create` method to the `HttpWebRequest` type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="64282-109">Auf ähnliche Weise werden die Antworten auf HTTP- und HTTPS-Anforderungen durch das `HttpWebResponse`-Objekt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="64282-109">Similarly, the `HttpWebResponse` object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="64282-110">Sie müssen `WebResponse`-Objekte in den Typ `HttpWebResponse` umwandeln, um auf die HTTP-spezifischen Eigenschaften des `HttpWebResponse`-Objekts zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="64282-110">To access the HTTP-specific properties of the `HttpWebResponse` object, you need to cast `WebResponse` objects to the `HttpWebResponse` type.</span></span>  
  
<span data-ttu-id="64282-111">Das .NET Framework stellt außerdem die Klassen <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> zum Verarbeiten von Anforderungen für Ressourcen bereit, die das URI-Schema „file:“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="64282-111">.NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="64282-112">Dementsprechend werden die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> zur Verarbeitung von Anforderungen für Ressourcen bereitgestellt, die das Schema „ftp:“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="64282-112">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="64282-113">Bei Anforderungen für eine Ressource, die eines dieser Schemas verwendet, können Sie mithilfe der Methode `WebRequest.Create` ein Objekt abrufen, das Sie für die Anforderung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="64282-113">If your request is for a resource that uses any of these schemes, you can use the `WebRequest.Create` method to obtain an object with which to make your request.</span></span>  
  
<span data-ttu-id="64282-114">Implementieren Sie von `WebRequest` und `WebResponse` abgeleitete protokollspezifische Klassen, um Anforderungen zu verarbeiten, die andere Protokolle auf Anwendungsebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="64282-114">To handle requests that use other application-level protocols, implement protocol-specific classes derived from `WebRequest` and `WebResponse`.</span></span> <span data-ttu-id="64282-115">Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="64282-115">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64282-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64282-116">See also</span></span>

- [<span data-ttu-id="64282-117">How to: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="64282-117">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="64282-118">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="64282-118">Requesting Data</span></span>](requesting-data.md)
