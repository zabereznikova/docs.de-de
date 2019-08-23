---
title: 'Vorgehensweise: Auslösen von Menüereignissen für Symbolleistenschaltflächen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: 381b8ba08db6ff5bb817c9c89008dacb1085ac1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956034"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Vorgehensweise: Auslösen von Menüereignissen für Symbolleistenschaltflächen
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Wenn Ihr Windows Form ein <xref:System.Windows.Forms.ToolBar> Steuerelement mit Symbolleisten-Schaltflächen enthält, sollten Sie wissen, auf welche Schaltfläche der Benutzer klickt.  
  
 Im- <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> Ereignis des-Steuer Elements können Sie die-Eigenschaft der- <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> Klasse auswerten. <xref:System.Windows.Forms.ToolBar.ButtonClick> Im folgenden Beispiel wird ein Meldungsfeld angezeigt, das angibt, auf welche Schaltfläche geklickt wurde. Ausführliche Informationen finden Sie unter <xref:System.Windows.Forms.MessageBox>.  
  
 Im folgenden Beispiel wird davon <xref:System.Windows.Forms.ToolBar> ausgegangen, dass ein-Steuerelement zu einem Windows Form hinzugefügt wurde.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>So behandeln Sie das Click-Ereignis für eine Symbolleiste  
  
1. Fügen Sie dem <xref:System.Windows.Forms.ToolBar> Steuerelement in einer Prozedur Symbolleisten-Schaltflächen hinzu.  
  
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
  
2. Fügen Sie einen Ereignishandler für <xref:System.Windows.Forms.ToolBar> das- <xref:System.Windows.Forms.ToolBar.ButtonClick> Ereignis des-Steuer Elements hinzu. Verwenden Sie eine Case-Wechsel Anweisung <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> und die-Klasse, um die Symbolleisten Schaltfläche zu bestimmen Zeigen Sie basierend darauf ein entsprechendes Meldungsfenster an.  
  
    > [!NOTE]
    > Im vorliegenden Beispiel wird ein Meldungsfenster lediglich als Platzhalter verwendet. Sie können bei Bedarf weiteren, nach dem Klicken auf eine Schaltfläche auszuführenden Code hinzufügen.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolBar>
- [Vorgehensweise: Hinzufügen von Schaltflächen zu Symbolleisten](how-to-add-buttons-to-a-toolbar-control.md)
- [Vorgehensweise: Definieren eines Symbols für eine Symbolleisten-Schaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)
- [ToolBar-Steuerelement](toolbar-control-windows-forms.md)
