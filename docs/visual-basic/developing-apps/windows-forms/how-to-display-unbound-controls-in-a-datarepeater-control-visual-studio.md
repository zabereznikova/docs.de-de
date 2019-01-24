---
title: 'Vorgehensweise: Zeigen Sie nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement (Visual Studio an)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730788"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Vorgehensweise: Zeigen Sie nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement (Visual Studio an)
Zusätzlich zu den gebundenen Steuerelementen, Sie möchten andere Steuerelemente zum Hinzufügen einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
> [!NOTE]
>  Außerdem benötigen Sie mindestens ein gebundenes Steuerelement auf der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> oder "nothing" wird zur Laufzeit angezeigt.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Hinzufügen von nicht gebundenen Steuerelementen zum DataRepeater  
  
1.  Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Ziehen Sie die Größe und Position Handles auf Größe, und platzieren Sie das Steuerelement.  
  
     Sie können auch die Größe und position des Steuerelements durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.  
  
3.  Fügen Sie mindestens ein vom datengebundenen Steuerelement, das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Ziehen Sie ein Steuerelement aus der **Toolbox** in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt. Der innere Bereich ist die *Elementvorlage*; Steuerelemente hinzugefügt werden, auf die Vorlage werden in jedem Element im wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit. Die äußere Region ist die *Viewport*, in denen die Elemente angezeigt, Steuerelemente, die in dieser Region hinzugefügt haben, werden nicht zur Laufzeit angezeigt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
