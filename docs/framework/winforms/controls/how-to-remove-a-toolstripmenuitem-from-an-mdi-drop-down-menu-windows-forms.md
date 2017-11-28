---
title: "Gewusst wie: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b265544b45ad0614985fdc1d8dbf6f9c0b909ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>Gewusst wie: Entfernen eines ToolStripMenuItem aus einem MDI-Dropdownmenü (Windows Forms)
In einigen Anwendungen kann sich die Art eines untergeordneten MDI-Fensters (Multiple-Document Interface) von der des übergeordneten MDI-Fensters unterscheiden. Beispielsweise könnte das übergeordnete MDI-Fenster eine Kalkulationstabelle und das untergeordnete MDI-Fenster ein Diagramm enthalten. In diesem Fall möchten Sie möglicherweise den Inhalt des Menüs des übergeordneten MDI-Fensters mit dem Inhalt des Menüs des untergeordneten MDI-Fensters aktualisieren, da untergeordnete MDI-Fenster unterschiedlicher Arten aktiviert werden.  
  
 Im folgenden Verfahren wird die <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften zum Entfernen eines Menüelements aus dem Dropdownbereich des übergeordneten MDI-Menüs. Die entfernte Menüelemente schließen die untergeordneten MDI-Fensters in übergeordneten MDI-Menüs wiederhergestellt wird.  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>So entfernen Sie ein MenuStrip in ein MDI-Dropdownmenü  
  
1.  Erstellen Sie ein Formular, und legen Sie dessen <xref:System.Windows.Forms.Form.IsMdiContainer%2A>-Eigenschaft auf `true` fest.  
  
2.  Fügen Sie einen <xref:System.Windows.Forms.MenuStrip> zu `Form1` hinzu, und legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft des <xref:System.Windows.Forms.MenuStrip> auf `true` fest  
  
3.  Fügen Sie ein Menüelement der obersten Ebene zu `Form1`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `&File` fest.  
  
4.  Hinzufügen von drei Untermenüelemente hinzu der `&File` Menüelement und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Open`, `&Import from`, und `E&xit`.  
  
5.  Fügen Sie zwei Untermenüelemente hinzu. die `&Import from` Untermenüelement und legen ihre <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaften `&Word` und `&Excel`.  
  
6.  Fügen Sie dem Projekt ein Formular hinzu, fügen Sie dem Formular ein <xref:System.Windows.Forms.MenuStrip> hinzu, und legen die <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>-Eigenschaft von `Form2`<xref:System.Windows.Forms.MenuStrip> auf `true` fest.  
  
7.  Fügen Sie ein Menüelement der obersten Ebene zu `Form2`<xref:System.Windows.Forms.MenuStrip> hinzu, und legen Sie dessen <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf `&File` fest.  
  
8.  Hinzufügen einer `&Import from` Untermenüelement hinzu der `&File` Menü `Form2`, und fügen eine `&Word` Untermenüelement hinzu der `&File` im Menü.  
  
9. Festlegen der <xref:System.Windows.Forms.MergeAction> und <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> Eigenschaften der `Form2` Menüelemente, wie in der folgenden Tabelle gezeigt.  
  
    |Menüelement Form2|MergeAction-Wert|MergeIndex-Wert|  
    |---------------------|-----------------------|----------------------|  
    |Datei|MatchOnly|-1|  
    |Importieren aus|MatchOnly|-1|  
    |Word|Entfernen|-1|  
  
10. In `Form1`, erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click> -Ereignis für die `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. Fügen Sie im Ereignishandler Code wie im folgenden Codebeispiel wird zum Erstellen und Anzeigen von neue Instanzen eines `Form2` als untergeordnete MDI-Fenster von `Form1`:  
  
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
  
-   Zwei <xref:System.Windows.Forms.Form>-Steuerelemente namens `Form1` und `Form2`.  
  
-   Ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form1`, das den Namen `menuStrip1` hat, und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement auf `Form2`, das den Namen `menuStrip2` hat.  
  
-   Verweise auf die <xref:System?displayProperty=nameWithType>-Assembly und die <xref:System.Windows.Forms?displayProperty=nameWithType>-Assembly.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von übergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Gewusst wie: Erstellen von untergeordneten MDI-Formularen](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
