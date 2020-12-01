---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 550555be7cc95cafebabfd3ac230ced024a9202c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261617"
---
# <a name="networkinformation"></a><span data-ttu-id="91daf-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="91daf-102">NetworkInformation</span></span>

<span data-ttu-id="91daf-103">Mit dem Namespace <xref:System.Net.NetworkInformation> können Sie Informationen über Netzwerkereignisse, Änderungen, Statistiken sowie Eigenschaften sammeln.</span><span class="sxs-lookup"><span data-stu-id="91daf-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="91daf-104">Sie können auch bestimmen, ob ein remoter Host mithilfe der <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>-Klasse erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="91daf-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="91daf-105">Netzwerkverfügbarkeit und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="91daf-105">Network Availability and Events</span></span>  

 <span data-ttu-id="91daf-106">Mithilfe der <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>-Klasse können Sie bestimmen, ob sich die Netzwerkadresse oder die Verfügbarkeit geändert hat.</span><span class="sxs-lookup"><span data-stu-id="91daf-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="91daf-107">Um diese Klasse verwenden zu können, erstellen Sie einen Ereignishandler, um die Änderung zu verarbeiten und um ihr einen <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> oder <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="91daf-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="91daf-108">Weitere Informationen finden Sie unter [Vorgehensweise: Erkennen von Netzwerkverfügbarkeit und Adressänderungen](how-to-detect-network-availability-and-address-changes.md).</span><span class="sxs-lookup"><span data-stu-id="91daf-108">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="91daf-109">Netzwerkstatistiken und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="91daf-109">Network Statistics and Properties</span></span>  

 <span data-ttu-id="91daf-110">Sie können Netzwerkstatistiken und -eigenschaften auf einer Schnittstelle oder auf Protokollbasis sammeln.</span><span class="sxs-lookup"><span data-stu-id="91daf-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="91daf-111">Die Klassen <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> und <xref:System.Net.NetworkInformation.PhysicalAddress> halten Informationen über eine bestimmte Netzwerkschnittstelle bereit, während die Klassen <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> und <xref:System.Net.NetworkInformation.UdpStatistics> Informationen über Pakete der Ebene 3 und der Ebene 4 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="91daf-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="91daf-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Schnittstellen- und Protokollinformationen](how-to-get-interface-and-protocol-information.md).</span><span class="sxs-lookup"><span data-stu-id="91daf-112">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="91daf-113">Bestimmen, ob ein Remotehost erreichbar ist</span><span class="sxs-lookup"><span data-stu-id="91daf-113">Determine if a Remote Host is Reachable</span></span>  

 <span data-ttu-id="91daf-114">Sie können die <xref:System.Net.NetworkInformation.Ping>-Klasse verwenden, um zu bestimmen, ob ein Remotehost verfügbar, auf dem Netzwerk oder erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="91daf-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="91daf-115">Weitere Informationen finden Sie unter [Vorgehensweise: Pingen eines Hosts](how-to-ping-a-host.md).</span><span class="sxs-lookup"><span data-stu-id="91daf-115">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91daf-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91daf-116">See also</span></span>

- [<span data-ttu-id="91daf-117">Network Programming Samples (Beispiele zur Netzwerkprogrammierung)</span><span class="sxs-lookup"><span data-stu-id="91daf-117">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
