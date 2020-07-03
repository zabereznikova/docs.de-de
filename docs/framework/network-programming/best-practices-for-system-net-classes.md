---
title: Bewährte Methoden für System.Net-Klassen
description: Halten Sie sich an die folgenden Empfehlungen zur optimalen Verwendung der in System.Net enthaltenen Klassen bei der .NET Framework-Programmierung.
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
ms.openlocfilehash: 583fa5e57c7c4d60252dddfd425596e7acad7c0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502677"
---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="b5905-103">Bewährte Methoden für System.Net-Klassen</span><span class="sxs-lookup"><span data-stu-id="b5905-103">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="b5905-104">Mit den folgenden Empfehlungen können Sie die in <xref:System.Net> enthaltenen Klassen bestmöglich verwenden:</span><span class="sxs-lookup"><span data-stu-id="b5905-104">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
- <span data-ttu-id="b5905-105">Bewährte Methoden für Transport Layer Security (TLS) finden Sie unter [Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework](tls.md).</span><span class="sxs-lookup"><span data-stu-id="b5905-105">For Transport Layer Security (TLS) best practices, see [Transport Layer Security (TLS) best practices with .NET Framework](tls.md).</span></span>

- <span data-ttu-id="b5905-106">Verwenden Sie nach Möglichkeit <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> anstelle der Typumwandlung in abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="b5905-106">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="b5905-107">Anwendungen, die **WebRequest** und **WebResponse** verwenden, profitieren von neuen Internetprotokollen ohne umfangreiche Codeänderungen.</span><span class="sxs-lookup"><span data-stu-id="b5905-107">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
- <span data-ttu-id="b5905-108">Beim Schreiben von ASP.NET-Anwendungen, die auf einem Server mit den **System.Net**-Klassen ausgeführt werden, ist es leistungstechnisch gesehen häufig besser, asynchrone Methoden für <xref:System.Net.WebRequest.GetResponse%2A> und <xref:System.Net.WebResponse.GetResponseStream%2A> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5905-108">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
- <span data-ttu-id="b5905-109">Die Anzahl der offenen Verbindungen einer Internetressource haben einen erheblichen Einfluss auf die Netzwerkleistung und den Durchsatz.</span><span class="sxs-lookup"><span data-stu-id="b5905-109">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="b5905-110">**System.Net** verwendet standardmäßig zwei Verbindungen pro Anwendung und pro Host.</span><span class="sxs-lookup"><span data-stu-id="b5905-110">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="b5905-111">Das Festlegen der <xref:System.Net.ServicePoint.ConnectionLimit%2A>-Eigenschaft in <xref:System.Net.ServicePoint> für Ihre Anwendung kann diese Zahl für einen bestimmten Host erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b5905-111">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="b5905-112">Das Festlegen der <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType>-Eigenschaft kann diese Standardeinstellung für alle Hosts erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b5905-112">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> property can increase this default for all hosts.</span></span>  
  
- <span data-ttu-id="b5905-113">Beim Schreiben von Protokollen auf Socketebene versuchen Sie nach Möglichkeit <xref:System.Net.Sockets.TcpClient> oder <xref:System.Net.Sockets.UdpClient> zu verwenden, anstatt direkt <xref:System.Net.Sockets.Socket> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b5905-113">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="b5905-114">Diese zwei Clientklassen kapseln die Erstellung von TCP- und UDP-Sockets, ohne dass Sie die Details der Verbindung behandeln.</span><span class="sxs-lookup"><span data-stu-id="b5905-114">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
- <span data-ttu-id="b5905-115">Verwenden Sie beim Zugriff auf Websites, die Anmeldeinformationen erfordern, die <xref:System.Net.CredentialCache>-Klasse zum Erstellen eines Zwischenspeichers für Anmeldeinformationen, anstatt sie mit jeder Anforderung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5905-115">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="b5905-116">Die **CredentialCache**-Klasse durchsucht den Zwischenspeicher nach den entsprechenden Anmeldeinformationen für eine Anforderung, sodass Sie keine Verantwortung für das Erstellen und Bereitstellen von Anmeldeinformationen auf Basis der URL haben.</span><span class="sxs-lookup"><span data-stu-id="b5905-116">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5905-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5905-117">See also</span></span>

- [<span data-ttu-id="b5905-118">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b5905-118">Network Programming in the .NET Framework</span></span>](index.md)
