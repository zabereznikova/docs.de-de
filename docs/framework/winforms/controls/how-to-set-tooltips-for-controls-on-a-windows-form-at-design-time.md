---
title: 'Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 689b06e8fbebe490f79ab6c12f144546472a95ff
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087218"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="65a23-102">Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="65a23-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="65a23-103">Sie können festlegen, eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in der Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="65a23-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="65a23-104">Weitere Informationen zu den <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter [Übersicht über die ToolTip-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="65a23-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65a23-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="65a23-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="65a23-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65a23-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="65a23-107">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="65a23-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="65a23-108">So legen Sie eine QuickInfo programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="65a23-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="65a23-109">Fügen Sie das Steuerelement, das die QuickInfo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65a23-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="65a23-110">Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="65a23-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="65a23-111">Festlegen eine QuickInfo im designer</span><span class="sxs-lookup"><span data-stu-id="65a23-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="65a23-112">Fügen Sie eine <xref:System.Windows.Forms.ToolTip>-Komponente zum Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="65a23-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="65a23-113">Wählen Sie das Steuerelement, das die QuickInfo angezeigt, oder fügen Sie es dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="65a23-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="65a23-114">In der **Eigenschaften** legen die **QuickInfo auf ToolTip1** Wert, der eine entsprechende Zeichenfolge des Texts.</span><span class="sxs-lookup"><span data-stu-id="65a23-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="65a23-115">Das programmgesteuerte Entfernen von einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="65a23-115">To remove a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="65a23-116">Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="65a23-116">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a><span data-ttu-id="65a23-117">So entfernen Sie eine QuickInfo im designer</span><span class="sxs-lookup"><span data-stu-id="65a23-117">To remove a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="65a23-118">Wählen Sie das Steuerelement, das die QuickInfo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65a23-118">Select the control that is displaying the ToolTip.</span></span>  
  
2.  <span data-ttu-id="65a23-119">In der **Eigenschaften** Fenster, löschen Sie den Text in die **QuickInfo auf ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="65a23-119">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="65a23-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65a23-120">See Also</span></span>  
- [<span data-ttu-id="65a23-121">Übersicht über die ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="65a23-121">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
- [<span data-ttu-id="65a23-122">Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65a23-122">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
- [<span data-ttu-id="65a23-123">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="65a23-123">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
