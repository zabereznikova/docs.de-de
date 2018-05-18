---
title: 'Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: a00306407cfe880ebc915d74a753109cc9696f6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen in Visual Basic
Dieses Thema beschreibt, wie `My.Computer.Ports` zum Senden von Zeichenfolgen an serielle Ports des Computers in Visual Basic verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sendet eine Zeichenfolge an den seriellen COM1-Anschluss. Möglicherweise müssen Sie auf Ihrem Computer einen anderen seriellen Anschluss verwenden.  
  
 Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird. Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.  
  
 Die <xref:System.IO.Ports.SerialPort.WriteLine%2A>-Methode sendet die Daten an den seriellen Anschluss.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet; für eine erhöhte Flexibilität sollte der Code es dem Benutzer ermöglichen, den gewünschten seriellen Anschluss aus einer Liste von seriellen Anschlüssen auszuwählen. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird. Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [Gewusst wie: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
