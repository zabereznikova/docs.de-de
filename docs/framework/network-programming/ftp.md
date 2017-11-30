---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d7b169a6de494d10fa332ebf5f2aa315ae69653a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ftp"></a><span data-ttu-id="4d7f6-102">FTP</span><span class="sxs-lookup"><span data-stu-id="4d7f6-102">FTP</span></span>
<span data-ttu-id="4d7f6-103">.NET Framework bietet durch die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> eine umfassende Unterstützung für das FTP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="4d7f6-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="4d7f6-104">Diese Klassen werden von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4d7f6-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="4d7f6-105">In den meisten Klassen stellen die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die FTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen zu <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> umwandeln.</span><span class="sxs-lookup"><span data-stu-id="4d7f6-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4d7f6-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4d7f6-106">Examples</span></span>  
 <span data-ttu-id="4d7f6-107">Weitere Informationen finden Sie in den folgenden Themen: [How to: Download Files with FTP (Vorgehensweise: Herunterladen von Dateien mit FTP)](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP (Vorgehensweise: Hochladen von Dateien mit FTP)](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) und [How to: List Directory Contents with FTP (Vorgehensweise: Auflisten von Verzeichnisinhalten mit FTP)](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="4d7f6-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="4d7f6-108">FTP und Proxys</span><span class="sxs-lookup"><span data-stu-id="4d7f6-108">FTP and proxies</span></span>  
 <span data-ttu-id="4d7f6-109">Wenn es sich bei einem Proxy (angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>-Eigenschaft) um einen HTTP-Proxy handelt, werden nur die <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>-, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>- und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>-Befehle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d7f6-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7f6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d7f6-110">See Also</span></span>  
 [<span data-ttu-id="4d7f6-111">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="4d7f6-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="4d7f6-112">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="4d7f6-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="4d7f6-113">Beispiel zur FTP-Clienttechnologie</span><span class="sxs-lookup"><span data-stu-id="4d7f6-113">FTP Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [<span data-ttu-id="4d7f6-114">Beispiel zur FTP-Explorer-Technologie</span><span class="sxs-lookup"><span data-stu-id="4d7f6-114">FTP Explorer Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [<span data-ttu-id="4d7f6-115">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="4d7f6-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
