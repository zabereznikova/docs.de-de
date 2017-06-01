---
title: "Gewusst wie: Hinzuf&#252;gen der Schaltfl&#228;chen f&#252;r das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], bearbeiten"
  - "BindingNavigator-Steuerelement [Windows Forms], Hinzufügen von Schaltflächen"
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Hinzuf&#252;gen der Schaltfl&#228;chen f&#252;r das Laden, Speichern und Abbrechen zum BindingNavigator-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement ist ein spezielles <xref:System.Windows.Forms.ToolStrip>\-Steuerelement, das für die Navigation und Bearbeitung von Steuerelementen vorgesehen ist, die an Daten gebunden sind.  
  
 Da es sich um ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement handelt, kann die <xref:System.Windows.Forms.BindingNavigator>\-Komponente problemlos geändert werden, um zusätzliche oder alternative Befehle für den Benutzer bereitzustellen.  
  
 In der folgenden Prozedur ist ein <xref:System.Windows.Forms.TextBox>\-Steuerelement an Daten gebunden, und das dem Formular hinzugefügte <xref:System.Windows.Forms.ToolStrip>\-Steuerelement wird um die Schaltflächen für das Laden, Speichern und Abbrechen ergänzt.  
  
### So fügen Sie die Schaltflächen für das Laden, Speichern und Abbrechen der BindingNavigator\-Komponente hinzu  
  
1.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.TextBox>\-Steuerelement hinzu.  
  
2.  Binden Sie es an eine <xref:System.Windows.Forms.BindingSource>, die an eine Datenquelle gebunden ist.  In diesem Beispiel ist die <xref:System.Windows.Forms.BindingSource> an eine Datenbank gebunden.  
  
3.  Nachdem das Dataset und der Tabellenadapter generiert wurden, ziehen Sie ein <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement in das Formular.  
  
4.  Legen Sie für die <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A>\-Eigenschaft des <xref:System.Windows.Forms.BindingNavigator>\-Steuerelements die <xref:System.Windows.Forms.BindingSource> auf dem Formular fest, die an die Steuerelemente gebunden ist.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.BindingNavigator>\-Steuerelement aus.  
  
6.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\), um das Dialogfeld **BindingNavigator\-Aufgaben** aufzurufen, und wählen Sie **Elemente bearbeiten** aus.  
  
     Der **Elementauflistungs\-Editor** wird angezeigt.  
  
7.  Führen Sie im **Elementauflistungs\-Editor** folgende Schritte aus:  
  
    1.  Fügen Sie ein <xref:System.Windows.Forms.ToolStripSeparator> und drei <xref:System.Windows.Forms.ToolStripButton>\-Elemente hinzu, indem Sie den entsprechenden <xref:System.Windows.Forms.ToolStripItem>\-Typ auswählen und auf die Schaltfläche **Hinzufügen** klicken.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Name%2A>\-Eigenschaft der Schaltflächen auf `` LoadButton, `` SaveButton und `` CancelButton fest.  
  
    3.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft der Schaltflächen auf `` Load`,` Save und `` Cancel fest.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>\-Eigenschaft für jede der Schaltflächen auf `` Text fest.  Wahlweise können Sie diese Eigenschaft auf `` Image `` oder `` ImageAndText `` festlegen und das anzuzeigende Bild in der <xref:System.Windows.Forms.ToolStripItem.Image%2A>\-Eigenschaft auswählen.  
  
    5.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen. Die Schaltflächen werden dem <xref:System.Windows.Forms.ToolStrip> hinzugefügt.  
  
8.  Klicken Sie mit der rechten Maustaste auf das Formular, und wählen Sie **Code anzeigen**.  
  
9. Suchen Sie im Code\-Editor die Codezeile, mit der Daten in den Tabellenadapter geladen werden.  Dieser Code wurde generiert, als Sie die Datenbindung in Schritt 2 eingerichtet haben.  er Code sollte in etwa folgendermaßen aussehen: `TableAdapterName.Fill(DataSetName.TableName)`.  Er ist voraussichtlich im <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars enthalten.  
  
10. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis der zuvor erstellten  `` **Auslastung** `` <xref:System.Windows.Forms.ToolStripButton>, und verschieben Sie diesen Code in den Handler.  
  
     Der Code sollte nun ungefähr wie folgt aussehen:  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis des zuvor erstellten  `` <xref:System.Windows.Forms.ToolStripButton> **Save**, und schreiben Sie Code, um die Daten in der Tabelle, an die das Steuerelement gebunden ist, zu aktualisieren.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  In einigen Fällen verfügt die <xref:System.Windows.Forms.BindingNavigator>\-Komponente bereits über die Schaltfläche `` **Speichern**, allerdings ohne dass Code vom Windows Forms\-Designer generiert wurde.  In diesem Fall können Sie den voranstehenden Code in den <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignishandler für diese Schaltfläche einfügen, anstatt eine komplett neue Schaltfläche auf dem <xref:System.Windows.Forms.ToolStrip> zu erstellen.  Da die Schaltfläche jedoch standardmäßig deaktiviert ist, müssen Sie die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A>\-Eigenschaft der Schaltfläche auf `true` festlegen, damit die Schaltfläche ordnungsgemäß funktioniert.  
  
12. Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis des zuvor erstellten ``  `T:System.Windows.Forms.ToolStripButton` **Abbrechen**, und schreiben Sie Code, um Änderungen an dem angezeigten Datensatz zu verwerfen.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>\-Methode wird auf die Datenzeile beschränkt.  Speichern Sie alle Änderungen, die Sie vornehmen, während Sie diesen Datensatz anzeigen, bevor Sie zum nächsten Datensatz navigieren.  
  
## Siehe auch  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.ToolStrip>   
 [BindingNavigator\-Steuerelement](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Übersicht über die BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)