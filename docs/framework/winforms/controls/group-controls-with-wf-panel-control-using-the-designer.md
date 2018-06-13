---
title: 'Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1cf4519a9aaaa1c4f0df321ab38c3f543c87b2a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525622"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="cb15e-102">Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="cb15e-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="cb15e-103">Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um die Gruppierung anderer Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="cb15e-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="cb15e-104">Es gibt drei Gründe zum Gruppieren von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="cb15e-104">There are three reasons to group controls.</span></span> <span data-ttu-id="cb15e-105">Gruppieren von verwandten Form-Elemente für eine klare Benutzeroberfläche visual ist. Ein weiterer Vorteil ist die programmgesteuerte Gruppierung von Optionsfeldern z. B.; die letzte ist für die Steuerelemente zur Entwurfszeit als Einheit verschieben.</span><span class="sxs-lookup"><span data-stu-id="cb15e-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb15e-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="cb15e-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cb15e-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cb15e-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cb15e-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="cb15e-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="cb15e-109">So erstellen eine Gruppe von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="cb15e-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="cb15e-110">Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte der Toolbox auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="cb15e-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="cb15e-111">Fügen Sie weitere Steuerelemente, wenn der Bereich, und Zeichnen im Auswahlbereich aus.</span><span class="sxs-lookup"><span data-stu-id="cb15e-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="cb15e-112">Wenn Sie vorhandene Steuerelemente verfügen, die in einem Bereich eingeschlossen werden sollen, können Sie wählen Sie alle Steuerelemente, Ausschneiden in die Zwischenablage, wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und fügen Sie sie in der Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="cb15e-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="cb15e-113">Sie können auch in den Bereich ziehen.</span><span class="sxs-lookup"><span data-stu-id="cb15e-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="cb15e-114">(Optional) Wenn Sie ein Panel einen Rahmen hinzufügen möchten, legen Sie dessen <xref:System.Windows.Forms.BorderStyle> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cb15e-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="cb15e-115">Es gibt drei Möglichkeiten zur Auswahl: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, und <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="cb15e-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb15e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb15e-116">See Also</span></span>  
 [<span data-ttu-id="cb15e-117">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb15e-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="cb15e-118">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb15e-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="cb15e-119">Gewusst wie: Festlegen des Hintergrunds eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="cb15e-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
