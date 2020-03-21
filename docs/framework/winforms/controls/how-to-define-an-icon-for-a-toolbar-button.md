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
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182210"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="85f5d-102">Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="85f5d-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="85f5d-103">Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="85f5d-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="85f5d-104"><xref:System.Windows.Forms.ToolBar>Tasten sind in der Lage, Symbole in ihnen für eine einfache Identifizierung durch Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="85f5d-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="85f5d-105">Dies wird erreicht, indem der [ImageList-Komponentenkomponente](imagelist-component-windows-forms.md) Bilder <xref:System.Windows.Forms.ImageList> hinzugefügt <xref:System.Windows.Forms.ToolBar> und die Komponente dann dem Steuerelement zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="85f5d-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="85f5d-106">So legen Sie ein Symbol für eine Symbolleistenschaltfläche programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="85f5d-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="85f5d-107">Instanziieren Sie in einem <xref:System.Windows.Forms.ImageList> Verfahren <xref:System.Windows.Forms.ToolBar> eine Komponente und ein Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="85f5d-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="85f5d-108">Weisen Sie der Komponente im <xref:System.Windows.Forms.ImageList> gleichen Verfahren ein Bild zu.</span><span class="sxs-lookup"><span data-stu-id="85f5d-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="85f5d-109">Weisen Sie das <xref:System.Windows.Forms.ImageList> Steuerelement im <xref:System.Windows.Forms.ToolBar> gleichen Verfahren <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> dem Steuerelement zu, und weisen Sie die Eigenschaft der einzelnen Symbolleistenschaltflächen zu.</span><span class="sxs-lookup"><span data-stu-id="85f5d-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="85f5d-110">Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bildes festgelegt ist, der Ordner **Eigene Dokumente.**</span><span class="sxs-lookup"><span data-stu-id="85f5d-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="85f5d-111">Dies ist der Grund, da Sie davon ausgehen können, dass die meisten Computer, auf denen das Windows-Betriebssystem ausgeführt wird, dieses Verzeichnis enthalten.</span><span class="sxs-lookup"><span data-stu-id="85f5d-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="85f5d-112">Dadurch können auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="85f5d-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="85f5d-113">Im folgenden Beispiel wird <xref:System.Windows.Forms.PictureBox> ein Formular mit einem bereits hinzugefügten Steuerelement angenommen.</span><span class="sxs-lookup"><span data-stu-id="85f5d-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="85f5d-114">Nach den obigen Schritten sollten Sie Code geschrieben haben, der dem unten angezeigten ähnelt.</span><span class="sxs-lookup"><span data-stu-id="85f5d-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="85f5d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85f5d-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="85f5d-116">Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen</span><span class="sxs-lookup"><span data-stu-id="85f5d-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="85f5d-117">ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="85f5d-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="85f5d-118">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="85f5d-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
