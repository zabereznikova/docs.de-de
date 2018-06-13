---
title: 'Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 9c396f861307d1c8e722beaf38c6cb914d0630c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531910"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 <xref:System.Windows.Forms.ToolBar> Schaltflächen können Symbole darin enthaltene zur leichteren Identifizierung von Benutzern anzuzeigen. Dies erfolgt durch Hinzufügen von Bildern, die [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) -Komponente die <xref:System.Windows.Forms.ImageList> Komponente mit der <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>So legen Sie ein Symbol für eine Symbolleisten-Schaltfläche programmgesteuert fest  
  
1.  Instanziieren Sie in einer Prozedur ein <xref:System.Windows.Forms.ImageList> Komponente und eine <xref:System.Windows.Forms.ToolBar> Steuerelement.  
  
2.  Weisen Sie in die gleiche Prozedur, ein Bild an, die <xref:System.Windows.Forms.ImageList> Komponente.  
  
3.  Weisen Sie in der gleichen Prozedur die <xref:System.Windows.Forms.ImageList> die Steuerung an die <xref:System.Windows.Forms.ToolBar> steuern und weisen Sie die <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> Eigenschaft der einzelnen Symbolleisten-Schaltflächen.  
  
     Im folgenden Codebeispiel legen der Pfad für der Speicherort des Bilds wird die **eigene** Ordner. Dies geschieht, da Sie davon ausgehen können, die meisten Computer das Windows-Betriebssystem ausgeführt werden, dieses Verzeichnis enthält. Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen. Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.PictureBox> Steuerelement bereits hinzugefügt.  
  
     Nach der oben beschriebenen Schritten sollten Sie Code ähnlich dem unten angezeigten geschrieben haben.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolBar>  
 [Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar-Steuerelement](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
