---
title: "Gewusst wie: Definieren eines Symbols f&#252;r eine Symbolleisten-Schaltfl&#228;che | Microsoft Docs"
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
  - "Schaltflächen [Windows Forms], Symbole"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbole [Windows Forms], Schaltflächen der Symbolleiste"
  - "Bilder [Windows Forms], Schaltflächen der Symbolleiste"
  - "ToolBar-Steuerelement [Windows Forms], Hinzufügen von Symbolen zu Schaltflächen"
  - "Symbolleisten [Windows Forms], Hinzufügen von Symbolen zu Schaltflächen"
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Definieren eines Symbols f&#252;r eine Symbolleisten-Schaltfl&#228;che
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement das <xref:System.Windows.Forms.ToolBar>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Auf <xref:System.Windows.Forms.ToolBar>\-Schaltflächen können Symbole angezeigt werden, damit sie für die Benutzer leicht erkennbar sind.  Hierzu werden der [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)\-Komponente Bilder hinzugefügt. Anschließend wird die <xref:System.Windows.Forms.ImageList>\-Komponente dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement zugewiesen.  
  
### So legen Sie ein Symbol für eine Symbolleisten\-Schaltfläche programmgesteuert fest  
  
1.  Instanziieren Sie in einer Prozedur eine <xref:System.Windows.Forms.ImageList>\-Komponente und ein <xref:System.Windows.Forms.ToolBar>\-Steuerelement.  
  
2.  Weisen Sie der <xref:System.Windows.Forms.ImageList>\-Komponente in derselben Prozedur ein Bild zu.  
  
3.  Weisen Sie in derselben Prozedur das <xref:System.Windows.Forms.ImageList>\-Steuerelement dem <xref:System.Windows.Forms.ToolBar>\-Steuerelement zu. Weisen Sie auch die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>\-Eigenschaft der einzelnen Symbolleisten\-Schaltflächen zu.  
  
     Im folgenden Codebeispiel wurde als Speicherort für das Bild der Ordner **Eigene Dateien** festgelegt.  Dieser Speicherort wird verwendet, weil vorausgesetzt werden kann, dass die meisten Computer mit einem Windows\-Betriebssystem über dieses Verzeichnis verfügen.  Auf diese Weise können auch Benutzer mit minimalen Systemzugriffsberechtigungen die Anwendung sicher ausführen.  Im unten stehenden Beispiel wird davon ausgegangen, dass einem Formular bereits ein <xref:System.Windows.Forms.PictureBox>\-Steuerelement hinzugefügt wurde.  
  
     Den oben stehenden Schritten entsprechend sollte der von Ihnen geschriebene Code etwa wie folgt aussehen.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolBar>   
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleisten\-Schaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [ToolBar\-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)