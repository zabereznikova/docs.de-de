---
title: 'Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736402"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a>Gewusst wie: Einfügen eines MenuStrip in ein MDI-Dropdownmenü (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden. Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten. In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.  
  
 Im folgenden Verfahren werden die Eigenschaften <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> verwendet, um eine Gruppe von Menü Elementen aus dem untergeordneten MDI-Menü in den Dropdown Bereich des übergeordneten MDI-Menüs einzufügen. Durch das Schließen des untergeordneten MDI-Fensters werden die eingefügten Menü Elemente aus der übergeordneten MDI-  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a>So fügen Sie ein MenuStrip in ein MDI-Dropdown Menü ein  
  
1. Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2. Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest  
  
3. Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `&File` fest.  
  
4. Fügen Sie dem Menü Element `&File` drei unter Menü Elemente hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften auf `&Open`, `&Import from`und `E&xit`fest.  
  
5. Fügen Sie dem `&Import from` unter Menü Element zwei unter Menü Elemente hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften auf `&Word` und `&Excel`fest.  
  
6. Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
7. Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&File` fest.  
  
8. Fügen Sie unter Menü Elemente dem Menü `&File` `Form2` in der folgenden Reihenfolge hinzu: eine <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`und eine andere <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Legen Sie die Eigenschaften <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> der `Form2` Menü Elemente fest, wie in der folgenden Tabelle dargestellt.  
  
    |Form2 (Menü Element)|MergeAction-Wert|Mergeingedex-Wert|  
    |---------------------|-----------------------|----------------------|  
    |Datei|Nur MatchOnly|-1|  
    |Trennzeichen|Einfügen|2|  
    |Speichern|Einfügen|3|  
    |Speichern und Schließen|Einfügen|4|  
    |Trennzeichen|Einfügen|5|  
  
10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>-Ereignis von `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Fügen Sie im Ereignishandler Code ein, der dem folgenden Codebeispiel ähnelt, um neue Instanzen von `Form2` als untergeordnete MDI-Fenster von `Form1` zu erstellen und anzuzeigen.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
- Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../advanced/how-to-create-mdi-parent-forms.md)
- [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../advanced/how-to-create-mdi-child-forms.md)
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
