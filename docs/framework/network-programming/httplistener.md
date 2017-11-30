---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ca0a22ff1d06485658da75a46bd408a12a3a964c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="httplistener"></a><span data-ttu-id="cdeea-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="cdeea-102">HttpListener</span></span>
<span data-ttu-id="cdeea-103">Die <xref:System.Net.HttpListener>-Klasse stellt einen programmgesteuerten HTTP-Protokolllistener bereit.</span><span class="sxs-lookup"><span data-stu-id="cdeea-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="cdeea-104">Der Listener ist für die Lebensdauer des <xref:System.Net.HttpListener>-Objekts aktiv und wird in der Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cdeea-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="cdeea-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="cdeea-105">HTTP.SYS</span></span>  
 <span data-ttu-id="cdeea-106">Die <xref:System.Net.HttpListener>-Klasse basiert auf HTTP.sys; hierbei handelt es sich um den Kernelmoduslistener, der den gesamten HTTP-Verkehr für Windows verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cdeea-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="cdeea-107">HTTP.sys bietet Verbindungsverwaltung, Bandbreiteneinschränkung und Webserverprotokollierung.</span><span class="sxs-lookup"><span data-stu-id="cdeea-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="cdeea-108">Verwenden Sie das Tool "`HttpCfg.exe`", um SSL-Zertifikate hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cdeea-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="cdeea-109">Weitere Informationen finden Sie in der Dokumentation zum Tool [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) in der [Server](http://go.microsoft.com/fwlink/?LinkID=178285)-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="cdeea-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdeea-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdeea-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="cdeea-111">HTTP-Server</span><span class="sxs-lookup"><span data-stu-id="cdeea-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="cdeea-112">Security Enhancements in Internetinformation</span><span class="sxs-lookup"><span data-stu-id="cdeea-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="cdeea-113">Beispiel zur HttpListener ASPX-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="cdeea-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="cdeea-114">Beispiel zur HttpListener-Technologie</span><span class="sxs-lookup"><span data-stu-id="cdeea-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="cdeea-115">Beispiele zur Netzwerkprogrammierung</span><span class="sxs-lookup"><span data-stu-id="cdeea-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
