---
title: "NetworkInformation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Netzwerk"
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# NetworkInformation
Der <xref:System.Net.NetworkInformation>\-Namespace ermöglicht es Ihnen, Informationen über Netzwerkereignisse, Änderungen, \-Statistik und Eigenschaften zu erfassen.  Außerdem können Sie bestimmen, ob ein Remotehost erreichbar ist, indem er die <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName>\-Klasse verwendet.  
  
## Netzwerk\-Verfügbarkeit und Ereignisse  
 Die <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName>\-Klasse ermöglicht es Ihnen, zu bestimmen, ob die Netzwerkadresse oder die Verfügbarkeit geändert hat.  Um diese Klasse zu verwenden, erstellen Sie einen Ereignishandler um die Änderung zu verarbeiten, und ordnen Sie ihm den <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> oder <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> zu.  Weitere Informationen finden Sie unter [Gewusst wie: Erkennen von Netzwerkverfügbarkeit und Adressänderungen](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## Netzwerk\- Sie Statistiken und Eigenschaften  
 Sie können die Netzwerkstatistik und \-eigenschaften auf einer Schnittstelle erfassen oder Basis protokollieren.  <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> und <xref:System.Net.NetworkInformation.PhysicalAddress>\-Klassen geben Informationen über eine bestimmte Netzwerkschnittstelle, während <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics><xref:System.Net.NetworkInformation.UdpStatistics>\-Klassen und Informationen über Pakete der Ebene 3 und der Ebene 4 geben.  Weitere Informationen finden Sie unter [Gewusst wie: Abrufen von Schnittstellen\- und Protokollinformationen](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## Bestimmen Sie, wenn ein Remotehost erreichbar ist  
 Sie können die <xref:System.Net.NetworkInformation.Ping>\-Klasse, um zu bestimmen, ob ein Remotehost oben, im Netzwerk befindet, und erreichbar.  Weitere Informationen finden Sie unter [Gewusst wie: Pingen eines Hosts](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## Siehe auch  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Netzwerk\-Informationstechnologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [NetStat\-Tool\-Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [Ping\-Client\-Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179565)