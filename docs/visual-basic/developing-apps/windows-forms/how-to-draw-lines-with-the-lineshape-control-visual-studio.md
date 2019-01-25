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
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Vorgehensweise: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)
Sie können die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement zum Zeichnen von horizontaler, vertikalen oder diagonaler Linien in einem Formular oder Container, sowohl zur Entwurfszeit und zur Laufzeit.  
  
 **Beachten Sie** auf Ihrem Computer möglicherweise angezeigt andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio Elemente der Benutzeroberfläche in den folgenden Anweisungen. Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-draw-a-line-at-design-time"></a>Zeichnen eine Linie zur Entwurfszeit  
  
1.  Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** ziehen Sie in ein Formular oder Containersteuerelement.  
  
2.  Ziehen Sie die Größe und zuschnittpunkt, um die Größe und position der Zeile.  
  
     Sie können auch die Größe und position der Linie durch Ändern der `X1`, `X2`, `Y1`, und `Y2` Eigenschaften in der **Eigenschaften** Fenster.  
  
3.  In der **Eigenschaften** optional legen zusätzliche Eigenschaften wie z. B. `BorderStyle` oder `BorderColor` so ändern Sie die Darstellung der Linie.  
  
### <a name="to-draw-a-line-at-run-time"></a>Zeichnen eine Linie zur Laufzeit  
  
1.  Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .  
  
2.  In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Microsoft.VisualBasic.PowerPacks.VS**, und klicken Sie dann auf **OK**.  
  
3.  In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Fügen Sie den folgenden Code in ein `Event`-Verfahren ein:  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [Einführung in das Line-Steuerelement und das Shape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [Vorgehensweise: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
