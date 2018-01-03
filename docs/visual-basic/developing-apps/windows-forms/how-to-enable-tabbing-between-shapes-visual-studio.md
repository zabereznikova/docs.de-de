---
title: 'Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0b1e8b0378e65becd80324491632ecd8dbffdbbf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="c2129-102">Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="c2129-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="c2129-103">Die Linien- und Formsteuerelemente keine `TabStop` oder `TabIndex` Eigenschaften, aber Sie können weiterhin aktivieren Tabulator-zwischen ihnen.</span><span class="sxs-lookup"><span data-stu-id="c2129-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="c2129-104">Im folgenden Beispiel wird die STRG-Taste und die TAB-Taste drücken zwischen Formen Registerkarte; zwischen den Schaltflächen Registerkarte wird nur die TAB-Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="c2129-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2129-105">Auf Ihrem Computer werden möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio angezeigt als die in den folgenden Anweisungen aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="c2129-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="c2129-106">Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig.</span><span class="sxs-lookup"><span data-stu-id="c2129-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="c2129-107">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c2129-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="c2129-108">So aktivieren Sie die TAB-Taste zwischen Formen</span><span class="sxs-lookup"><span data-stu-id="c2129-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="c2129-109">Ziehen Sie drei <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelemente und zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** zu einem Formular.</span><span class="sxs-lookup"><span data-stu-id="c2129-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="c2129-110">In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:</span><span class="sxs-lookup"><span data-stu-id="c2129-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="c2129-111">Fügen Sie den folgenden Code in eine Ereignisprozedur:</span><span class="sxs-lookup"><span data-stu-id="c2129-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="c2129-112">Fügen Sie den folgenden Code in die `Button1_PreviewKeyDown` Ereignisprozedur:</span><span class="sxs-lookup"><span data-stu-id="c2129-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c2129-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2129-113">See Also</span></span>  
 [<span data-ttu-id="c2129-114">Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2129-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="c2129-115">Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2129-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="c2129-116">Einführung in das Line-Steuerelement und das Shape-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2129-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
