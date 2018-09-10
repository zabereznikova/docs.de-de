---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 88b39b5ae01ec5b22044dde82ba0f802c1a50ca9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526751"
---
# <a name="networkinformation"></a>NetworkInformation
Mit dem Namespace <xref:System.Net.NetworkInformation> können Sie Informationen über Netzwerkereignisse, Änderungen, Statistiken sowie Eigenschaften sammeln. Sie können auch bestimmen, ob ein remoter Host mithilfe der <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>-Klasse erreichbar ist.  
  
## <a name="network-availability-and-events"></a>Netzwerkverfügbarkeit und Ereignisse  
 Mithilfe der <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType>-Klasse können Sie bestimmen, ob sich die Netzwerkadresse oder die Verfügbarkeit geändert hat. Um diese Klasse verwenden zu können, erstellen Sie einen Ereignishandler, um die Änderung zu verarbeiten und um ihr einen <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> oder <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> zuzuordnen. Weitere Informationen finden Sie unter [Vorgehensweise: Erkennen von Netzwerkverfügbarkeit und Adressänderungen](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Netzwerkstatistiken und -eigenschaften  
 Sie können Netzwerkstatistiken und -eigenschaften auf einer Schnittstelle oder auf Protokollbasis sammeln. Die Klassen <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> und <xref:System.Net.NetworkInformation.PhysicalAddress> halten Informationen über eine bestimmte Netzwerkschnittstelle bereit, während die Klassen <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> und <xref:System.Net.NetworkInformation.UdpStatistics> Informationen über Pakete der Ebene 3 und der Ebene 4 bereitstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Schnittstellen- und Protokollinformationen](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Bestimmen, ob ein Remotehost erreichbar ist  
 Sie können die <xref:System.Net.NetworkInformation.Ping>-Klasse verwenden, um zu bestimmen, ob ein Remotehost verfügbar, auf dem Netzwerk oder erreichbar ist. Weitere Informationen finden Sie unter [Vorgehensweise: Pingen eines Hosts](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Beispiel zur Netzwerk-Informationstechnologie](https://go.microsoft.com/fwlink/?LinkID=179564)  
 [Beispiel zur Technologie des NetStat-Tools](https://go.microsoft.com/fwlink/?LinkID=179562)  
 [Beispiel für die Technologie eines Ping-Clients](https://go.microsoft.com/fwlink/?LinkID=179565)
