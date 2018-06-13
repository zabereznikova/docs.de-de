---
title: WCF und WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: ac888db14ebd21c4aed2f717c1f71bed310b8388
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498526"
---
# <a name="wcf-and-websockets"></a><span data-ttu-id="ec502-102">WCF und WebSockets</span><span class="sxs-lookup"><span data-stu-id="ec502-102">WCF and WebSockets</span></span>
<span data-ttu-id="ec502-103">Mit .NET Framework 4.5 wird Unterstützung für WebSockets in Windows Communication Foundation eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ec502-103">The .NET Framework 4.5 introduces support for WebSockets in Windows Communication Foundation.</span></span>  <span data-ttu-id="ec502-104">WebSockets ist eine effiziente standardbasierte Technologie, die die bidirektionale Kommunikation über die HTTP-Standardports 80 und 443 ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ec502-104">WebSockets is an efficient, standards-based technology that enables bidirectional communication over the standard HTTP ports 80 and 443.</span></span> <span data-ttu-id="ec502-105">Die Verwendung der standardmäßigen HTTP-Ports ermöglicht WebSockets die webbasierte Kommunikation über Vermittler.</span><span class="sxs-lookup"><span data-stu-id="ec502-105">The use of the standard HTTP ports allow WebSockets to communicate across the web through intermediaries.</span></span>  <span data-ttu-id="ec502-106">Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Standardbindungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec502-106">Two new standard bindings have been added to support communication over a WebSocket transport.</span></span> <span data-ttu-id="ec502-107"><xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>.</span><span class="sxs-lookup"><span data-stu-id="ec502-107"><xref:System.ServiceModel.NetHttpBinding> and <xref:System.ServiceModel.NetHttpsBinding>.</span></span> <span data-ttu-id="ec502-108">WebSockets-spezifische Einstellungen können konfiguriert werden, auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement> durch den Zugriff auf die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ec502-108">WebSockets-specific settings can be configured on the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> by accessing the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> property.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ec502-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ec502-109">In This Section</span></span>  
 [<span data-ttu-id="ec502-110">Verwenden von NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ec502-110">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <span data-ttu-id="ec502-111">Erläutert die <xref:System.ServiceModel.NetHttpBinding> und deren Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ec502-111">Discusses the <xref:System.ServiceModel.NetHttpBinding> and how to configure it.</span></span>  
  
 [<span data-ttu-id="ec502-112">Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert</span><span class="sxs-lookup"><span data-stu-id="ec502-112">How to: Create a WCF Service that Communicates over WebSockets</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 <span data-ttu-id="ec502-113">Beschreibt, wie ein WCF-Dienst erstellt wird, der über WebSockets kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="ec502-113">Describes how to create a WCF service that communicates over Websockets.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ec502-114">Referenz</span><span class="sxs-lookup"><span data-stu-id="ec502-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ec502-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ec502-115">Related Sections</span></span>
