---
title: 'Gewusst wie: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731009"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>Gewusst wie: Erstellen einer MDI-Fensterliste mithilfe von MenuStrip (Windows Forms)
Verwenden Sie die Multiple Document Interface (MDI), um Anwendungen zu erstellen, die mehrere Dokumente gleichzeitig öffnen und Inhalte aus einem Dokument kopieren und in das andere einfügen können.  
  
 In diesem Verfahren wird gezeigt, wie Sie eine Liste aller aktiven untergeordneten Formulare im Fenstermenü des übergeordneten Fensters erstellen.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>So erstellen Sie eine MDI-Fensterliste in einem MenuStrip  
  
1. Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2. Fügen Sie dem Formular eine <xref:System.Windows.Forms.MenuStrip> hinzu.  
  
3. Fügen Sie dem <xref:System.Windows.Forms.MenuStrip> zwei Menü Elemente der obersten Ebene hinzu, und legen Sie deren <xref:System.Windows.Forms.Control.Text%2A> Eigenschaften auf `&File` und `&Window`fest.  
  
4. Fügen Sie dem `&File`-Menüelement ein Untermenüelement hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&Open` fest.  
  
5. Legen Sie die <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf die `&Window`-<xref:System.Windows.Forms.ToolStripMenuItem>fest.  
  
6. Fügen Sie dem Projekt ein Formular hinzu, und fügen Sie das gewünschte Steuerelement hinzu, z. b. einen anderen <xref:System.Windows.Forms.MenuStrip>.  
  
7. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>-Ereignis von `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8. Fügen Sie im-Ereignishandler Code ähnlich dem folgenden ein, um neue Instanzen von `Form2` als untergeordnete MDI-`Form1`zu erstellen und anzuzeigen.  
  
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
  
9. Platzieren Sie Code wie den folgenden in den `&New`<xref:System.Windows.Forms.ToolStripMenuItem>, um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
- Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip-Steuerelement](menustrip-control-windows-forms.md)
