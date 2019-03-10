---
title: 'Vorgehensweise: Verwalten von ToolStrip-Überlauf in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 53f610a728925d454a8833a49e705818f027aec5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707273"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Vorgehensweise: Verwalten von ToolStrip-Überlauf in Windows Forms

Wenn alle Elemente in einer <xref:System.Windows.Forms.ToolStrip> Steuerelement nicht in den zugewiesenen Raum passen, können Sie Überlauffunktion aktivieren, auf die <xref:System.Windows.Forms.ToolStrip> und bestimmen das Überlaufverhalten von bestimmten <xref:System.Windows.Forms.ToolStripItem>s.

Beim Hinzufügen von <xref:System.Windows.Forms.ToolStripItem>s, die mehr Platz benötigen, als zu erfordern die <xref:System.Windows.Forms.ToolStrip> erhalten die aktuelle Größe des Formulars eine <xref:System.Windows.Forms.ToolStripOverflowButton> automatisch angezeigt wird, auf die <xref:System.Windows.Forms.ToolStrip>. Die <xref:System.Windows.Forms.ToolStripOverflowButton> angezeigt wird, und der Überlauf-aktivierten Elemente in der Dropdown-Überlauf verschoben werden. Dadurch können Sie anpassen und priorisieren wie Ihre <xref:System.Windows.Forms.ToolStrip> Elemente ordnungsgemäß anpassen, um verschiedene Größen. Sie können auch die Darstellung der Elemente ändern, wenn sie in der Überlauf geraten, mit der <xref:System.Windows.Forms.ToolStripItem.Placement%2A> und <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> Eigenschaften und die <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis. Wenn das Formular zur Entwurfszeit oder zur Laufzeit mehr Sie vergrößern <xref:System.Windows.Forms.ToolStripItem>s angezeigt werden kann, auf dem hauptblatt <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStripOverflowButton> möglicherweise ausgeblendet, bis Sie die Größe des Formulars zu reduzieren.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>Überlauf bei eines ToolStrip-Steuerelements aktivieren

- Sicherstellen, dass die <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> Eigenschaft ist nicht festgelegt, um `false` für die <xref:System.Windows.Forms.ToolStrip>. Die Standardeinstellung ist `True`.

     Wenn <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> ist `True` (Standardeinstellung), eine <xref:System.Windows.Forms.ToolStripItem> wird gesendet, um das Überlaufmenü den Dropdown-bei den Inhalt des der <xref:System.Windows.Forms.ToolStripItem> überschreitet die Breite einer horizontalen <xref:System.Windows.Forms.ToolStrip> oder die Höhe eines vertikalen <xref:System.Windows.Forms.ToolStrip>.

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Angeben von Überlaufverhalten von einem bestimmten ToolStripItem

- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStripItem> auf den gewünschten Wert. Mögliche Werte sind `Always`, `Never`, und `AsNeeded`. Die Standardeinstellung ist `AsNeeded`.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
