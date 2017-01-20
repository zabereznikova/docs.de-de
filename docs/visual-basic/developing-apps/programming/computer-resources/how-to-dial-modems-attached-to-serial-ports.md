---
title: "How to: Dial Modems Attached to Serial Ports in Visual Basic | Microsoft Docs"
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
  - "modems, dialing"
  - "serial ports, dialing"
  - "My.Computer.Ports object"
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Dial Modems Attached to Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] mit `My.Computer.Ports` einen Wählvorgang mit einem Modem ausführen können.  
  
 In der Regel ist das Modem an einen der seriellen Anschlüsse am Computer angeschlossen.  Für die Kommunikation mit dem Modem muss die Anwendung Befehle an den entsprechenden seriellen Anschluss senden.  
  
### So wählen Sie mit einem Modem  
  
1.  Stellen Sie fest, mit welchem seriellen Anschluss das Modem verbunden ist.  In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.  
  
2.  Verwenden Sie die `My.Computer.Ports.OpenSerialPort`\-Methode, um einen Verweis auf den Anschluss abzurufen.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Der `Using`\-Block ermöglicht der Anwendung, den seriellen Anschluss auch dann zu schließen, wenn dies eine Ausnahme generiert.  Code, der den seriellen Anschluss konfiguriert, sollte vollständig innerhalb dieses Blocks oder eines `Try...Catch...Finally`\-Blocks stehen.  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/VbVbalrMyComputer/Class2.vb#28)]  
  
3.  Geben Sie mit der `DtrEnable`\-Eigenschaft an, dass der Computer bereit für eingehende Übertragungen vom Modem ist.  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/VbVbalrMyComputer/Class2.vb#29)]  
  
4.  Senden Sie den Wählbefehl und die Telefonnummer mithilfe der <xref:System.IO.Ports.SerialPort.Write%2A>\-Methode über den seriellen Anschluss an das Modem.  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/VbVbalrMyComputer/Class2.vb#30)]  
  
## Beispiel  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/VbVbalrMyComputer/Class2.vb#27)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Connectivity and Networking**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Kompilieren des Codes  
 Für das Beispiel wird ein Verweis auf den <xref:System?displayProperty=fullName>\-Namespace benötigt.  
  
## Robuste Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.  Es empfiehlt sich, dem Benutzer die Möglichkeit zur Auswahl des gewünschten Anschlusses aus einer Liste freier Anschlüsse zu geben.  Weitere Informationen finden Sie unter [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 In diesem Beispiel wird mithilfe eines `Using`\-Blocks sichergestellt, dass die Anwendung den seriellen Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird.  Weitere Informationen finden Sie unter [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 In diesem Beispiel trennt die Anwendung nach dem Anwählen des Modems die Verbindung zum seriellen Anschluss.  In einer echten Anwendung würden zusätzlich Daten zum und vom Modem übertragen werden.  Weitere Informationen finden Sie unter [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)