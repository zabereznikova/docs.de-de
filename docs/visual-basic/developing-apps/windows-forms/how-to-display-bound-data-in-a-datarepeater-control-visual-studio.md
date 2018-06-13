---
title: 'Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589866"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)
Die häufigste Verwendung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement wird zum Anzeigen von gebundener Daten aus einer Datenbank oder anderen Datenquelle.  
  
 Zusätzlich zur gebundene Steuerelemente möchten Sie möglicherweise andere Steuerelemente hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Sie können auch Binden an eine Datenquelle zur Laufzeit durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Eigenschaft `True` und Zuweisen von einer Datenquelle, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> Eigenschaft. In diesem Fall müssen Sie alle Interaktionen mit der Datenquelle zu verwalten. Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Zum Erstellen von datengebundenen DataRepeater  
  
1.  Ziehen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  Größe der Größe und Position Ziehpunkte, und positionieren Sie das Steuerelement.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt. Der obere Bereich ist die *Elementvorlage*; Steuerelemente hinzugefügt wurden, um die Vorlage werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Laufzeit. Der untere Bereich ist der *Viewport*, in die Elemente angezeigt werden soll.  
  
     Sie können auch die Größe und position des Steuerelements oder der Elementvorlage durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu. Weitere Informationen finden Sie unter [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources).  
  
4.  In der **Datenquellen** Fenster, wählen Sie den Knoten den obersten Ebene für die Tabelle, die Daten enthält, die Sie binden möchten.  
  
5.  Ändern Sie den Ablagetyp der Tabelle, die `Details` durch Klicken auf `Details` in der Dropdown-Liste für den Tabellenknoten.  
  
6.  Wählen Sie den Tabellenknoten, und ziehen Sie es in den Elementvorlagenbereich von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
     Sie können angeben, welche Typen von Steuerelementen für jedes Feld angezeigt werden. Weitere Informationen finden Sie unter [festlegen, welches Steuerelement erstellt werden, beim Ziehen aus Datenquellenfenster](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Vorgehensweise: erstellen ein Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
