---
title: NetworkInformation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3a72eb23c7ad053d6f0fe505668cd037e65d582b
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="networkinformation"></a>NetworkInformation
Mit dem Namespace <xref:System.Net.NetworkInformation> können Sie Informationen über Netzwerkereignisse, Änderungen, Statistiken sowie Eigenschaften sammeln. Sie können auch bestimmen, ob ein remoter Host mithilfe der <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName>-Klasse erreichbar ist.  
  
## <a name="network-availability-and-events"></a>Netzwerkverfügbarkeit und Ereignisse  
 Mithilfe der <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName>-Klasse können Sie bestimmen, ob sich die Netzwerkadresse oder die Verfügbarkeit geändert hat. Um diese Klasse verwenden zu können, erstellen Sie einen Ereignishandler, um die Änderung zu verarbeiten und um ihr einen <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> oder <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> zuzuordnen. Weitere Informationen finden Sie unter [Vorgehensweise: Erkennen von Netzwerkverfügbarkeit und Adressänderungen](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Netzwerkstatistiken und -eigenschaften  
 Sie können Netzwerkstatistiken und -eigenschaften auf einer Schnittstelle oder auf Protokollbasis sammeln. Die Klassen <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> und <xref:System.Net.NetworkInformation.PhysicalAddress> halten Informationen über eine bestimmte Netzwerkschnittstelle bereit, während die Klassen <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> und <xref:System.Net.NetworkInformation.UdpStatistics> Informationen über Pakete der Ebene 3 und der Ebene 4 bereitstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Schnittstellen- und Protokollinformationen](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Bestimmen, ob ein Remotehost erreichbar ist  
 Sie können die <xref:System.Net.NetworkInformation.Ping>-Klasse verwenden, um zu bestimmen, ob ein Remotehost verfügbar, auf dem Netzwerk oder erreichbar ist. Weitere Informationen finden Sie unter [Vorgehensweise: Pingen eines Hosts](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Netzwerk-Informationstechnologie-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [NetStat Tool Technologie-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [FTP-Client-Technologie-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179565)

