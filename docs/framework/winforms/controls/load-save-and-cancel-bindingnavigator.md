---
title: 'Gewusst wie: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 8f331c67dd22a6a9e2382ecc11d23c67cd2a5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Gewusst wie: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist eine zweckgebundene <xref:System.Windows.Forms.ToolStrip> Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen auf dem Formular, das an Daten gebunden werden soll.  
  
 Da es ist ein <xref:System.Windows.Forms.ToolStrip> -Steuerelement, die <xref:System.Windows.Forms.BindingNavigator> Komponente kann problemlos geändert werden, um zusätzliche oder andere Befehle für den Benutzer enthalten.  
  
 Im folgenden Verfahren ein <xref:System.Windows.Forms.TextBox> -Steuerelement an Daten gebunden ist und die <xref:System.Windows.Forms.ToolStrip> dem Formular hinzugefügten Steuerelemente zum Laden, speichern und Abbrechen (Schaltflächen) geändert wird.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Zum Hinzufügen laden, speichern und Abbrechen (Schaltflächen) an das BindingNavigator-Komponente  
  
1.  Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.  
  
2.  Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, die an eine Datenquelle gebunden ist. In diesem Beispiel die <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden ist.  
  
3.  Nachdem das Dataset und der Tabellenadapter generiert wurden, ziehen Sie ein <xref:System.Windows.Forms.BindingNavigator> Steuerelement dem Formular.  
  
4.  Legen Sie die <xref:System.Windows.Forms.BindingNavigator> des Steuerelements <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> Eigenschaft, um die <xref:System.Windows.Forms.BindingSource> auf das Formular, das an die Steuerelemente gebunden ist.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.  
  
6.  Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) daher die **BindingNavigator Aufgaben** Dialogfeld wird angezeigt, und wählen Sie **ElementeBearbeiten**.  
  
     Die **-Elementauflistungs-Editor** angezeigt wird.  
  
7.  In der **-Elementauflistungs-Editor**, führen Sie Folgendes aus:  
  
    1.  Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton> Elemente durch Auswählen des entsprechenden <xref:System.Windows.Forms.ToolStripItem> und klicken Sie auf die **hinzufügen** Schaltfläche.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A> Eigenschaft der Schaltflächen auf**LoadButton**,**SaveButton**, und**CancelButton**bzw.  
  
    3.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft der Schaltflächen auf**laden** `,` **speichern**, und **"Abbrechen"**.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Eigenschaft für die einzelnen Schaltflächen, um**Text**. Alternativ können Sie diese Eigenschaft festlegen, um**Image**oder**ImageAndText**festlegen und das Bild angezeigt werden die <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft.  
  
    5.  Klicken Sie auf **OK** um das Dialogfeld zu schließen. Die Schaltflächen werden hinzugefügt, um die <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Mit der rechten Maustaste in des Formulars, und wählen Sie **Code anzeigen**.  
  
9. Suchen Sie im Code-Editor die Zeile des Codes, die Daten in der Tabellenadapter lädt. Dieser Code generiert wurde, beim Einrichten der Datenbindung in Schritt 2. Der Code sollte ähnlich der folgenden sein: `TableAdapterName.Fill(DataSetName.TableName)`. Es werden die meisten werden wahrscheinlich in der Form <xref:System.Windows.Forms.Form.Load> Ereignis.  
  
10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die**laden** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und verschieben Sie diesen Code Laden von Daten in.  
  
     Der Code sollte etwa wie folgt aussehen:  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die **speichern** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben Sie Code zum Aktualisieren der Daten innerhalb der Tabelle das Steuerelement gebunden ist.  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  In einigen Fällen die <xref:System.Windows.Forms.BindingNavigator> Komponente müssen bereits ein**speichern** Schaltfläche aber keinen Code von Windows Forms-Designer generiert wurde. In diesem Fall können Sie im vorangehenden Code Platzieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für diese Schaltfläche, statt eine völlig neue Schaltfläche zu erstellen, auf die <xref:System.Windows.Forms.ToolStrip>. Allerdings die Schaltfläche "" ist standardmäßig deaktiviert, daher Sie festlegen müssen, die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft der Schaltfläche auf `true` haben Sie die Schaltfläche Funktion ordnungsgemäß.  
  
12. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignis für die **"Abbrechen"** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Code schreiben, um alle Änderungen an den Datensatz "Abbrechen", der angezeigt wird.  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Methode auf die Datenzeile begrenzt. Speichern Sie alle Änderungen, die Sie vornehmen, während dieser einzelnen Datensätze vor dem Navigieren zu den nächsten Datensatz anzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [BindingNavigator-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Übersicht über die BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
