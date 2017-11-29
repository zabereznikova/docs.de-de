---
title: "Übersicht über das SplitContainer-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SplitContainer
helpviewer_keywords: SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f18c46c85ed840b6625d9ed754d1d036a80975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Übersicht über das SplitContainer-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind. Wenn sich der Mauszeiger über der Leiste befindet, ändert sich seine Form und zeigt an, dass die Leiste verschiebbar ist.  
  
> [!IMPORTANT]
>  In der **Toolbox**, <xref:System.Windows.Forms.SplitContainer> steuern ersetzt die <xref:System.Windows.Forms.Splitter> Steuerelement, das in der vorherigen Version von war [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]. Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement ist dem <xref:System.Windows.Forms.Splitter>-Steuerelement vorzuziehen. Die <xref:System.Windows.Forms.Splitter> Klasse dient weiterhin in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] für Kompatibilität mit vorhandenen Anwendungen, aber wir empfehlen Ihnen die Verwendung stark der <xref:System.Windows.Forms.SplitContainer> Steuerelement für neue Projekte.  
  
 Mit der <xref:System.Windows.Forms.SplitContainer> -Steuerelement, können Sie komplexe Benutzeroberflächen erstellen; häufig bestimmt die Auswahl in einem Fensterbereich, welche Objekte im anderen Fensterbereich angezeigt werden. Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen. Mit zwei Bereichen können Sie die Informationen in Bereichen aggregieren, und das Balken- oder "Splitter" erleichtert es Benutzern, die Größe der Bereiche ändern.  
  
 Mehrere <xref:System.Windows.Forms.SplitContainer> Steuerelement kann auch geschachtelt werden können und mit der zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement dienstorientierten horizontal, oberen und unteren Bereiche zu erstellen.  
  
 Beachten Sie, den <xref:System.Windows.Forms.SplitContainer> Steuerelement ist Tastatur standardmäßig; Benutzer können die Pfeiltasten zum Verschieben des Splitters, wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaftensatz auf `false`.  
  
 Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft von der <xref:System.Windows.Forms.SplitContainer> Steuerelement bestimmt die Richtung des Splitters, nicht des Steuerelements selbst. Daher, wenn diese Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.Orientation.Vertical>, verläuft der Splitter von oben nach unten, links und rechts Bereiche erstellen.  
  
 Achten Sie außerdem darauf, den Wert von der <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> Eigenschaft variiert abhängig vom Wert der <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> Eigenschaft.  
  
 Sie können auch die Größe und die Verschiebung der Einschränken der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Die <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> Eigenschaft bestimmt, welcher Bereich bleibt die gleiche Größe nach der <xref:System.Windows.Forms.SplitContainer> die Größe des Steuerelements wird geändert, und die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> Eigenschaft bestimmt, ob der Splitter durch die Tastatur oder Maus verschiebbar ist.  
  
> [!NOTE]
>  Auch wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaftensatz auf `true`, Splitters möglicherweise immer noch verschoben werden, programmgesteuert, z. B. mithilfe der <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> Eigenschaft.  
  
 Schließlich jeder Bereich, der die <xref:System.Windows.Forms.SplitContainer> Steuerelement verfügt über Eigenschaften, deren individuelle Größe zu bestimmen.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>-Eigenschaft|Bestimmt der Bereich, das unverändert bleibt nach der Größe der <xref:System.Windows.Forms.SplitContainer> Größe des Steuerelements geändert.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft|Bestimmt, ob der Splitter mit der Tastatur oder Maus verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A>-Eigenschaft|Bestimmt, ob der Splitter vertikal oder horizontal angeordnet sind.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>-Eigenschaft|Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>-Eigenschaft|Bestimmt die minimale Entfernung in Pixel, dass der Splitter vom Benutzer verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>-Eigenschaft|Bestimmt die Breite des Splitters in Pixel an.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving>-Ereignis|Tritt auf, wenn der Splitter verschoben werden.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved>-Ereignis|Tritt auf, wenn der Splitter verschoben wurde.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [SplitContainer-Steuerelement-Beispiel](http://msdn.microsoft.com/en-us/9015fad0-7108-4d85-a83a-a72d038c4f65)
