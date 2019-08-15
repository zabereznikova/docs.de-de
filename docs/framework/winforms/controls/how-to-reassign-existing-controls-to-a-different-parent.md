---
title: 'Vorgehensweise: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039786"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Vorgehensweise: Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element
Sie können auf Ihrem Formular vorhandene Steuerelemente einem neuen Containersteuerelement zuordnen.

## <a name="to-reassign-existing-controls-to-a-different-parent"></a>Erneutes Zuweisen von vorhandenen Steuerelementen zu einem anderen übergeordneten Element

1. Ziehen Sie drei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** auf das Formular.

     Positionieren Sie sie nahe beieinander, ohne sie aber auszurichten.

2. Klicken Sie in der **Toolbox**auf das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements.

     Ziehen Sie das Symbol nicht auf das Formular.

3. Bewegen Sie den Mauszeiger in die Nähe der drei <xref:System.Windows.Forms.Button> -Steuerelemente.

     Der Mauszeiger nimmt die Form eines Fadenkreuzes an, an das das Symbol des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements angefügt ist.

4. Klicken Sie, und halten Sie die Maustaste gedrückt.

5. Ziehen Sie den Mauszeiger, um die Kontur des <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelements zu zeichnen.

6. Ziehen Sie die Kontur um die drei <xref:System.Windows.Forms.Button> -Steuerelemente.

7. Lassen Sie die Maustaste los.

     Die drei <xref:System.Windows.Forms.Button> -Steuerelemente werden jetzt in das <xref:System.Windows.Forms.FlowLayoutPanel> -Steuerelement eingefügt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
