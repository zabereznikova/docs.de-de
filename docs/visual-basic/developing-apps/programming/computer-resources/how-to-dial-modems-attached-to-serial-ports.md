---
title: "Vorgehensweise: Anwählen von Modems an seriellen Anschlüssen in Visual Basic | Microsoft-Dokumentation"
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
- modems, dialing
- serial ports, dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 4916c7bc3fc60b25dba8386294f11d07346cb358
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a>Gewusst wie: Wählen mit Modems an seriellen Anschlüssen in Visual Basic
Dieses Thema beschreibt, wie Sie `My.Computer.Ports` nutzen, um ein Modem in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] anzuwählen.  
  
 In der Regel ist das Modem mit einem der seriellen Anschlüsse am Computer verbunden. Damit die Anwendung mit dem Modem kommunizieren kann, muss sie Befehle an den entsprechenden seriellen Anschluss senden.  
  
### <a name="to-dial-a-modem"></a>So wählen Sie ein Modem an  
  
1.  Ermitteln Sie den seriellen Anschluss, mit dem das Modem verbunden ist. In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.  
  
2.  Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Anschluss zu erhalten. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird. Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]  
  
3.  Legen Sie die `DtrEnable`-Eigenschaft fest, um anzugeben, dass der Computer für eine eingehende Übertragung vom Modem empfangsbereit ist.  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]  
  
4.  Senden Sie den Anwählbefehl und die Telefonnummer mithilfe der <xref:System.IO.Ports.SerialPort.Write%2A>-Methode über den seriellen Anschluss an das Modem.  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert einen Verweis auf den <xref:System?displayProperty=fullName>-Namespace.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist. Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird. Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 In diesem Beispiel trennt die Anwendung den seriellen Anschluss, nachdem sie das Modem anwählt. In der Praxis ist es erwünscht, dass Daten von und an das Modem übertragen werden. Weitere Informationen finden Sie unter [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Vorgehensweise: Senden von Zeichenfolgen zu seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)   
 [Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
