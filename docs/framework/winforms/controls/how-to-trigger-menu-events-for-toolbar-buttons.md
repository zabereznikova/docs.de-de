---
title: "Gewusst wie: Ausl&#246;sen von Men&#252;ereignissen f&#252;r Symbolleisten-Schaltfl&#228;chen | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Symbolleisten"
  - "ToolBar-Steuerelement [Windows Forms], Click-Ereignishandler"
  - "ToolBar-Steuerelement [Windows Forms], Codieren einer Schaltfläche – Click-Ereignisse"
  - "Symbolleisten [Windows Forms], Click-Ereignishandler"
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Ausl&#246;sen von Men&#252;ereignissen f&#252;r Symbolleisten-Schaltfl&#228;chen
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Wenn das Windows Form ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement mit Symbolleisten\-Schaltflächen enthält, werden Sie wissen möchten, auf welche Schaltfläche der Benutzer klickt.  
  
 Im <xref:System.Windows.Forms.ToolBar.ButtonClick>\-Ereignis des <xref:System.Windows.Forms.ToolBar>\-Steuerelements können Sie die <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A>\-Eigenschaft der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>\-Klasse auswerten.  Im folgenden Beispiel wird ein Meldungsfeld angezeigt, das angibt, auf welche Schaltfläche geklickt wurde.  Ausführliche Informationen finden Sie unter [MessageBox\-Klasse](frlrfSystemWindowsFormsMessageBoxClassTopic).  
  
 Im nachfolgenden Beispiel wird davon ausgegangen, dass einem Windows Form ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement hinzugefügt wurde.  
  
### So behandeln Sie das Click\-Ereignis für eine Symbolleiste  
  
1.  Fügen Sie dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement in einer Prozedur Symbolleisten\-Schaltflächen hinzu.  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
  
    ```  
  
    ```csharp  
    public void ToolBarConfig()   
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=   
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=   
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2.  Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolBar.ButtonClick>\-Ereignis des <xref:System.Windows.Forms.ToolBar>\-Steuerelements hinzu.  Ermitteln Sie mit einer case\/switch\-Anweisung und mit der <xref:System.Windows.Forms.ToolBarButtonClickEventArgs>\-Klasse die Symbolleisten\-Schaltfläche, auf die geklickt wurde.  Zeigen Sie ein entsprechendes Meldungsfenster an.  
  
    > [!NOTE]
    >  Im vorliegenden Beispiel wird ein Meldungsfenster lediglich als Platzhalter verwendet.  Sie können bei Bedarf weiteren, nach dem Klicken auf eine Schaltfläche auszuführenden Code hinzufügen.  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [Gewusst wie: Definieren eines Symbols für eine Symbolleisten\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)