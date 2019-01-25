---
title: 'Vorgehensweise: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596227"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="71664-102">Vorgehensweise: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="71664-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="71664-103">Sie können die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement zum Zeichnen von horizontaler, vertikalen oder diagonaler Linien in einem Formular oder Container, sowohl zur Entwurfszeit und zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="71664-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="71664-104">**Beachten Sie** auf Ihrem Computer möglicherweise angezeigt andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio Elemente der Benutzeroberfläche in den folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="71664-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="71664-105">Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig.</span><span class="sxs-lookup"><span data-stu-id="71664-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="71664-106">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="71664-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="71664-107">Zeichnen eine Linie zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="71664-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="71664-108">Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** ziehen Sie in ein Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="71664-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="71664-109">Ziehen Sie die Größe und zuschnittpunkt, um die Größe und position der Zeile.</span><span class="sxs-lookup"><span data-stu-id="71664-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="71664-110">Sie können auch die Größe und position der Linie durch Ändern der `X1`, `X2`, `Y1`, und `Y2` Eigenschaften in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="71664-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="71664-111">In der **Eigenschaften** optional legen zusätzliche Eigenschaften wie z. B. `BorderStyle` oder `BorderColor` so ändern Sie die Darstellung der Linie.</span><span class="sxs-lookup"><span data-stu-id="71664-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="71664-112">Zeichnen eine Linie zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="71664-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="71664-113">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="71664-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="71664-114">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Microsoft.VisualBasic.PowerPacks.VS**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="71664-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="71664-115">In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:</span><span class="sxs-lookup"><span data-stu-id="71664-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="71664-116">Fügen Sie den folgenden Code in ein `Event`-Verfahren ein:</span><span class="sxs-lookup"><span data-stu-id="71664-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="71664-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71664-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [<span data-ttu-id="71664-118">Einführung in das Line-Steuerelement und das Shape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="71664-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="71664-119">Vorgehensweise: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="71664-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
