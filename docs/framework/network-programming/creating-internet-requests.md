---
title: Erstellen von Internetanforderungen
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
ms.openlocfilehash: 80e3a6bd199691df9391e88d5a64fab5df2a08a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048622"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="2d512-102">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="2d512-102">Creating Internet Requests</span></span>
<span data-ttu-id="2d512-103">Anwendungen erstellen mithilfe der <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Methode <xref:System.Net.WebRequest>-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="2d512-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2d512-104">Diese statische Methode erstellt eine von **WebRequest** abgeleitete Klasse basierend auf dem URI-Schema, das an sie übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2d512-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="2d512-105">Web-, Datei- und FTP-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d512-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="2d512-106">.NET Framework stellt die von **WebRequest** abgeleitete <xref:System.Net.HttpWebRequest>-Klasse bereit, um HTTP- und HTTPS-Anforderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d512-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="2d512-107">In den meisten Fällen stellt die **WebRequest**-Klasse alle für eine Anforderung erforderlichen Eigenschaften bereit. Bei Bedarf können Sie jedoch mit der **WebRequest.Create**-Methode erstellte **WebRequest**-Objekte in den Typ **HttpWebRequest** umwandeln, um auf die HTTP-spezifischen Eigenschaften der Anforderung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2d512-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="2d512-108">Auf ähnliche Weise werden die Antworten von HTTP- und HTTPS-Anforderungen durch das **HttpWebResponse**-Objekt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2d512-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="2d512-109">Wenn Sie auf die HTTP-spezifischen Eigenschaften des **HttpWebResponse**-Objekts zugreifen möchten, müssen Sie **WebResponse**-Objekte in den Typ **HttpWebResponse** umwandeln.</span><span class="sxs-lookup"><span data-stu-id="2d512-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="2d512-110">.NET Framework stellt außerdem die Klassen <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> zum Verarbeiten von Anforderungen für Ressourcen bereit, die das URI-Schema „file:“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d512-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="2d512-111">Dementsprechend werden die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> zur Verarbeitung von Anforderungen für Ressourcen bereitgestellt, die das Schema „ftp:“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d512-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="2d512-112">Bei Anforderungen für eine Ressource, die eines dieser Schemas verwendet, können Sie mithilfe der **WebRequest.Create**-Methode ein Objekt abrufen, mit dem Sie die Anforderung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2d512-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="2d512-113">Bei Anforderungen, die andere Protokolle auf Anwendungsebene verwenden, müssen Sie von **WebRequest** und **WebResponse** abgeleitete protokollspezifische Klassen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2d512-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="2d512-114">Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="2d512-114">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d512-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d512-115">See also</span></span>

- [<span data-ttu-id="2d512-116">Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="2d512-116">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="2d512-117">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="2d512-117">Requesting Data</span></span>](requesting-data.md)
