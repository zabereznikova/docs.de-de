---
title: 'Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f170250dde2f6db31ed68908936c0e9714a7e846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a>Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement (Visual Studio)
Sie können die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Steuerelement horizontale, vertikale oder diagonale Linien in einem Formular oder Container zu zeichnen, sowohl zur Entwurfszeit und zur Laufzeit.  
  
 **Hinweis** Computers möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio Schnittstellenelemente anzeigen in den folgenden Anweisungen. Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-draw-a-line-at-design-time"></a>Zum Zeichnen einer Linie zur Entwurfszeit  
  
1.  Ziehen Sie die <xref:Microsoft.VisualBasic.PowerPacks.LineShape> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** ziehen Sie in einem Formular oder Containersteuerelement.  
  
2.  Ziehen Sie den Ziehpunkt, und zuschnittpunkt, um die Größe und position der Zeile.  
  
     Sie können auch die Größe und position der Linie durch Ändern der `X1`, `X2`, `Y1`, und `Y2` Eigenschaften in der **Eigenschaften** Fenster.  
  
3.  In der **Eigenschaften** Fenster optional zusätzliche Eigenschaften festlegen, wie z. B. `BorderStyle` oder `BorderColor` so ändern Sie die Darstellung der Linie.  
  
### <a name="to-draw-a-line-at-run-time"></a>Zum Zeichnen einer Linie zur Laufzeit  
  
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
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [Einführung in das Line-Steuerelement und das Shape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
