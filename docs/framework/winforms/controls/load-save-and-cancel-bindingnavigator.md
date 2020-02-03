---
title: Schaltflächen zum Laden, speichern und Abbrechen zum BindingNavigator-Steuerelement hinzufügen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: ac862d163f1bd8b66f29160d836bc459e4bf4081
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745127"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Gewusst wie: Hinzufügen der Schaltflächen für das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms

Das <xref:System.Windows.Forms.BindingNavigator> Steuerelement ist ein spezielles <xref:System.Windows.Forms.ToolStrip> Steuerelement, das zum Navigieren und Bearbeiten von Steuerelementen auf dem Formular dient, die an Daten gebunden sind.

Da es sich um ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement handelt, kann die <xref:System.Windows.Forms.BindingNavigator> Komponente problemlos geändert werden, um zusätzliche oder Alternative Befehle für den Benutzer einzuschließen.

Im folgenden Verfahren wird ein <xref:System.Windows.Forms.TextBox>-Steuerelement an Daten gebunden, und das <xref:System.Windows.Forms.ToolStrip> Steuerelement, das dem Formular hinzugefügt wird, wird so geändert, dass es die Schaltflächen laden, speichern und Abbrechen enthält.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Hinzufügen von Schaltflächen zum Laden, speichern und Abbrechen zur BindingNavigator-Komponente

1. Fügen Sie in Visual Studio ein <xref:System.Windows.Forms.TextBox>-Steuerelement zum Formular hinzu.

2. Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, die an eine Datenquelle gebunden ist. In diesem Beispiel ist der <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden.

3. Nachdem das DataSet und der Tabellen Adapter generiert wurden, ziehen Sie ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in das Formular.

4. Legen Sie die <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>-Eigenschaft des <xref:System.Windows.Forms.BindingNavigator> Steuer Elements auf die <xref:System.Windows.Forms.BindingSource> in dem Formular fest, das an die Steuerelemente gebunden ist.

5. Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement.

6. Klicken Sie auf das Smarttagsymbol (![Smarttag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")-Symbol), damit das Dialogfeld **BindingNavigator-Aufgaben** angezeigt wird, und klicken Sie auf **Elemente bearbeiten**.

     Der Elementauflistungs- **Editor** wird angezeigt.

7. Führen Sie im Elementauflistungs- **Editor**die folgenden Schritte aus:

    1. Fügen Sie einen <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton> Elemente hinzu, indem Sie den entsprechenden Typ von <xref:System.Windows.Forms.ToolStripItem> auswählen und auf die Schaltfläche **Hinzufügen** klicken.

    2. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A>-Eigenschaft der Schaltflächen auf **loadButton**, **SaveButton**bzw. **CancelButton**fest.

    3. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft der Schaltflächen auf **Laden**, **Speichern**und **Abbrechen**fest.

    4. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft für jede Schaltfläche auf **Text**fest. Alternativ können Sie diese Eigenschaft auf **Image** oder **ImageAndText**festlegen und das Bild so festlegen, dass es in der <xref:System.Windows.Forms.ToolStripItem.Image%2A>-Eigenschaft angezeigt wird.

    5. Klicken Sie auf **OK**, um das Dialogfeld zu schließen. Die Schaltflächen werden der <xref:System.Windows.Forms.ToolStrip>hinzugefügt.

8. Klicken Sie mit der rechten Maustaste, und wählen Sie **Code anzeigen**aus.

9. Suchen Sie im Code-Editor nach der Codezeile, die Daten in den Tabellen Adapter lädt. Dieser Code wurde generiert, als Sie die Datenbindung in Schritt 2 eingerichtet haben. Der Code sollte in etwa wie folgt aussehen: `TableAdapterName.Fill(DataSetName.TableName)`. Sie wird wahrscheinlich im <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars angezeigt.

10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis der zuvor erstellten **Load** -<xref:System.Windows.Forms.ToolStripButton>, und verschieben Sie diesen Datenlade Code hinein.

     Der Code sollte nun in etwa wie folgt aussehen:

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

11. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis des zuvor erstellten **Speicher**<xref:System.Windows.Forms.ToolStripButton>, und schreiben Sie Code, um die Daten in der Tabelle zu aktualisieren, an die das Steuerelement gebunden ist.

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
    > In einigen Fällen verfügt die <xref:System.Windows.Forms.BindingNavigator> Komponente bereits über eine Schaltfläche zum **Speichern** , aber vom Windows Forms-Designer wurde kein Code generiert. In diesem Fall können Sie den vorangehenden Code im <xref:System.Windows.Forms.ToolStripItem.Click> Ereignishandler für diese Schaltfläche platzieren, anstatt eine völlig neue Schaltfläche auf dem <xref:System.Windows.Forms.ToolStrip>zu erstellen. Die Schaltfläche ist jedoch standardmäßig deaktiviert, sodass Sie die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A>-Eigenschaft der Schaltfläche auf `true` festlegen müssen, damit die Schaltfläche ordnungsgemäß funktioniert.

12. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis der zuvor erstellten **Cancel** -<xref:System.Windows.Forms.ToolStripButton>, und schreiben Sie Code, um alle Änderungen am angezeigten Daten Satz abzubrechen.

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
    > Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>-Methode wird auf die Daten Zeile festgelegt. Speichern Sie alle Änderungen, die Sie vornehmen, während Sie den einzelnen Datensatz anzeigen, bevor Sie zum nächsten Datensatz navigieren.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator-Steuerelement](bindingnavigator-control-windows-forms.md)
- [Übersicht über die BindingSource-Komponente](bindingsource-component-overview.md)
