---
title: 'Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: febec0a8579d34f8ff59066da5b5aa59c1cce6b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345639"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a>Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen in Visual Basic

In diesem Thema wird beschrieben, wie Sie `My.Computer.Ports` nutzen, um ein Modem in Visual Basic anzuwählen.  
  
 In der Regel ist das Modem mit einem der seriellen Anschlüsse am Computer verbunden. Damit die Anwendung mit dem Modem kommunizieren kann, muss sie Befehle an den entsprechenden seriellen Anschluss senden.  
  
### <a name="to-dial-a-modem"></a>So wählen Sie ein Modem an  
  
1. Ermitteln Sie den seriellen Anschluss, mit dem das Modem verbunden ist. In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist.  
  
2. Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird. Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. Legen Sie die `DtrEnable`-Eigenschaft fest, um anzugeben, dass der Computer für eine eingehende Übertragung vom Modem empfangsbereit ist.  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. Senden Sie den Wählbefehl und die Telefonnummer mithilfe der <xref:System.IO.Ports.SerialPort.Write%2A>-Methode über den seriellen Anschluss an das Modem.  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a>Beispiel  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Für das Beispiel wird ein Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace benötigt.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 In diesem Beispiel wird davon ausgegangen, dass das Modem mit COM1 verbunden ist. Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird. Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 In diesem Beispiel trennt die Anwendung den seriellen Anschluss, nachdem sie das Modem anwählt. In der Praxis ist es erwünscht, dass Daten von und an das Modem übertragen werden. Weitere Informationen finden Sie unter [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
