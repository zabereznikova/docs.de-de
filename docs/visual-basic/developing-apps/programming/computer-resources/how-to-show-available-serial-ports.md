---
title: 'Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: b19bdd56311ab7029fb224256d138a0dc0dd8ddc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557345"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Gewusst wie: Anzeigen von verfügbaren seriellen Anschlüssen in Visual Basic

In diesem Thema wird beschrieben, wie `My.Computer.Ports` zum Anzeigen der verfügbaren seriellen Ports eines Computers in Visual Basic verwendet wird.  
  
 Damit ein Benutzer auswählen kann, welcher Anschluss verwendet werden soll, werden die Namen der seriellen Anschlüsse in ein <xref:System.Windows.Forms.ListBox>-Steuerelement platziert.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel werden alle Zeichenfolgen durchlaufen, die die `My.Computer.Ports.SerialPortNames`-Eigenschaft zurückgibt. Diese Zeichenfolgen sind die Namen der auf dem Computer verfügbaren Anschlüsse.  
  
 Üblicherweise wählt ein Benutzer aus der Liste der verfügbaren Anschlüsse aus, welchen seriellen Anschluss die Anwendung verwenden soll. In diesem Beispiel werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>-Steuerelement gespeichert. Weitere Informationen finden Sie unter [ListBox-Steuerelement](/dotnet/desktop/winforms/controls/listbox-control-windows-forms).  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Dieses Beispiel erfordert Folgendes:  
  
- Ein Projektverweis auf „System.Windows.Forms.dll“.  
  
- Zugriff auf die Member des <xref:System.Windows.Forms>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
- Dass Ihr Formular ein <xref:System.Windows.Forms.ListBox>-Steuerelement mit dem Namen `ListBox1` hat.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Sie müssen nicht das <xref:System.Windows.Forms.ListBox>-Steuerelement verwenden, um die Namen der verfügbaren seriellen Anschlüsse anzuzeigen. Stattdessen können Sie <xref:System.Windows.Forms.ComboBox> oder ein anderes Steuerelement verwenden. Wenn die Anwendung keine Antwort des Benutzers erfordert, können Sie ein <xref:System.Windows.Forms.TextBox>-Steuerungselement verwenden, um die Informationen anzuzeigen.  
  
> [!NOTE]
> Die von `My.Computer.Ports.SerialPortNames` zurückgegebenen Anschlussnamen sind möglicherweise unter Windows 98 unzulässig. Verwenden Sie die Ausnahmebehandlung, um Anwendungsfehler zu verhindern – z.B die `Try...Catch...Finally`-Anweisung oder die `Using`-Anweisung beim Öffnen der Anschlüsse mithilfe der Anschlussnamen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Gewusst wie: Wählen mit Modems an seriellen Anschlüssen](how-to-dial-modems-attached-to-serial-ports.md)
- [Gewusst wie: Senden von Zeichenfolgen zu seriellen Anschlüssen](how-to-send-strings-to-serial-ports.md)
- [Gewusst wie: Empfangen von Zeichenfolgen von seriellen Anschlüssen](how-to-receive-strings-from-serial-ports.md)
