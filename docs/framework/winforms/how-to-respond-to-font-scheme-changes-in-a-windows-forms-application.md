---
title: 'Vorgehensweise: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 6aad851770fb886de5d5c00b544ac6eac2857e42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339046"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Vorgehensweise: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung
In der Windows-Betriebssystemen kann ein Benutzer die systemweite schriftarteinstellungen, um die Standardschriftart angezeigt werden, vergrößert oder verkleinert werden ändern. Ändern der schriftarteinstellungen ist wichtig für Benutzer, die sehbehinderte und größeren Typ zum Lesen des Texts auf ihren Bildschirmen erfordern. Sie können Ihre Windows Forms-Anwendung, um diese Änderungen zu reagieren durch erhöhen oder verringern die Größe des Formulars und alle darin enthaltenen Text ein, wenn des Schriftartenschemas Änderungen anpassen. Wenn Sie das Formular aus, um Änderungen in Schriftgrade Ihren Bedürfnissen entsprechend dynamisch zu berücksichtigen möchten, können Sie Code zum Formular hinzufügen.  
  
 In der Regel ist die Standardschriftart, die von Windows Forms verwendet die Schriftart, die zurückgegeben werden, indem die <xref:Microsoft.Win32> Namespace beim Aufrufen von `GetStockObject(DEFAULT_GUI_FONT)`. Die Schriftart, die durch diesen Aufruf zurückgegeben wird nur geändert, wenn die Bildschirmauflösung ändert. Wie im folgenden Verfahren dargestellt wird, muss den Code der Standardschriftart ändern <xref:System.Drawing.SystemFonts.IconTitleFont%2A> Reaktion auf Änderungen in der Schriftgrad.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Verwenden Sie die desktop-Schriftart und reagieren auf Änderungen des Schriftartenschemas  
  
1. Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eine Windows Forms-Anwendung über die Befehlszeile](how-to-create-a-windows-forms-application-from-the-command-line.md) und [in Windows Forms-Steuerelemente](./controls/controls-to-use-on-windows-forms.md).  
  
2. Hinzufügen eines Verweises auf die <xref:Microsoft.Win32> Namespace in Ihrem Code.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. Fügen Sie den folgenden Code, an den Konstruktor des Formulars, um die erforderlichen Ereignishandler einzubinden und so ändern Sie die Standardschriftart für das Formular verwendet.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. Implementieren Sie einen Handler für die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignis, das bewirkt, das Formular dass für die automatische Skalierung bei der <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie Änderungen.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. Abschließend implementieren Sie einen Handler für die <xref:System.Windows.Forms.Form.FormClosing> -Ereignis, das trennt die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignishandler.  
  
     > [!IMPORTANT]
     > Wird dieser Code eingefügt wird Ihre Anwendung für die Speicherverluste verursachen.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. Kompilieren Sie den Code, und führen Sie diesen aus.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>So ändern Sie manuell das Schriftartschema in Windows XP  
  
1. Während die Windows Forms-Anwendung ausgeführt wird, mit der rechten Maustaste in des Windows-Desktops, und wählen Sie **Eigenschaften** aus dem Kontextmenü.  
  
2. In der **Anzeigeeigenschaften** Dialogfeld klicken Sie auf die **Darstellung** Registerkarte.  
  
3. Von der **Schriftgrad** Dropdown-Liste wählen eine andere Schriftgröße.  
  
     Sie werden feststellen, dass das Formular jetzt auf Laufzeit-Änderungen in der desktop Schriftartenschemas reagiert. Wenn der Benutzer ändert zwischen **Normal**, **großen Schriftarten**, und **Extragroß**, das Formular die Schriftart und ordnungsgemäß skaliert werden kann.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Der Konstruktor in diesem Codebeispiel enthält einen Aufruf von `InitializeComponent`, die definiert, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen. Entfernen Sie diese Codezeile aus, wenn Sie Ihre Anwendung in der Befehlszeile erstellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Automatische Skalierung in Windows Forms](automatic-scaling-in-windows-forms.md)
