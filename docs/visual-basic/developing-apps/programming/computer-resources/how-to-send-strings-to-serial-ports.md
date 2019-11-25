---
title: 'Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: b2051451142a7818a3b7d1bc564c5ae36b2579fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345587"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse in Visual Basic

Dieses Thema beschreibt, wie `My.Computer.Ports` zum Senden von Zeichenfolgen an serielle Ports des Computers in Visual Basic verwendet wird.  
  
## <a name="example"></a>Beispiel  

 Dieses Beispiel sendet eine Zeichenfolge an den seriellen COM1-Anschluss. Möglicherweise müssen Sie auf Ihrem Computer einen anderen seriellen Anschluss verwenden.  
  
 Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Der `Using`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird. Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block oder in einem `Try...Catch...Finally`-Block angezeigt werden.  
  
 Die <xref:System.IO.Ports.SerialPort.WriteLine%2A>-Methode sendet die Daten an den seriellen Anschluss.  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet; für eine erhöhte Flexibilität sollte der Code es dem Benutzer ermöglichen, den gewünschten seriellen Anschluss aus einer Liste von seriellen Anschlüssen auszuwählen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Dieses Beispiel verwendet einen `Using`-Block, um sicherzustellen, dass die Anwendung den Anschluss auch dann schließt, wenn eine Ausnahme ausgelöst wird. Weitere Informationen finden Sie unter [using-Anweisung](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
