---
title: WCF und WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 2ee27eef015ee8c2fbee8360b444343a1c757097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281585"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="ca411-102">WCF und WebSockets</span><span class="sxs-lookup"><span data-stu-id="ca411-102">WCF and WebSockets</span></span>

<span data-ttu-id="ca411-103">Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ca411-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="ca411-104">WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP-Standardports 80 und 443 ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ca411-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="ca411-105">Die Verwendung der standardmäßigen HTTP-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.</span><span class="sxs-lookup"><span data-stu-id="ca411-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="ca411-106">Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ca411-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="ca411-107"><xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="ca411-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="ca411-108">Websockets-spezifische Einstellungen können auf der konfiguriert werden, indem Sie auf <xref:System.ServiceModel.Channels.HttpTransportBindingElement> die- <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ca411-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ca411-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ca411-109">In This Section</span></span>  

 [<span data-ttu-id="ca411-110">Verwenden der NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ca411-110">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)  
 <span data-ttu-id="ca411-111">Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca411-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="ca411-112">Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert</span><span class="sxs-lookup"><span data-stu-id="ca411-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="ca411-113">Beschreibt, wie ein WCF-Dienst erstellt wird, der über WebSockets kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="ca411-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ca411-114">Referenz</span><span class="sxs-lookup"><span data-stu-id="ca411-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ca411-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ca411-115">Related Sections</span></span>
