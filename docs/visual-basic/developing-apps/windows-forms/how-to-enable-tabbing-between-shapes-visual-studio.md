---
title: 'Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
ms.openlocfilehash: 437027e53cb651dd5fabe40b9d8952250f108dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589546"
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)
Die Linien- und Formsteuerelemente keine `TabStop` oder `TabIndex` Eigenschaften, aber Sie können weiterhin aktivieren Tabulator-zwischen ihnen. Im folgenden Beispiel wird die STRG-Taste und die TAB-Taste drücken zwischen Formen Registerkarte; zwischen den Schaltflächen Registerkarte wird nur die TAB-Taste drücken.  
  
> [!NOTE]
>  Auf Ihrem Computer werden möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio angezeigt als die in den folgenden Anweisungen aufgeführten. Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="to-enable-tabbing-among-shapes"></a>So aktivieren Sie die TAB-Taste zwischen Formen  
  
1.  Ziehen Sie drei <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelemente und zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** zu einem Formular.  
  
2.  In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  Fügen Sie den folgenden Code in eine Ereignisprozedur:  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Fügen Sie den folgenden Code in die `Button1_PreviewKeyDown` Ereignisprozedur:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Einführung in das Line-Steuerelement und das Shape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
