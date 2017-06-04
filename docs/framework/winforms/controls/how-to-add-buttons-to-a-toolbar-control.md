---
title: "Gewusst wie: Hinzuf&#252;gen von Schaltfl&#228;chen zu einem ToolBar-Steuerelement | Microsoft Docs"
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
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Schaltflächen"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Dropdownmenüs"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Trennzeichen"
  - "Symbolleisten [Windows Forms], Hinzufügen von Schaltflächen"
ms.assetid: 78a58a8d-1041-4e38-9219-4096fa6a5c5c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Hinzuf&#252;gen von Schaltfl&#228;chen zu einem ToolBar-Steuerelement
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Ein wesentlicher Bestandteil des <xref:System.Windows.Forms.ToolBar>\-Steuerelements sind die von Ihnen hinzugefügten Schaltflächen.  Mit diesen Schaltflächen kann ein problemloser Zugriff auf Menübefehle bereitgestellt werden. Sie können jedoch auch in einem anderen Bereich der Benutzeroberfläche der Anwendung platziert werden, um Benutzern Befehle zur Verfügung zu stellen, die in der Menüstruktur nicht verfügbar sind.  
  
 In nachfolgendem Beispiel wird davon ausgegangen, dass einem Windows Form \(`Form1`\) ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement hinzugefügt wurde.  
  
### So fügen Sie Schaltflächen programmgesteuert hinzu  
  
1.  Erstellen Sie in einer Prozedur Symbolleisten\-Schaltflächen, indem Sie diese der <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=fullName>\-Auflistung hinzufügen.  
  
2.  Geben Sie Eigenschafteneinstellungen für einzelne Schaltflächen an, indem Sie den Index der Schaltfläche mit der <xref:System.Windows.Forms.ToolBar.Buttons%2A>\-Eigenschaft übergeben.  
  
     Im unten stehenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement hinzugefügt wurde.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=fullName>\-Auflistung ist nullbasiert, daher sollte die Ausführung von Code entsprechend fortgesetzt werden.  
  
    ```vb  
    Public Sub CreateToolBarButtons()  
    ' Create buttons and set text property.  
       ToolBar1.Buttons.Add("One")  
       ToolBar1.Buttons.Add("Two")  
       ToolBar1.Buttons.Add("Three")  
       ToolBar1.Buttons.Add("Four")  
    ' Set properties of StatusBar panels.  
    ' Set Style property.  
       ToolBar1.Buttons(0).Style = ToolBarButtonStyle.PushButton  
       ToolBar1.Buttons(1).Style = ToolBarButtonStyle.Separator  
       ToolBar1.Buttons(2).Style = ToolBarButtonStyle.ToggleButton  
       ToolBar1.Buttons(3).Style = ToolBarButtonStyle.DropDownButton  
    ' Set the ToggleButton's PartialPush property.  
       ToolBar1.Buttons(2).PartialPush = True  
    ' Instantiate a ContextMenu component and menu items.  
    ' Set the DropDownButton's DropDownMenu property to the context menu.  
       Dim cm As New ContextMenu()  
       Dim miOne As New MenuItem("One")  
       Dim miTwo As New MenuItem("Two")  
       Dim miThree As New MenuItem("Three")  
       cm.MenuItems.Add(miOne)  
       cm.MenuItems.Add(miTwo)  
       cm.MenuItems.Add(miThree)  
       ToolBar1.Buttons(3).DropDownMenu = cm  
    ' Set the PushButton's Pushed property.  
       ToolBar1.Buttons(0).Pushed = True  
    ' Set the ToolTipText property of one of the buttons.  
       ToolBar1.Buttons(1).ToolTipText = "Button 2"  
    End Sub  
  
    ```  
  
    ```csharp  
    public void CreateToolBarButtons()  
    {  
       // Create buttons and set text property.  
       toolBar1.Buttons.Add("One");  
       toolBar1.Buttons.Add("Two");  
       toolBar1.Buttons.Add("Three");  
       toolBar1.Buttons.Add("Four");  
  
       // Set properties of StatusBar panels.  
       // Set Style property.  
       toolBar1.Buttons[0].Style = ToolBarButtonStyle.PushButton;  
       toolBar1.Buttons[1].Style = ToolBarButtonStyle.Separator;  
       toolBar1.Buttons[2].Style = ToolBarButtonStyle.ToggleButton;  
       toolBar1.Buttons[3].Style = ToolBarButtonStyle.DropDownButton;  
  
       // Set the ToggleButton's PartialPush property.  
       toolBar1.Buttons[2].PartialPush = true;  
  
       // Instantiate a ContextMenu component and menu items.  
       // Set the DropDownButton's DropDownMenu property to   
       // the context menu.  
       ContextMenu cm = new ContextMenu();  
       MenuItem miOne = new MenuItem("One");  
       MenuItem miTwo = new MenuItem("Two");  
       MenuItem miThree = new MenuItem("Three");  
       cm.MenuItems.Add(miOne);  
       cm.MenuItems.Add(miTwo);  
       cm.MenuItems.Add(miThree);  
  
       toolBar1.Buttons[3].DropDownMenu = cm;  
       // Set the PushButton's Pushed property.  
       toolBar1.Buttons[0].Pushed = true;  
       // Set the ToolTipText property of 1 of the buttons.  
       toolBar1.Buttons[1].ToolTipText = "Button 2";  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void CreateToolBarButtons()  
       {  
          // Create buttons and set text property.  
          toolBar1->Buttons->Add( "One" );  
          toolBar1->Buttons->Add( "Two" );  
          toolBar1->Buttons->Add( "Three" );  
          toolBar1->Buttons->Add( "Four" );  
  
          // Set properties of StatusBar panels.  
          // Set Style property.  
          toolBar1->Buttons[0]->Style = ToolBarButtonStyle::PushButton;  
          toolBar1->Buttons[1]->Style = ToolBarButtonStyle::Separator;  
          toolBar1->Buttons[2]->Style = ToolBarButtonStyle::ToggleButton;  
          toolBar1->Buttons[3]->Style = ToolBarButtonStyle::DropDownButton;  
  
          // Set the ToggleButton's PartialPush property.  
          toolBar1->Buttons[2]->PartialPush = true;  
  
          // Instantiate a ContextMenu component and menu items.  
          // Set the DropDownButton's DropDownMenu property to   
          // the context menu.  
          System::Windows::Forms::ContextMenu^ cm = gcnew System::Windows::Forms::ContextMenu;  
          MenuItem^ miOne = gcnew MenuItem( "One" );  
          MenuItem^ miTwo = gcnew MenuItem( "Two" );  
          MenuItem^ miThree = gcnew MenuItem( "Three" );  
          cm->MenuItems->Add( miOne );  
          cm->MenuItems->Add( miTwo );  
          cm->MenuItems->Add( miThree );  
          toolBar1->Buttons[3]->DropDownMenu = cm;  
  
          // Set the PushButton's Pushed property.  
          toolBar1->Buttons[0]->Pushed = true;  
  
          // Set the ToolTipText property of 1 of the buttons.  
          toolBar1->Buttons[1]->ToolTipText = "Button 2";  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [Gewusst wie: Definieren eines Symbols für eine Symbolleisten\-Schaltfläche](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleisten\-Schaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Übersicht über das ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)