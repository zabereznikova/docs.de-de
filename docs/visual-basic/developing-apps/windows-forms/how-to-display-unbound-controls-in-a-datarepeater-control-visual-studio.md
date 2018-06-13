---
title: 'Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588105"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement (Visual Studio)
Zusätzlich zur gebundene Steuerelemente möchten Sie möglicherweise andere Steuerelemente zum Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
> [!NOTE]
>  Außerdem benötigen Sie mindestens ein gebundenes Steuerelement auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> oder nichts wird zur Laufzeit angezeigt werden.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Hinzufügen von nicht gebundenen Steuerelementen zu einem DataRepeater  
  
1.  Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  Größe der Größe und Position Ziehpunkte, und positionieren Sie das Steuerelement.  
  
     Sie können auch die Größe und position des Steuerelements durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.  
  
3.  Fügen Sie mindestens ein datengebundenes Steuerelement auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeige von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Ziehen Sie ein Steuerelement aus der **Toolbox** in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt. Der innere Bereich ist der *Elementvorlage*; Steuerelemente hinzugefügt wurden, um die Vorlage werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit. Der äußere Bereich ist der *Viewport*, in denen die Elemente angezeigt, da in dieser Region hinzugefügten Steuerelemente zur Laufzeit nicht angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
