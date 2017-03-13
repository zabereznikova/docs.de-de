---
title: "How to: Send Strings to Serial Ports in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ports, sending strings to"
  - "strings [Visual Basic], sending to serial ports"
  - "My.Computer.Ports object"
  - "serial ports, sending strings to"
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Send Strings to Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] mit `My.Computer.Ports` Zeichenfolgen an die seriellen Anschlüsse des Computers gesendet werden.  
  
## Beispiel  
 In diesem Beispiel wird eine Zeichenfolge zum seriellen Anschluss COM1 gesendet.  Sie müssen eventuell einen anderen seriellen Anschluss auf dem Computer verwenden.  
  
 Verwenden Sie die `My.Computer.Ports.OpenSerialPort`\-Methode, um einen Verweis auf den Anschluss abzurufen.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Der `Using`\-Block ermöglicht der Anwendung, den seriellen Anschluss auch dann zu schließen, wenn dies eine Ausnahme generiert.  Code, der den seriellen Anschluss konfiguriert, sollte vollständig innerhalb dieses Blocks oder eines `Try...Catch...Finally`\-Blocks stehen.  
  
 Die <xref:System.IO.Ports.SerialPort.WriteLine%2A>\-Methode sendet die Daten an den seriellen Anschluss.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## Kompilieren des Codes  
  
-   In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  
  
## Robuste Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet. Für eine höhere Flexibilität sollte der Code dem Benutzer die Auswahl des gewünschten seriellen Anschlusses aus einer Liste mit verfügbaren Anschlüssen ermöglichen.  Weitere Informationen finden Sie unter [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 In diesem Beispiel wird mithilfe eines `Using`\-Blocks sichergestellt, dass die Anwendung den seriellen Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird.  Weitere Informationen finden Sie unter [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)