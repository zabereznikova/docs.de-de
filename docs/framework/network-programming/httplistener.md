---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68c69de839ccbd51de9f0bfa74be018f877f7731
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085894"
---
# <a name="httplistener"></a><span data-ttu-id="feb34-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="feb34-102">HttpListener</span></span>
<span data-ttu-id="feb34-103">Die <xref:System.Net.HttpListener>-Klasse stellt einen programmgesteuerten HTTP-Protokolllistener bereit.</span><span class="sxs-lookup"><span data-stu-id="feb34-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="feb34-104">Der Listener ist für die Lebensdauer des <xref:System.Net.HttpListener>-Objekts aktiv und wird in der Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="feb34-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="feb34-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="feb34-105">HTTP.SYS</span></span>  
 <span data-ttu-id="feb34-106">Die <xref:System.Net.HttpListener>-Klasse basiert auf HTTP.sys; hierbei handelt es sich um den Kernelmoduslistener, der den gesamten HTTP-Verkehr für Windows verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="feb34-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="feb34-107">HTTP.sys bietet Verbindungsverwaltung, Bandbreiteneinschränkung und Webserverprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="feb34-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="feb34-108">Verwenden Sie das Tool "`HttpCfg.exe`", um SSL-Zertifikate hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="feb34-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="feb34-109">Weitere Informationen finden Sie in der Dokumentation zum Tool [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) in der [Server](https://go.microsoft.com/fwlink/?LinkID=178285)-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="feb34-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb34-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feb34-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="feb34-111">HTTP-Server</span><span class="sxs-lookup"><span data-stu-id="feb34-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="feb34-112">Security Enhancements in Internet Information (Sicherheitsverbesserungen bei Internetinformationen)</span><span class="sxs-lookup"><span data-stu-id="feb34-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="feb34-113">Beispiel zur HttpListener ASPX-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="feb34-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="feb34-114">Beispiel zur HttpListener-Technologie</span><span class="sxs-lookup"><span data-stu-id="feb34-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="feb34-115">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="feb34-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
