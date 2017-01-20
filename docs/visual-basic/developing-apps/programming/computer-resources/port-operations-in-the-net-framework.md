---
title: "Port Operations in the .NET Framework with Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ports, Visual Basic"
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Port Operations in the .NET Framework with Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können über die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassen im <xref:System.IO.Ports?displayProperty=fullName>\-Namespace auf die seriellen Anschlüsse des Computers zugreifen.  Die wichtigste Klasse, <xref:System.IO.Ports.SerialPort>, bietet ein Framework für synchrone und ereignisgesteuerte E\/A\-Vorgänge, Zugriff auf Pin\- und Unterbrechungszustände sowie Zugriff auf die Treibereigenschaften für den seriellen Anschluss.  Diese Klasse kann mit einem <xref:System.IO.Stream>\-Objekt umschlossen werden, das über die <xref:System.IO.Ports.SerialPort.BaseStream%2A>\-Eigenschaft zugänglich ist.  Durch das Umschließen von <xref:System.IO.Ports.SerialPort> mit einem <xref:System.IO.Stream>\-Objekt wird der Zugriff auf den seriellen Anschluss für Klassen ermöglicht, in denen Streams verwendet werden.  Der Namespace enthält verschiedene Enumerationen, die die Steuerung von seriellen Anschlüssen vereinfachen.  
  
 Am einfachsten kann ein <xref:System.IO.Ports.SerialPort>\-Objekt mit der <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>\-Methode erstellt werden.  
  
> [!NOTE]
>  Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassen können nicht für den direkten Zugriff auf andere Anschlussarten verwendet werden, beispielsweise parallele Anschlüsse oder USB\-Anschlüsse.  
  
## Enumerationen  
 In dieser Tabelle werden die wichtigsten Enumerationen für den Zugriff auf den seriellen Anschluss beschrieben:  
  
|||  
|-|-|  
|Enumeration|Beschreibung|  
|<xref:System.IO.Ports.Handshake>|Gibt das Steuerprotokoll an, das beim Aufbau der Kommunikation über den seriellen Anschluss für ein <xref:System.IO.Ports.SerialPort>\-Objekt verwendet wird.|  
|<xref:System.IO.Ports.Parity>|Gibt das Paritätsbit für ein <xref:System.IO.Ports.SerialPort>\-Objekt an.|  
|<xref:System.IO.Ports.SerialData>|Gibt den Typ von Zeichen an, der über das <xref:System.IO.Ports.SerialPort>\-Objekt auf dem seriellen Anschluss empfangen wurde.|  
|<xref:System.IO.Ports.SerialError>|Gibt Fehler an, die für das <xref:System.IO.Ports.SerialPort>\-Objekt auftreten.|  
|<xref:System.IO.Ports.SerialPinChange>|Gibt den Typ von Änderung an, die für das <xref:System.IO.Ports.SerialPort>\-Objekt aufgetreten ist.|  
|<xref:System.IO.Ports.StopBits>|Gibt die Anzahl von Stoppbits an, die für das <xref:System.IO.Ports.SerialPort>\-Objekt verwendet werden.|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)