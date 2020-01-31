---
title: Übersicht über das SplitContainer-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742926"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Übersicht über das SplitContainer-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind. Wenn sich der Mauszeiger über der Leiste befindet, ändert sich seine Form und zeigt an, dass die Leiste verschiebbar ist.  
  
> [!IMPORTANT]
> In der **Toolbox**ersetzt <xref:System.Windows.Forms.SplitContainer> Steuerelement das <xref:System.Windows.Forms.Splitter> Steuerelement, das in der vorherigen Version von Visual Studio vorhanden war. Das <xref:System.Windows.Forms.SplitContainer>-Steuerelement ist dem <xref:System.Windows.Forms.Splitter>-Steuerelement vorzuziehen. Die <xref:System.Windows.Forms.Splitter>-Klasse ist aus Gründen der Kompatibilität mit vorhandenen Anwendungen weiterhin in .NET Framework enthalten. Bei neuen Projekten wird jedoch ausdrücklich die Verwendung des <xref:System.Windows.Forms.SplitContainer>-Steuerelements empfohlen.  
  
 Mit dem <xref:System.Windows.Forms.SplitContainer>-Steuerelement können Sie komplexe Benutzeroberflächen erstellen. häufig wird durch eine Auswahl in einem Panel festgelegt, welche Objekte im anderen Panel angezeigt werden. Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen. Wenn Sie über zwei Panels verfügen, können Sie Informationen in Bereichen zusammenfassen, und der Balken ("Splitter") macht es Benutzern leicht, die Größe der Panels zu ändern.  
  
 Es können auch mehrere <xref:System.Windows.Forms.SplitContainer> Steuerelemente mit dem zweiten <xref:System.Windows.Forms.SplitContainer> Steuerelement horizontal ausgerichtet werden, um obere und untere Bereiche zu erstellen.  
  
 Beachten Sie, dass das <xref:System.Windows.Forms.SplitContainer> Steuerelement standardmäßig über die Tastatur zugänglich ist. Benutzer können die Pfeiltasten drücken, um den Splitter zu verschieben, wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft auf `false`festgelegt ist.  
  
 Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A>-Eigenschaft des <xref:System.Windows.Forms.SplitContainer> Steuer Elements bestimmt die Richtung des Splitters, nicht des Steuer Elements selbst. Wenn diese Eigenschaft auf <xref:System.Windows.Forms.Orientation.Vertical>festgelegt ist, wird der Splitter daher von oben nach unten ausgeführt, wobei das linke und das Rechte Panel erstellt werden.  
  
 Beachten Sie außerdem, dass der Wert der <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>-Eigenschaft in Abhängigkeit vom Wert der <xref:System.Windows.Forms.SplitContainer.Orientation%2A>-Eigenschaft variiert. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>-Eigenschaft.  
  
 Sie können auch die Größe und Bewegung des <xref:System.Windows.Forms.SplitContainer> Steuer Elements einschränken. Die <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>-Eigenschaft bestimmt, welcher Bereich nach der Größenänderung des <xref:System.Windows.Forms.SplitContainer> Steuer Elements nach der Größenänderung beibehalten wird, und die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft bestimmt, ob der Splitter von der Tastatur oder der Maus verschoben werden kann.  
  
> [!NOTE]
> Auch wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft auf `true`festgelegt ist, kann der Splitter weiterhin Programm gesteuert verschoben werden. beispielsweise mit der <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>-Eigenschaft.  
  
 Schließlich verfügt jeder Bereich des <xref:System.Windows.Forms.SplitContainer> Steuer Elements über Eigenschaften, die seine individuelle Größe bestimmen.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Häufig verwendete Eigenschaften, Methoden und Ereignisse  
  
|-Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> -Eigenschaft|Bestimmt, welcher Bereich nach der Größenänderung des <xref:System.Windows.Forms.SplitContainer> Steuer Elements unverändert bleibt.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaft|Bestimmt, ob der Splitter mit der Tastatur oder der Maus verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A> -Eigenschaft|Bestimmt, ob der Splitter vertikal oder horizontal angeordnet ist.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> -Eigenschaft|Bestimmt den Abstand vom linken oder oberen Rand bis zur verschiebbaren Splitter Leiste in Pixel.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft|Bestimmt den minimalen Abstand in Pixel, dass der Splitter vom Benutzer verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> -Eigenschaft|Bestimmt die Breite des Splitters in Pixel.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> -Ereignis|Tritt ein, wenn der Splitter verschoben wird.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> -Ereignis|Tritt ein, wenn der Splitter verschoben wurde.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer-Steuerelement](splitcontainer-control-windows-forms.md)
- [SplitContainer-Steuerelement Beispiel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
