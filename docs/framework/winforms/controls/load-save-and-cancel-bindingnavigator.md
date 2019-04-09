---
title: 'Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 52d4fc32836a5d20bd99d8ebfd3119c761376e30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098714"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Vorgehensweise: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist eine zweckgebundene <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen im Formular, das an Daten gebunden werden soll.  
  
 Da es ist eine <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das <xref:System.Windows.Forms.BindingNavigator> Komponente kann problemlos geändert werden, um zusätzliche oder andere Befehle für den Benutzer bereitzustellen.  
  
 Im folgenden Verfahren eine <xref:System.Windows.Forms.TextBox> -Steuerelement an Daten gebunden ist und die <xref:System.Windows.Forms.ToolStrip> -Steuerelement, das dem Formular hinzugefügt wird geändert, um das Laden, speichern und Abbrechen (Schaltflächen).  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Zum Hinzufügen laden, speichern und Abbrechen (Schaltflächen) der BindingNavigator-Komponente  
  
1.  Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.  
  
2.  Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, das an eine Datenquelle gebunden ist. In diesem Beispiel die <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden ist.  
  
3.  Nachdem die Adapter Dataset und eine Tabelle generiert wurden, ziehen Sie eine <xref:System.Windows.Forms.BindingNavigator> -Steuerelement auf das Formular.  
  
4.  Legen Sie die <xref:System.Windows.Forms.BindingNavigator> des Steuerelements <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> Eigenschaft, um die <xref:System.Windows.Forms.BindingSource> auf das Formular, das an die Steuerelemente gebunden ist.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.  
  
6.  Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) daher **BindingNavigator-Aufgaben** Dialogfeld wird angezeigt, und wählen Sie **ElementeBearbeiten**.  
  
     Die **-Elementauflistungs-Editor** angezeigt wird.  
  
7.  In der **-Elementauflistungs-Editor**, führen Sie die folgenden:  
  
    1.  Hinzufügen einer <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton> Elemente nach Auswahl des entsprechenden Typs <xref:System.Windows.Forms.ToolStripItem> und klicken Sie auf die **hinzufügen** Schaltfläche.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A> Eigenschaft die Schaltflächen für die **LoadButton**, **SaveButton**, und **CancelButton**bzw.  
  
    3.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A> Eigenschaft die Schaltflächen für die **Load**, **speichern**, und **Abbrechen**.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> -Eigenschaft für die Schaltflächen um **Text**. Alternativ können Sie diese Eigenschaft festlegen, um **Image** oder **ImageAndText**, festlegen und das Bild anzuzeigenden der <xref:System.Windows.Forms.ToolStripItem.Image%2A> Eigenschaft.  
  
    5.  Klicken Sie auf **OK** um das Dialogfeld zu schließen. Die Schaltflächen werden hinzugefügt, um die <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Mit der rechten Maustaste in des Formulars, und wählen Sie **Ansichtscode**.  
  
9. Suchen Sie im Code-Editor, die Zeile des Codes, der Daten in der Tabellenadapter lädt. Dieser Code wurde generiert, wenn Sie die Datenbindung in Schritt 2 einrichten. Der Code sollte ähnlich der folgenden sein: `TableAdapterName.Fill(DataSetName.TableName)`. Die meisten wird voraussichtlich im des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis.  
  
10. Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **Load** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und verschieben Sie diesen Code Laden von Daten in.  
  
     Der Code sollte jetzt etwa wie folgt aussehen:  
  
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
  
11. Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **speichern** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben Sie Code zum Aktualisieren der Daten in der Tabelle das Steuerelement gebunden ist.  
  
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
    > In einigen Fällen die <xref:System.Windows.Forms.BindingNavigator> Komponente verfügen bereits über eine **speichern** Schaltfläche, aber keinen Code vom Windows Forms-Designer generiert wurde. In diesem Fall können Sie in den vorangehenden Code Platzieren der <xref:System.Windows.Forms.ToolStripItem.Click> -Ereignishandler für diese Schaltfläche, anstatt eine komplett neue Schaltfläche auf der <xref:System.Windows.Forms.ToolStrip>. Allerdings die Schaltfläche ist standardmäßig deaktiviert, daher Sie festlegen müssen, die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft der Schaltfläche auf `true` um die Funktion der Schaltfläche richtig zu erhalten.
  
12. Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignis die **Abbrechen** <xref:System.Windows.Forms.ToolStripButton> Sie zuvor erstellt haben, und Schreiben von Code zum Abbrechen von Änderungen an den Datensatz, der angezeigt wird.  
  
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
    >  Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Methode bezieht sich auf die Zeile der Daten. Speichern Sie alle Änderungen, die Sie vornehmen, während der Anzeige dieser einzelnen Datensätze vor der Navigation zum nächsten Datensatz.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
- [Übersicht über die BindingSource-Komponente](bindingsource-component-overview.md)
