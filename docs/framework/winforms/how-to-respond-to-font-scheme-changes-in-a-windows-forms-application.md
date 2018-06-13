---
title: 'Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 455609ea602f450803718f5be34618b087560d21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539451"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Gewusst wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung
In den Windows-Betriebssystemen kann ein Benutzer die systemweite schriftarteinstellungen, um die Standardschriftart angezeigt vergrößern oder verkleinern möchten ändern. Das Ändern dieser schriftarteinstellungen ist wichtig für Benutzer, die Sehbehinderte sind, und größeren Typ zum Lesen des Texts auf ihre Bildschirme benötigen. Sie können anpassen, dass Ihre Windows Forms-Anwendung, um diese Änderungen, die durch erhöhen oder verringern die Größe des Formulars und alle enthaltenen Text bei jeder Änderung des Schriftartenschemas zu reagieren. Wenn das Formular, um dynamisch Änderungen in Schriftgrade Ihren Bedürfnissen gerecht zu werden soll, können Sie Code zum Formular hinzufügen.  
  
 In der Regel ist die Standardschriftart von Windows Forms verwendet die zurückgegebene Schriftart der <xref:Microsoft.Win32> Namespace beim Aufrufen von `GetStockObject(DEFAULT_GUI_FONT)`. Die Schriftart, die durch diesen Aufruf zurückgegeben wird nur geändert, wenn sich die Bildschirmauflösung ändert. Wie in der folgenden Prozedur dargestellt, muss den Code ändern Standardschriftart <xref:System.Drawing.SystemFonts.IconTitleFont%2A> Reaktion auf Änderungen an der Größe der Schriftart.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Verwenden Sie die Remotedesktop-Schriftart und reagieren auf Änderungen des Schriftartenschemas  
  
1.  Erstellen Sie das Formular, und fügen Sie die gewünschten Steuerelemente hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer Windows Forms-Anwendung über die Befehlszeile](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) und [Steuerelemente für Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Hinzufügen eines Verweises auf die <xref:Microsoft.Win32> Namespace in Ihrem Code.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Fügen Sie den folgenden Code an den Konstruktor des Formulars erforderlichen Ereignishandler verknüpft und die Standardschriftart verwendet für das Formular zu ändern.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Implementieren Sie einen Handler für die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> Ereignis, das bewirkt, das Formular dass, um automatisch skalieren, wenn die <xref:Microsoft.Win32.UserPreferenceCategory.Window> Kategorie Änderungen.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Implementieren Sie schließlich einen Handler für die <xref:System.Windows.Forms.Form.FormClosing> Ereignis, das trennt die <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> -Ereignishandler.  
  
> [!IMPORTANT]
>  Dieser Code wird die Anwendung zu Speicherverlust führen.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Kompilieren Sie den Code, und führen Sie diesen aus.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>So ändern manuell die Schriftartenschemas in Windows XP  
  
1.  Während die Windows Forms-Anwendung ausgeführt wird, mit der rechten Maustaste in des Windows-Desktops, und wählen Sie **Eigenschaften** aus dem Kontextmenü.  
  
2.  In der **Anzeigeeigenschaften** (Dialogfeld), klicken Sie auf die **Darstellung** Registerkarte.  
  
3.  Aus der **Schriftgrad** Dropdown-Liste wählen eine andere Schriftgröße.  
  
     Beachten Sie, dass das Formular jetzt reagiert auf zeitänderungen in der desktop Schriftartenschemas ausgeführt. Wenn der Benutzer zwischen ändert **Normal**, **große Schriftarten**, und **Extragroß**, dem Formular die Schriftart und ordnungsgemäß skaliert.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Der Konstruktor in diesem Codebeispiel enthält einen Aufruf von `InitializeComponent`, also definiert, wenn Sie ein neues Windows Forms-Projekt in Visual Studio erstellen. Entfernen Sie diese Codezeile aus, wenn Sie Ihre Anwendung in der Befehlszeile erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [Automatische Skalierung in Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
