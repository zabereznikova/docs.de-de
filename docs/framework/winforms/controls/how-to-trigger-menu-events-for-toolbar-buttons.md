---
title: 'Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen'
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
ms.openlocfilehash: 99db077b41a59fe9263f7283b58b8c31959c7c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182075"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="5dc11-102">Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen</span><span class="sxs-lookup"><span data-stu-id="5dc11-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
> <span data-ttu-id="5dc11-103">Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das <xref:System.Windows.Forms.ToolBar>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.ToolBar>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5dc11-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="5dc11-104">Wenn Ihr Windows-Formular über ein <xref:System.Windows.Forms.ToolBar> Steuerelement mit Symbolleistenschaltflächen verfügt, sollten Sie wissen, auf welche Schaltfläche der Benutzer klickt.</span><span class="sxs-lookup"><span data-stu-id="5dc11-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="5dc11-105">Im <xref:System.Windows.Forms.ToolBar.ButtonClick> Ereignis des <xref:System.Windows.Forms.ToolBar> Steuerelements können <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> Sie die <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> Eigenschaft der Klasse auswerten.</span><span class="sxs-lookup"><span data-stu-id="5dc11-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="5dc11-106">Im folgenden Beispiel wird ein Meldungsfeld angezeigt, das angibt, auf welche Schaltfläche geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="5dc11-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="5dc11-107">Einzelheiten dazu finden Sie unter <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="5dc11-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="5dc11-108">Im folgenden Beispiel <xref:System.Windows.Forms.ToolBar> wird davon ausgegangen, dass einem Windows-Formular ein Steuerelement hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="5dc11-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="5dc11-109">So behandeln Sie das Click-Ereignis für eine Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="5dc11-109">To handle the Click event on a toolbar</span></span>  
  
1. <span data-ttu-id="5dc11-110">Fügen Sie dem Steuerelement in <xref:System.Windows.Forms.ToolBar> einer Prozedur Symbolleistenschaltflächen hinzu.</span><span class="sxs-lookup"><span data-stu-id="5dc11-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
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
  
2. <span data-ttu-id="5dc11-111">Fügen Sie einen <xref:System.Windows.Forms.ToolBar> Ereignishandler <xref:System.Windows.Forms.ToolBar.ButtonClick> für das Ereignis des Steuerelements hinzu.</span><span class="sxs-lookup"><span data-stu-id="5dc11-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="5dc11-112">Verwenden Sie eine Anweisung <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> für die Großundteilumschaltung und die Klasse, um die Schaltfläche "Symbolleisten" zu bestimmen, auf die geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="5dc11-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="5dc11-113">Zeigen Sie basierend darauf ein entsprechendes Meldungsfenster an.</span><span class="sxs-lookup"><span data-stu-id="5dc11-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5dc11-114">Im vorliegenden Beispiel wird ein Meldungsfenster lediglich als Platzhalter verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dc11-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="5dc11-115">Sie können bei Bedarf weiteren, nach dem Klicken auf eine Schaltfläche auszuführenden Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5dc11-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5dc11-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dc11-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="5dc11-117">Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5dc11-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="5dc11-118">Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5dc11-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="5dc11-119">ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5dc11-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
