---
title: "Operationen für serielle Anschlüsse in .NET Framework mit Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 61b91fe5f3bb016bace838b9eeabb1a59190bfe9
ms.lasthandoff: 03/13/2017

---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Operationen für serielle Anschlüsse in .NET Framework mit Visual Basic
Sie können auf die seriellen Anschlüsse Ihres Computers über die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-Klassen im Namespace <xref:System.IO.Ports?displayProperty=fullName> zugreifen. Die wichtigste Klasse, <xref:System.IO.Ports.SerialPort>, bietet ein Framework für synchrone und ereignisgesteuerte E/A-Vorgänge, Zugriff auf Pin- und Unterbrechungszustände sowie Zugriff auf die Treibereigenschaften für den seriellen Anschluss. Er kann in ein <xref:System.IO.Stream>-Objekt eingeschlossen werden, auf das durch die Eigenschaft <xref:System.IO.Ports.SerialPort.BaseStream%2A> zugegriffen werden kann. Auf den seriellen Anschluss kann von Klassen zugegriffen werden, die Streams verwenden, indem <xref:System.IO.Ports.SerialPort> von einem <xref:System.IO.Stream>-Objekt umschlossen wird. Der Namespace enthält Enumerationen, die die Steuerung von seriellen Anschlüssen vereinfacht.  
  
 Der einfachste Weg, ein <xref:System.IO.Ports.SerialPort>-Objekt zu erstellen, ist über die Methode <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
> [!NOTE]
>  Sie können [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]-Klassen nicht verwenden, um direkt auf andere Porttypen wie Parallelanschlüsse, USB-Anschlüsse usw. zuzugreifen.  
  
## <a name="enumerations"></a>Enumerationen  
 Diese Tabelle enthält und beschreibt die wichtigsten Enumerationen für den Zugriff auf einen seriellen Anschluss:  
  
|Enumeration|Beschreibung|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|Gibt das Steuerungsprotokoll an, das beim Herstellen einer Kommunikation eines seriellen Anschlusses für ein <xref:System.IO.Ports.SerialPort>-Objekt verwendet wird.|  
|<xref:System.IO.Ports.Parity>|Gibt das Paritätsbit für ein <xref:System.IO.Ports.SerialPort>-Objekt an.|  
|<xref:System.IO.Ports.SerialData>|Gibt den Zeichentyp an, der an einem seriellen Anschluss des <xref:System.IO.Ports.SerialPort>-Objekts empfangen wurde.|  
|<xref:System.IO.Ports.SerialError>|Gibt die auftretenden Fehler am <xref:System.IO.Ports.SerialPort>-Objekt an.|  
|<xref:System.IO.Ports.SerialPinChange>|Gibt den auftretenden Änderungstyp am <xref:System.IO.Ports.SerialPort>-Objekt an.|  
|<xref:System.IO.Ports.StopBits>|Gibt die Anzahl von Stoppbits an, die das <xref:System.IO.Ports.SerialPort>-Objekt verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Zugreifen auf die Anschlüsse des Computers](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
