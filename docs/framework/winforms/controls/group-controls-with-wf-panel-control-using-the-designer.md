---
title: 'Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 99bfcd96dea1bb92866127095a422003bf01f7cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506873"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="e8bdb-102">Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="e8bdb-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="e8bdb-103">Windows Forms <xref:System.Windows.Forms.Panel> Steuerelemente werden verwendet, um die Gruppierung anderer Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="e8bdb-104">Es gibt drei Gründe zum Gruppieren von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-104">There are three reasons to group controls.</span></span> <span data-ttu-id="e8bdb-105">Eine ist die visuelle Gruppierung von verwandten Form-Elemente für eine übersichtliche Benutzeroberfläche. eine andere ist die programmgesteuerte Gruppieren von Optionsfeldern z. B. das letzte ist für die Steuerelemente zur Entwurfszeit als Einheit verschieben.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8bdb-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e8bdb-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e8bdb-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e8bdb-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="e8bdb-109">Um eine Gruppe von Steuerelementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-109">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="e8bdb-110">Ziehen Sie eine <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte der Toolbox auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2.  <span data-ttu-id="e8bdb-111">Fügen Sie weitere Steuerelemente hinzu, um den Bereich, Zeichnen im Auswahlbereich.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="e8bdb-112">Wenn Sie vorhandene Steuerelemente verfügen, die Sie in einem Panel schließen möchten, können Sie wählen alle Steuerelemente, verschieben Sie sie in die Zwischenablage, wählen Sie die <xref:System.Windows.Forms.Panel> steuern, und fügen Sie sie in den Bereich.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="e8bdb-113">Sie können auch in den Bereich ziehen.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-113">You can also drag them into the panel.</span></span>  
  
3.  <span data-ttu-id="e8bdb-114">(Optional) Wenn Sie einen Rahmen um einen Bereich hinzufügen möchten, legen Sie dessen <xref:System.Windows.Forms.BorderStyle> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="e8bdb-115">Es gibt drei Optionen: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, und <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="e8bdb-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bdb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8bdb-116">See Also</span></span>  
 [<span data-ttu-id="e8bdb-117">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e8bdb-117">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="e8bdb-118">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e8bdb-118">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="e8bdb-119">Gewusst wie: Festlegen des Hintergrunds eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="e8bdb-119">How to: Set the Background of a Panel</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
