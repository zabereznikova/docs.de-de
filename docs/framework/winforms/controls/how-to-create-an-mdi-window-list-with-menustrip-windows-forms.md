---
title: 'Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: 229afc879be6407340e2fca6c3b2474475bcb5a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611971"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>Vorgehensweise: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)
Verwenden Sie zum Erstellen von Anwendungen, die mehrere Dokumente öffnen, zur gleichen Zeit und kopieren und Einfügen von Inhalt aus einem Dokument in den anderen können die Multiple Document Interface (MDI).  
  
 Dieses Verfahren zeigt, wie Sie eine Liste aller aktiven untergeordneten Formulare in Fenstermenü des übergeordneten Elements zu erstellen.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>Zum Erstellen einer MDI-Fensterliste in einem MenuStrip  
  
1. Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2. Fügen Sie dem Formular eine <xref:System.Windows.Forms.MenuStrip> hinzu.  
  
3. Zwei Menüelemente der obersten Ebene zum Hinzufügen der <xref:System.Windows.Forms.MenuStrip> und legen Sie deren <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften `&File` und `&Window`.  
  
4. Fügen Sie dem `&File`-Menüelement ein Untermenüelement hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&Open` fest.  
  
5. Legen Sie die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Eigenschaft der <xref:System.Windows.Forms.MenuStrip> auf der `&Window` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6. Das Projekt ein Formular hinzu, und fügen Sie das gewünschte Steuerelement hinzu, z. B. einen anderen <xref:System.Windows.Forms.MenuStrip>.  
  
7. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>-Ereignis von `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8. Fügen Sie Code, die etwa wie folgt zu erstellende und anzuzeigende neue Instanzen von innerhalb des ereignishandlers `Form2` als untergeordnete MDI-Fenster von `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. Fügen Sie Code wie den folgenden in das `&New` <xref:System.Windows.Forms.ToolStripMenuItem> um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
- Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip-Steuerelement](menustrip-control-windows-forms.md)
