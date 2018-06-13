---
title: 'Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590841"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="876fc-102">Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="876fc-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="876fc-103">Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement kann angezeigt werden, in einem vertikal (vertikaler Bildlauf der Elemente) oder Horizontal (horizontaler Bildlauf der Elemente) Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="876fc-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="876fc-104">Sie können die Ausrichtung zur Entwurfszeit oder zur Laufzeit ändern, indem Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="876fc-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="876fc-105">Wenn Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft zur Laufzeit, Sie sollten auch ändern der Größe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und die untergeordneten Steuerelemente neu positionieren.</span><span class="sxs-lookup"><span data-stu-id="876fc-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="876fc-106">Wenn Sie auf Steuerelemente neu positionieren der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zur Laufzeit müssen Sie zum Aufrufen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> Methoden am Anfang und Ende des Codeblocks, der die Steuerelemente neu positioniert.</span><span class="sxs-lookup"><span data-stu-id="876fc-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="876fc-107">So ändern Sie das Layout zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="876fc-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="876fc-108">Wählen Sie in der Windows Forms-Designer die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="876fc-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="876fc-109">Wählen Sie den äußeren Rahmen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, indem Sie auf den unteren Bereich des Steuerelements nicht in der oberen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Region.</span><span class="sxs-lookup"><span data-stu-id="876fc-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="876fc-110">Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaft entweder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="876fc-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="876fc-111">So ändern Sie das Layout zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="876fc-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="876fc-112">Fügen Sie den folgenden Code, um eine Schaltfläche oder ein Menü `Click` Ereignishandler:</span><span class="sxs-lookup"><span data-stu-id="876fc-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="876fc-113">In den meisten Fällen sollten Sie zum Hinzufügen von Code ähnlich dem im Beispielabschnitt angezeigt wird, um die Größe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und Neuanordnen von Steuerelementen entsprechend die neue Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="876fc-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="876fc-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="876fc-114">Example</span></span>  
 <span data-ttu-id="876fc-115">Im folgende Beispiel wird gezeigt, wie So reagieren Sie auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> Ereignis in einem Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="876fc-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="876fc-116">Dieses Beispiel benötigen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement namens `DataRepeater1` auf ein Formular, und dass seine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> enthalten zwei <xref:System.Windows.Forms.TextBox> -Steuerelemente namens `TextBox1` und `TextBox2`.</span><span class="sxs-lookup"><span data-stu-id="876fc-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="876fc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="876fc-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [<span data-ttu-id="876fc-118">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="876fc-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="876fc-119">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="876fc-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="876fc-120">Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="876fc-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
