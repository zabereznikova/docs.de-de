---
title: Übersicht über das SplitContainer-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: d96f754c9e28455b6494c17d4d295837c008f535
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747222"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Übersicht über das SplitContainer-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind. Wenn sich der Mauszeiger über der Leiste befindet, ändert sich seine Form und zeigt an, dass die Leiste verschiebbar ist.  
  
> [!IMPORTANT]
>  In der **Toolbox**, <xref:System.Windows.Forms.SplitContainer> steuern, ersetzt die <xref:System.Windows.Forms.Splitter> Steuerelement, das in der vorherigen Version von Visual Studio war. Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement ist dem <xref:System.Windows.Forms.Splitter>-Steuerelement vorzuziehen. Die <xref:System.Windows.Forms.Splitter> Klasse befindet sich noch in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] für die Kompatibilität mit vorhandenen Anwendungen, aber wir empfehlen Ihnen die Verwendung der <xref:System.Windows.Forms.SplitContainer> Steuerelement für neue Projekte.  
  
 Mit der <xref:System.Windows.Forms.SplitContainer> Steuerelement, können Sie komplexe Benutzeroberflächen erstellen, häufig eine Auswahl in einem Bereich bestimmt, welche Objekte im anderen Fensterbereich angezeigt werden. Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen. Mit zwei Bereichen können Sie die Informationen in den Bereichen aggregieren, und der Balken oder "Splitter", erleichtert es Benutzern, die Größe der Bereiche ändern.  
  
 Mehr als eine <xref:System.Windows.Forms.SplitContainer> Steuerelement kann auch geschachtelt werden, und mit dem zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement ausgerichtet horizontal, um oberen und unteren Bereiche zu erstellen.  
  
 Beachten Sie, die die <xref:System.Windows.Forms.SplitContainer> Steuerelement standardmäßig Tastatur zugänglich ist, Benutzer können die Pfeiltasten zum Verschieben des Splitters Wenn Drücken der <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaftensatz auf `false`.  
  
 Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft der <xref:System.Windows.Forms.SplitContainer> Steuerelement bestimmt die Richtung des Splitters, nicht des Steuerelements selbst. Daher, wenn diese Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.Orientation.Vertical>, Splitters ausgeführt wird von oben nach unten, linken und rechten Bereiche erstellen.  
  
 Achten Sie außerdem, die den Wert des der <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> Eigenschaft variiert abhängig vom Wert der <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> Eigenschaft.  
  
 Sie können auch einschränken, die Größe und die Verschiebung von der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Die <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> Eigenschaft bestimmt, welchen Bereich bleibt die gleiche Größe nach der <xref:System.Windows.Forms.SplitContainer> Steuerelement wird vergrößert, und die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> Eigenschaft bestimmt, ob die Aufteilung von der Tastatur oder Maus verschiebbar ist.  
  
> [!NOTE]
>  Auch wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaftensatz auf `true`, der Splitter noch verschoben werden kann programmgesteuert, z. B. mithilfe der <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> Eigenschaft.  
  
 Schließlich jeder Bereich, der die <xref:System.Windows.Forms.SplitContainer> Steuerelement verfügt über Eigenschaften, um die einzelnen Größe zu bestimmen.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> -Eigenschaft|Bestimmt, welchen Bereich unverändert bleiben nach der Größe der <xref:System.Windows.Forms.SplitContainer> ist die Größe des Steuerelements geändert.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaft|Bestimmt, ob der Splitter mit der Tastatur oder Maus verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> -Eigenschaft|Bestimmt, ob der Splitter vertikal oder horizontal angeordnet ist.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> -Eigenschaft|Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft|Bestimmt die minimale Entfernung in Pixeln, des Splitters vom Benutzer verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> -Eigenschaft|Bestimmt die Breite des Splitters in Pixel an.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> -Ereignis|Tritt auf, wenn der Splitter verschoben werden.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> -Ereignis|Tritt auf, wenn der Splitter verschoben wurde.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
- [SplitContainer-Steuerelement-Beispiel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
