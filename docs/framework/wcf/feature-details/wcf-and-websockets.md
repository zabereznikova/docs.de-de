---
title: WCF und WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768731"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="25d65-102">WCF und WebSockets</span><span class="sxs-lookup"><span data-stu-id="25d65-102">WCF and WebSockets</span></span>
<span data-ttu-id="25d65-103">Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="25d65-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="25d65-104">WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP-Standardports 80 und 443 ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="25d65-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="25d65-105">Die Verwendung der standardmäßigen HTTP-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.</span><span class="sxs-lookup"><span data-stu-id="25d65-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="25d65-106">Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="25d65-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="25d65-107"><xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="25d65-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="25d65-108">WebSockets-spezifische Einstellungen können konfiguriert werden, auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement> durch den Zugriff auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="25d65-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="25d65-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="25d65-109">In This Section</span></span>  
 [<span data-ttu-id="25d65-110">Verwenden von NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="25d65-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="25d65-111">Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="25d65-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="25d65-112">Vorgehensweise: Erstellen eines WCF-Diensts, das über WebSockets kommuniziert</span><span class="sxs-lookup"><span data-stu-id="25d65-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="25d65-113">Beschreibt, wie ein WCF-Dienst erstellt wird, der über WebSockets kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="25d65-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="25d65-114">Referenz</span><span class="sxs-lookup"><span data-stu-id="25d65-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="25d65-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="25d65-115">Related Sections</span></span>
