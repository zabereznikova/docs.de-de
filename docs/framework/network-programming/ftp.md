---
title: 'FTP: .NET'
description: Hier erfahren Sie mehr über die umfassende Unterstützung für das FTP-Protokoll, das das .NET Framework mithilfe der Klassen „FtpWebRequest“ und „FtpWebResponse“ bereitstellt.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502586"
---
# <a name="ftp"></a><span data-ttu-id="327da-103">FTP</span><span class="sxs-lookup"><span data-stu-id="327da-103">FTP</span></span>

<span data-ttu-id="327da-104">.NET Framework bietet durch die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> eine umfassende Unterstützung für das FTP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="327da-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="327da-105">Diese Klassen werden von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="327da-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="327da-106">In den meisten Klassen stellen die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die FTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen zu <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> umwandeln.</span><span class="sxs-lookup"><span data-stu-id="327da-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="327da-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="327da-107">Examples</span></span>

<span data-ttu-id="327da-108">Weitere Informationen finden Sie unter den folgenden Themen: [How to: Herunterladen von Dateien über FTP](how-to-download-files-with-ftp.md), [Vorgehensweise: Hochladen von Dateien über FTP](how-to-upload-files-with-ftp.md) und [Vorgehensweise: Auflisten von Verzeichnisinhalt mit FTP](how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="327da-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="327da-109">FTP und Proxys</span><span class="sxs-lookup"><span data-stu-id="327da-109">FTP and proxies</span></span>

<span data-ttu-id="327da-110">Wenn es sich bei einem Proxy (angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>-Eigenschaft) um einen HTTP-Proxy handelt, werden nur die <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>-, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>- und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>-Befehle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="327da-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="327da-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="327da-111">See also</span></span>

- [<span data-ttu-id="327da-112">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="327da-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="327da-113">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="327da-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="327da-114">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="327da-114">Using Application Protocols</span></span>](using-application-protocols.md)
