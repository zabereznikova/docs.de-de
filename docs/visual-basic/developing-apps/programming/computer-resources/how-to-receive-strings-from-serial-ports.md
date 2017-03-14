---
title: "How to: Receive Strings From Serial Ports in Visual Basic | Microsoft Docs"
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
  - "serial ports, retrieving strings"
  - "strings [Visual Basic], retrieving from serial ports"
  - "My.Resources object"
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Receive Strings From Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] mit `My.Computer.Ports` Zeichenfolgen von den seriellen Anschlüssen des Computers empfangen werden.  
  
### So empfangen Sie Zeichenfolgen vom seriellen Anschluss  
  
1.  Initialisieren Sie die Rückgabezeichenfolge.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  Bestimmen Sie, welcher serielle Anschluss die Zeichenfolgen bereitstellen soll.  In diesem Beispiel wird davon ausgegangen, dass dies `COM1` ist.  
  
3.  Verwenden Sie die `My.Computer.Ports.OpenSerialPort`\-Methode, um einen Verweis auf den Anschluss abzurufen.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Der `Try...Catch...Finally`\-Block ermöglicht der Anwendung, den seriellen Anschluss auch dann zu schließen, wenn dies eine Ausnahme generiert.  Code, der den seriellen Anschluss bearbeitet, muss vollständig innerhalb dieses Blocks stehen.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  Erstellen Sie eine `Do`\-Schleife für das Lesen von Textzeilen, bis keine Zeilen mehr verfügbar sind.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  Verwenden Sie die <xref:System.IO.Ports.SerialPort.ReadLine%2A>\-Methode, um die nächste verfügbare Textzeile vom seriellen Anschluss zu lesen.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  Bestimmen Sie mit einer `If`\-Anweisung, ob die <xref:System.IO.Ports.SerialPort.ReadLine%2A>\-Methode `Nothing` zurückgibt \(d. h., dass kein weiterer Text verfügbar ist\).  Wenn `Nothing` zurückgegeben wird, beenden Sie die `Do`\-Schleife.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  Fügen Sie in die `If`\-Anweisung einen `Else`\-Block ein, um den Fall zu behandeln, dass die Zeichenfolge tatsächlich gelesen wird.  Der Block fügt die Zeichenfolge vom seriellen Anschluss an die Rückgabezeichenfolge an.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  Geben Sie die Zeichenfolge zurück.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## Beispiel  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Connectivity and Networking**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Kompilieren des Codes  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  
  
## Robuste Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  Für eine höhere Flexibilität sollte dem Benutzer die Möglichkeit zur Auswahl des gewünschten Anschlusses aus einer Liste freier Anschlüsse gegeben werden.  Weitere Informationen finden Sie unter [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 In diesem Beispiel wird mithilfe eines `Try...Catch...Finally`\-Blocks sichergestellt, dass die Anwendung den seriellen Anschluss schließt und ausgelöste Timeoutausnahmen abfängt.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)