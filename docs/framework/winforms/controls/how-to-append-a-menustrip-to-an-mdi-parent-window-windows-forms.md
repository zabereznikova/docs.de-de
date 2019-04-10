---
title: 'Vorgehensweise: Anhängen eines MenuStrip an ein übergeordnetes MDI-Fenster (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], appending
- MDI [Windows Forms], merging menu items
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
ms.openlocfilehash: a335531b090983de4e2b3daccc9f956930cbad6e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298941"
---
# <a name="how-to-append-a-menustrip-to-an-mdi-parent-window-windows-forms"></a>Vorgehensweise: Anhängen eines MenuStrip an ein übergeordnetes MDI-Fenster (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden. Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten. In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.  
  
 Im folgenden Verfahren werden die Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> verwendet, um das Menü des untergeordneten MDI-Fensters an das Menü des übergeordneten MDI-Fensters anzuhängen. Wird das untergeordnete MDI-Fensters geschlossen, wird das angefügte Menü aus dem übergeordneten MDI-Fenster entfernt.  
  
 Siehe auch [Multiple Document Interface (MDI) Applications](../advanced/multiple-document-interface-mdi-applications.md).  
  
### <a name="to-append-a-menu-item-to-an-mdi-parent"></a>So fügen Sie ein Menüelement an ein übergeordnetes MDI-Fenster an  
  
1. Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2. Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest  
  
3. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft der `Form1`<xref:System.Windows.Forms.MenuStrip> zu `false`.  
  
4. Fügen Sie ein Menüelement der obersten Ebene, um die `Form1`<xref:System.Windows.Forms.MenuStrip> und legen Sie seine <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft `&File`.  
  
5. Fügen Sie dem `&File`-Menüelement ein Untermenüelement hinzu, und legen Sie dessen <xref:System.Windows.Forms.Form.Text%2A>-Eigenschaft auf `&Open` fest.  
  
6. Fügen Sie dem Projekt ein Formular, fügen Sie eine <xref:System.Windows.Forms.MenuStrip> auf das Formular, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> Eigenschaft der `Form2`<xref:System.Windows.Forms.MenuStrip> zu `true`.  
  
7. Fügen Sie ein Menüelement der obersten Ebene, um die `Form2`<xref:System.Windows.Forms.MenuStrip> und legen Sie seine <xref:System.Windows.Forms.Form.Text%2A> Eigenschaft `&Special`.  
  
8. Fügen Sie dem `&Special`-Menüelement zwei Untermenüelemente hinzu, und legen Sie deren <xref:System.Windows.Forms.Form.Text%2A>-Eigenschaften auf `Command&1` bzw. `Command&2` fest.  
  
9. Legen Sie die <xref:System.Windows.Forms.MergeAction>-Eigenschaft der Menüelemente `&Special`, `Command&1` und `Command&2` auf <xref:System.Windows.Forms.MergeAction.Append> fest.  
  
10. Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.Control.Click> Ereignis die `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Fügen Sie im Ereignishandler Code ein, der dem folgenden Codebeispiel ähnelt, um neue Instanzen von `Form2` als untergeordnete MDI-Fenster von `Form1` zu erstellen und anzuzeigen.  
  
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
  
12. Fügen Sie Code wie im folgenden Codebeispiel wird in der `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> um den Ereignishandler zu registrieren.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
-   Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.
