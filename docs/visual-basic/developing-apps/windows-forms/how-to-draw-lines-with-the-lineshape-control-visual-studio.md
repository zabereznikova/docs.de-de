---
title: 'Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587344"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="26147-102">Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="26147-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="26147-103">Sie können die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement horizontale, vertikale oder diagonale Linien in einem Formular oder Container zu zeichnen, sowohl zur Entwurfszeit und zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="26147-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="26147-104">**Hinweis** Computers möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio Schnittstellenelemente anzeigen in den folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="26147-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="26147-105">Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig.</span><span class="sxs-lookup"><span data-stu-id="26147-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="26147-106">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="26147-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="26147-107">Zum Zeichnen einer Linie zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="26147-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="26147-108">Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** ziehen Sie in einem Formular oder Containersteuerelement.</span><span class="sxs-lookup"><span data-stu-id="26147-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="26147-109">Ziehen Sie den Ziehpunkt, und zuschnittpunkt, um die Größe und position der Zeile.</span><span class="sxs-lookup"><span data-stu-id="26147-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="26147-110">Sie können auch die Größe und position der Linie durch Ändern der `X1`, `X2`, `Y1`, und `Y2` Eigenschaften in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="26147-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="26147-111">In der **Eigenschaften** Fenster optional zusätzliche Eigenschaften festlegen, wie z. B. `BorderStyle` oder `BorderColor` so ändern Sie die Darstellung der Linie.</span><span class="sxs-lookup"><span data-stu-id="26147-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="26147-112">Zum Zeichnen einer Linie zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="26147-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="26147-113">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="26147-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="26147-114">In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Microsoft.VisualBasic.PowerPacks.VS**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="26147-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="26147-115">In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:</span><span class="sxs-lookup"><span data-stu-id="26147-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="26147-116">Fügen Sie den folgenden Code in ein `Event`-Verfahren ein:</span><span class="sxs-lookup"><span data-stu-id="26147-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="26147-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26147-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="26147-118">Einführung in das Line-Steuerelement und das Shape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="26147-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="26147-119">Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="26147-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
