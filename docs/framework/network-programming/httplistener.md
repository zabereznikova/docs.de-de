---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: db2c42dab15b4282c5474c50f970ffe47a101215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393451"
---
# <a name="httplistener"></a><span data-ttu-id="51ad9-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="51ad9-102">HttpListener</span></span>
<span data-ttu-id="51ad9-103">Die <xref:System.Net.HttpListener>-Klasse stellt einen programmgesteuerten HTTP-Protokolllistener bereit.</span><span class="sxs-lookup"><span data-stu-id="51ad9-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="51ad9-104">Der Listener ist für die Lebensdauer des <xref:System.Net.HttpListener>-Objekts aktiv und wird in der Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="51ad9-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="51ad9-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="51ad9-105">HTTP.SYS</span></span>  
 <span data-ttu-id="51ad9-106">Die <xref:System.Net.HttpListener>-Klasse basiert auf HTTP.sys; hierbei handelt es sich um den Kernelmoduslistener, der den gesamten HTTP-Verkehr für Windows verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="51ad9-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="51ad9-107">HTTP.sys bietet Verbindungsverwaltung, Bandbreiteneinschränkung und Webserverprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="51ad9-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="51ad9-108">Verwenden Sie das Tool "`HttpCfg.exe`", um SSL-Zertifikate hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="51ad9-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="51ad9-109">Weitere Informationen finden Sie in der Dokumentation zum Tool [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) in der [Server](http://go.microsoft.com/fwlink/?LinkID=178285)-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="51ad9-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ad9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51ad9-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="51ad9-111">HTTP-Server</span><span class="sxs-lookup"><span data-stu-id="51ad9-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="51ad9-112">Security Enhancements in Internet Information (Sicherheitsverbesserungen bei Internetinformationen)</span><span class="sxs-lookup"><span data-stu-id="51ad9-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="51ad9-113">Beispiel zur HttpListener ASPX-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="51ad9-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="51ad9-114">Beispiel zur HttpListener-Technologie</span><span class="sxs-lookup"><span data-stu-id="51ad9-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="51ad9-115">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="51ad9-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
