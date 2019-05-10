---
title: 'Vorgehensweise: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 378410977c31a446b34bf907dfd438a2a799c84a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662295"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>Vorgehensweise: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden. Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten. In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.  
  
 Im folgenden Verfahren wird die <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften für ein Menüelement aus dem Dropdownbereich des übergeordneten MDI-Menüs zu entfernen. Schließen die untergeordneten MDI-Fensters wird die entfernte Menüelemente übergeordneten MDI-Menüs wiederhergestellt.  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>So entfernen Sie ein MenuStrip in ein MDI-Dropdownmenü  
  
1. Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2. Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest  
  
3. Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `&File` fest.  
  
4. Fügen Sie drei Untermenüelemente an die `&File` Menü, und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Open`, `&Import from`, und `E&xit`.  
  
5. Fügen Sie zwei Untermenüelemente hinzu. die `&Import from` Untermenü, und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Word` und `&Excel`.  
  
6. Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
7. Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&File` fest.  
  
8. Hinzufügen eine `&Import from` Untermenüelement, das auf die `&File` im Menü `Form2`, und fügen eine `&Word` Untermenüelement, das auf die `&File` im Menü.  
  
9. Legen Sie die <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften der `Form2` Menüelemente, wie in der folgenden Tabelle gezeigt.  
  
    |Menüelement Form2|MergeAction-Wert|MergeIndex-Wert|  
    |---------------------|-----------------------|----------------------|  
    |Datei|MatchOnly|-1|  
    |Importieren aus|MatchOnly|-1|  
    |Word|Remove|-1|  
  
10. In `Form1`, erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.Control.Click> Ereignis die `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Fügen Sie Code wie im folgenden Codebeispiel wird zu erstellende und anzuzeigende neue Instanzen von innerhalb des ereignishandlers `Form2` als untergeordnete MDI-Fenster von `Form1`:  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. Fügen Sie Code, der dem folgenden Codebeispiel ähnelt, in `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> ein, um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
- Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Vorgehensweise: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
