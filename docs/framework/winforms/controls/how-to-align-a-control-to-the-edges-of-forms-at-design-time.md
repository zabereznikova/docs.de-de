---
title: 'Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 8ca6fd64edbd73301fd298f42c3d4d97d021888a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331862"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Vorgehensweise: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit
Können Sie vornehmen, das Steuerelement an Ihre Formen ausrichten, durch Festlegen der <xref:System.Windows.Forms.Control.Dock%2A>. Diese Eigenschaft legt fest, wo auf dem Formular das Steuerelement sich befindet. Die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft kann auf einen der folgenden Werte festgelegt werden:  
  
|Einstellung|Auswirkung auf das Steuerelement|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Wird im unteren Bereich des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Füllt den gesamten verbleibenden Platz im Formular aus.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Wird an der linken Seite des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.None>|Wird nicht angedockt und wird angezeigt, an dem vom angegebenen Speicherort der <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Wird an der rechten Seite des Formulars angedockt.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Wird im oberen Bereich des Formulars angedockt.|  
  
 Diese Werte können auch im Code festgelegt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern](how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>Die Dock-Eigenschaft für das Steuerelement zur Entwurfszeit festlegen  
  
1. Wählen Sie in der Windows Forms-Designer das Steuerelement ein.  
  
2. In der **Eigenschaften** klicken, die der Dropdown-Feld neben dem <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.  
  
     Eine grafische Benutzeroberfläche, die die sechs möglichen darstellt <xref:System.Windows.Forms.Control.Dock%2A> Einstellungen wird angezeigt.  
  
3. Wählen Sie die richtige Einstellung.  
  
4. Das Steuerelement wird jetzt von der Einstellung angegebene Weise angedockt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern](how-to-align-a-control-to-the-edges-of-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Vorgehensweise: Verankern von Steuerelementen in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
