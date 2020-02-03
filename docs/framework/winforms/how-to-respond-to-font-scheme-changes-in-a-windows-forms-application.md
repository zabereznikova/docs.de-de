---
title: Reagieren auf Änderungen an Schriftart Schemas in einer Windows Forms-App
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739224"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung
In den Windows-Betriebssystemen kann ein Benutzer die systemweiten Schriftart Einstellungen ändern, damit die Standard Schriftart größer oder kleiner erscheint. Das Ändern dieser Schriftart Einstellungen ist wichtig für Benutzer, die optisch beeinträchtigt sind und einen größeren Typ benötigen, um den Text auf den Bildschirmen zu lesen. Sie können Ihre Windows Forms Anwendung so anpassen, dass Sie auf diese Änderungen reagiert, indem Sie die Größe des Formulars und den gesamten enthaltenen Text erhöhen oder verringern, wenn sich das Schriftart Schema ändert. Wenn Sie möchten, dass das Formular Änderungen an den Schriftgrößen dynamisch unternimmt, können Sie dem Formular Code hinzufügen.  
  
 In der Regel ist die von Windows Forms verwendete Standard Schriftart die Schriftart, die vom <xref:Microsoft.Win32>-Namespace-Aufruf`GetStockObject(DEFAULT_GUI_FONT)`zurückgegeben wird. Die von diesem-Rückruf zurückgegebene Schriftart ändert sich nur, wenn sich die Bildschirmauflösung ändert. Wie im folgenden Verfahren gezeigt, muss der Code die Standard Schriftart in <xref:System.Drawing.SystemFonts.IconTitleFont%2A> ändern, damit auf Änderungen des Schrift Grads geantwortet werden kann.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>So verwenden Sie die Desktop Schriftart und reagieren auf Änderungen am Schriftart Schema  
  
1. Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer Windows Forms Anwendung aus der Befehlszeile](how-to-create-a-windows-forms-application-from-the-command-line.md) und Steuer [Elemente, die auf Windows Forms verwendet werden sollen](./controls/controls-to-use-on-windows-forms.md).  
  
2. Fügen Sie dem Code einen Verweis auf den <xref:Microsoft.Win32>-Namespace hinzu.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. Fügen Sie dem Konstruktor des Formulars den folgenden Code hinzu, um die erforderlichen Ereignishandler zu verbinden und die für das Formular verwendete Standard Schriftart zu ändern.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. Implementieren Sie einen Handler für das <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> Ereignis, das bewirkt, dass das Formular automatisch skaliert wird, wenn die <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie geändert wird.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. Implementieren Sie abschließend einen Handler für das <xref:System.Windows.Forms.Form.FormClosing> Ereignis, das den <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>-Ereignishandler trennt.  
  
     > [!IMPORTANT]
     > Wenn Sie diesen Code nicht einschließen, wird der Arbeitsspeicher von Ihrer Anwendung nicht mehr berücksichtigt.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. Kompilieren Sie den Code, und führen Sie diesen aus.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>So ändern Sie das Schriftart Schema in Windows XP manuell  
  
1. Wenn die Windows Forms-Anwendung ausgeführt wird, klicken Sie mit der rechten Maustaste auf den Windows-Desktop, und wählen Sie im Kontextmenü **Eigenschaften** aus.  
  
2. Klicken Sie im Dialogfeld **Anzeigeeigenschaften** **auf die Register** Karte Darstellung.  
  
3. Wählen Sie im Dropdown-Listenfeld **Schriftart Größe** einen neuen Schrift Grad aus.  
  
     Sie werden feststellen, dass das Formular nun auf Lauf Zeit Änderungen im Desktop Schriftart Schema reagiert. Wenn sich der Benutzer zwischen **normalen**, **großen Schriftarten**und **besonders großen Schriftarten**ändert, ändert sich die Schriftart, und die Skalierung erfolgt ordnungsgemäß.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Der Konstruktor in diesem Codebeispiel enthält einen aufzurufenden `InitializeComponent`, der definiert wird, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen. Entfernen Sie diese Codezeile, wenn Sie die Anwendung in der Befehlszeile entwickeln.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Automatische Skalierung in Windows Forms](automatic-scaling-in-windows-forms.md)
