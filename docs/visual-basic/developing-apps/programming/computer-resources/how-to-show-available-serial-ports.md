---
title: 'Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: c7e5f797c1d098a3b2d01745b949ed50375ea7e8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345576"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen in Visual Basic

In diesem Thema wird beschrieben, wie `My.Computer.Ports` zum Anzeigen der verfügbaren seriellen Ports eines Computers in Visual Basic verwendet wird.  
  
 Damit ein Benutzer auswählen kann, welcher Anschluss verwendet werden soll, werden die Namen der seriellen Anschlüsse in ein <xref:System.Windows.Forms.ListBox>-Steuerelement platziert.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel werden alle Zeichenfolgen durchlaufen, die die `My.Computer.Ports.SerialPortNames`-Eigenschaft zurückgibt. Diese Zeichenfolgen sind die Namen der auf dem Computer verfügbaren Anschlüsse.  
  
 Üblicherweise wählt ein Benutzer aus der Liste der verfügbaren Anschlüsse aus, welchen seriellen Anschluss die Anwendung verwenden soll. In diesem Beispiel werden die Namen der seriellen Anschlüsse in einem <xref:System.Windows.Forms.ListBox>-Steuerelement gespeichert. Weitere Informationen finden Sie unter [ListBox-Steuerelement](../../../../framework/winforms/controls/listbox-control-windows-forms.md).  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein Projektverweis auf „System.Windows.Forms.dll“.  
  
- Zugriff auf die Member des <xref:System.Windows.Forms>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
- Dass Ihr Formular ein <xref:System.Windows.Forms.ListBox>-Steuerelement mit dem Namen `ListBox1` hat.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Sie müssen nicht das <xref:System.Windows.Forms.ListBox>-Steuerelement verwenden, um die Namen der verfügbaren seriellen Anschlüsse anzuzeigen. Stattdessen können Sie <xref:System.Windows.Forms.ComboBox> oder ein anderes Steuerelement verwenden. Wenn die Anwendung keine Antwort des Benutzers erfordert, können Sie ein <xref:System.Windows.Forms.TextBox>-Steuerungselement verwenden, um die Informationen anzuzeigen.  
  
> [!NOTE]
> Die von `My.Computer.Ports.SerialPortNames` zurückgegebenen Anschlussnamen sind möglicherweise unter Windows 98 unzulässig. Verwenden Sie die Ausnahmebehandlung, um Anwendungsfehler zu verhindern – z.B die `Try...Catch...Finally`-Anweisung oder die `Using`-Anweisung beim Öffnen der Anschlüsse mithilfe der Anschlussnamen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
