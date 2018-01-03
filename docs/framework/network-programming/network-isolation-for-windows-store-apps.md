---
title: "Netzwerkisolation für Windows Store-Apps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ba7e480f50d3a339648229f17152eb28b28ec159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="41f4f-102">Netzwerkisolation für Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="41f4f-102">Network Isolation for Windows Store Apps</span></span>
<span data-ttu-id="41f4f-103">Klassen in den Namespaces <xref:System.Net>, <xref:System.Net.Http> und <xref:System.Net.Http.Headers> können verwendet werden, um Windows Store-Apps oder Desktop-Apps zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="41f4f-103">Classes in the <xref:System.Net>,  <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="41f4f-104">Bei Verwendung in einer Windows Store-App sind Klassen in diesen Namespaces von Netzwerkisolation betroffen, als Teil des Anwendungssicherheitsmodells, das von [!INCLUDE[win8](../../../includes/win8-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41f4f-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by the [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="41f4f-105">Die entsprechenden Netzwerkfunktionen müssen im App-Manifest für eine Windows Store-App aktiviert sein, damit das System den Netzwerkzugriff erlaubt.</span><span class="sxs-lookup"><span data-stu-id="41f4f-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="41f4f-106">Prüfliste für die Netzwerkisolation</span><span class="sxs-lookup"><span data-stu-id="41f4f-106">Checklist for Network Isolation</span></span>  
 <span data-ttu-id="41f4f-107">Verwenden Sie diese Prüfliste, um sicherzustellen, dass die Netzwerkisolation für Ihre Windows Store-App konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="41f4f-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1.  <span data-ttu-id="41f4f-108">Bestimmen Sie die Richtung der Netzwerkzugriffsanforderungen, die von der App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="41f4f-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="41f4f-109">Dies können entweder ausgehende, vom Client initiierte Anforderungen sein oder eingehende, unaufgeforderte Anforderungen, oder es könnte möglicherweise eine Kombination aus beiden Netzwerkanforderungstypen sein.</span><span class="sxs-lookup"><span data-stu-id="41f4f-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2.  <span data-ttu-id="41f4f-110">Bestimmen Sie den Typ der Netzwerkressourcen, mit denen diese App kommunizieren wird.</span><span class="sxs-lookup"><span data-stu-id="41f4f-110">Determine the type of network resources that that app will communicate with.</span></span> <span data-ttu-id="41f4f-111">Eine App muss möglicherweise mit vertrauenswürdigen Ressourcen in einem Heimnetzwerk oder einem Arbeitsplatznetzwerk kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="41f4f-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="41f4f-112">Eine App muss möglicherweise mit Ressourcen im Internet kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="41f4f-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="41f4f-113">Eine App benötigt möglicherweise den Zugriff auf beide Netzwerkressourcentypen.</span><span class="sxs-lookup"><span data-stu-id="41f4f-113">An app might need access to both types of network resources.</span></span>  
  
3.  <span data-ttu-id="41f4f-114">Konfigurieren Sie die minimal erforderlichen Netzwerkisolationsfunktionen im App-Manifest.</span><span class="sxs-lookup"><span data-stu-id="41f4f-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4.  <span data-ttu-id="41f4f-115">Stellen Sie Ihre App bereit, und führen Sie diese zu Testzwecken aus, indem Sie die Netzwerkisolationstools für die Problembehandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41f4f-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
 <span data-ttu-id="41f4f-116">Weitere ausführliche Informationen zum Konfigurieren der Netzwerkfunktionen und der Isolationstools zur Problembehandlung im Rahmen der Netzwerkisolation finden Sie unter [How to configure network isolation capabilities (Vorgehensweise beim Konfigurieren von Netzwerkisolierungseigenschaften)](http://go.microsoft.com/fwlink/?LinkID=228265) in der [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Entwicklerdokumentation.</span><span class="sxs-lookup"><span data-stu-id="41f4f-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](http://go.microsoft.com/fwlink/?LinkID=228265) in the [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] developer documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f4f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41f4f-117">See Also</span></span>  
 [<span data-ttu-id="41f4f-118">Herstellen einer Verbindung mit einem Webdienst</span><span class="sxs-lookup"><span data-stu-id="41f4f-118">Connecting to a web service</span></span>](http://go.microsoft.com/fwlink/?LinkID=245696)  
 [<span data-ttu-id="41f4f-119">Richtlinien und die Prüfliste für die Netzwerkisolation</span><span class="sxs-lookup"><span data-stu-id="41f4f-119">Guidelines and checklist for network isolation</span></span>](http://go.microsoft.com/fwlink/?LinkID=228265)  
 [<span data-ttu-id="41f4f-120">Schnellstart: Verbindungsherstellung mithilfe einer "HttpClient"</span><span class="sxs-lookup"><span data-stu-id="41f4f-120">Quickstart: Connecting using HttpClient</span></span>](http://go.microsoft.com/fwlink/?LinkId=245697)  
 [<span data-ttu-id="41f4f-121">Gewusst wie: Verwenden Sie den Handler für "HttpClient"</span><span class="sxs-lookup"><span data-stu-id="41f4f-121">How to use HttpClient handlers</span></span>](http://go.microsoft.com/fwlink/?LinkId=245699)  
 [<span data-ttu-id="41f4f-122">Sichere Verbindungen für "HttpClient"</span><span class="sxs-lookup"><span data-stu-id="41f4f-122">How to secure HttpClient connections</span></span>](http://go.microsoft.com/fwlink/?LinkId=245698)  
 [<span data-ttu-id="41f4f-123">HttpClient Sample (HttpClient-Beispiel)</span><span class="sxs-lookup"><span data-stu-id="41f4f-123">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)
