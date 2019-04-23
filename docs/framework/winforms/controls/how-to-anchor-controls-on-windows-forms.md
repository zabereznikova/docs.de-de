---
title: 'Vorgehensweise: Verankern von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b5550aef220ece09d5486421275b19a37bfe9011
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329777"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Vorgehensweise: Verankern von Steuerelementen in Windows Forms
Wenn Sie ein Formular entwerfen, die der Benutzer zur Laufzeit ändern kann, sollten die Steuerelemente im Formular ändern der Größe und ordnungsgemäß neu zu positionieren. Steuerelemente dynamisch mit dem Formular ändern möchten, können Sie die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft von Windows Forms-Steuerelementen. Die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft definiert eine Ankerposition, die für das Steuerelement. Wenn ein Steuerelement zu einem Formular verankert ist, und des Formulars geändert wird, behält das Steuerelement den Abstand zwischen dem Steuerelement und das Anchorpositionen. Angenommen, Sie haben eine <xref:System.Windows.Forms.TextBox> -Steuerelement, das auf der linken, rechten und unteren Rand des Formulars, verankert ist, wie des Formulars geändert wird, die <xref:System.Windows.Forms.TextBox> horizontal-Steuerelements geändert wird, sodass er die gleiche Distanz vom die Rechte und linke Seite des Formulars verwaltet. Darüber hinaus wird das Steuerelement vertikal positioniert, sodass am Speicherort immer den gleichen Abstand vom unteren Rand des Formulars ist. Wenn ein Steuerelement nicht verankert ist und die Größe des Formulars ist, wird die Position des Steuerelements relativ zu den Rändern des Formulars geändert.  
  
 Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Verankert ein Steuerelement in einem Formular  
  
1. Wählen Sie das Steuerelement zu verankern.  
  
    > [!NOTE]
    >  Sie können mehrere Steuerelemente gleichzeitig durch Drücken der STRG-Taste, auf jedes Steuerelement, um ihn auszuwählen und dann folgen den Rest dieses Verfahrens verankern.  
  
2. In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.  
  
     Ein Editor wird mit einem Kreuz angezeigt.  
  
3. Um einen Anker festzulegen, klicken Sie auf die oberen, linken, rechten oder unteren Teil der Cross.  
  
     Steuerelemente sind oben verankert und wird standardmäßig links.  
  
4. Um eine Seite des Steuerelements zu löschen, die verankert ist, klicken Sie auf diese Arm, der die kreuzfilterrichtung.  
  
5. Schließen der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaften-Editor, klicken Sie auf die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaftennamen erneut.  
  
 Wenn das Formular zur Laufzeit angezeigt wird, wird die Größe des Steuerelements die gleiche Distanz vom Rand des Formulars positioniert bleiben. Der Abstand zwischen dem verankerten Rand bleibt unverändert immer, wie der Abstand definiert, wenn das Steuerelement im Windows Forms-Designer befindet.  
  
> [!NOTE]
>  Bestimmte Steuerelemente, z. B. die <xref:System.Windows.Forms.ComboBox> steuern, besteht ein Limit, deren Größe. Verankerung des Steuerelements am unteren Rand der Form oder den Container kann nicht erzwingen, dass das Steuerelement seine Höhe Grenzwert überschritten.  
  
 Geerbte Steuerelemente muss `Protected` verankert werden können. Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen `Modifiers` -Eigenschaft in der **Eigenschaften** Fenster.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Vorgehensweise: Andocken von Steuerelementen in Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md)
