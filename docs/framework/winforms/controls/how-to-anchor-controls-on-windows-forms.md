---
title: 'Gewusst wie: Verankern von Steuerelementen in Windows Forms'
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
ms.openlocfilehash: 3d0885ac3acde6732a5c059063f992913a98b9c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Gewusst wie: Verankern von Steuerelementen in Windows Forms
Wenn Sie ein Formular entwerfen, die der Benutzer zur Laufzeit ändern kann, sollten die Steuerelemente im Formular Größe und ordnungsgemäß neu zu positionieren. Zum Ändern der Größe von Steuerelementen dynamisch mit dem Formular können Sie die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft von Windows Forms-Steuerelementen. Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft definiert ein Ankerposition für das Steuerelement. Wenn ein Steuerelement einem Formular verankert ist und der Größe des Formulars, behält das Steuerelement den Abstand zwischen dem Steuerelement und dem Anker Positionen an. Angenommen, Sie haben eine <xref:System.Windows.Forms.TextBox> Steuerelement, das den linken, rechten und unteren Rand des Formulars verbunden ist wie die Größe des Formulars die <xref:System.Windows.Forms.TextBox> ändert die Größe horizontal steuern, sodass er die gleiche Distanz vom die rechten und linken Rand des Formulars verwaltet. Darüber hinaus wird das Steuerelement vertikal positioniert, sodass am Speicherort stets die gleiche Distanz vom unteren Rand des Formulars. Wenn ein Steuerelement verankert ist, und der Größe des Formulars, wird die Position des Steuerelements relativ zu den Rändern des Formulars geändert.  
  
 Die <xref:System.Windows.Forms.Control.Anchor%2A> -Eigenschaft interagiert mit den <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-anchor-a-control-on-a-form"></a>Um ein Steuerelement in einem Formular zu verankern.  
  
1.  Wählen Sie das Steuerelement, verankert werden sollen.  
  
    > [!NOTE]
    >  Sie können mehrere Steuerelemente, die gleichzeitig durch Drücken der STRG-Taste auf jedes Steuerelement, um ihn auszuwählen und dann folgen den Rest dieses Verfahrens verankern.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaft.  
  
     Ein Editor wird angezeigt, in der ein Kreuz angezeigt.  
  
3.  Um einen Anker festzulegen, klicken Sie auf die oben, links, rechts oder unten im Abschnitt die kreuzfilterrichtung.  
  
     Steuerelemente sind oben verankert und wird standardmäßig links.  
  
4.  Um eine Seite des Steuerelements zu löschen, die verankert wurde, klicken Sie auf diese Arm für die kreuzfilterrichtung.  
  
5.  Schließen der <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaften-Editor, klicken Sie auf die <xref:System.Windows.Forms.Control.Anchor%2A> Eigenschaftsname erneut aus.  
  
 Wenn das Formular zur Laufzeit angezeigt wird, wird das Steuerelement an die gleiche Distanz vom Rand des Formulars positioniert bleiben. Der Abstand zwischen dem verankerten bleibt dasselbe immer, wie der Abstand definiert, wenn das Steuerelement in Windows Forms-Designer positioniert ist.  
  
> [!NOTE]
>  Bestimmte Steuerelemente, z. B. die <xref:System.Windows.Forms.ComboBox> steuern, besteht ein Limit, der Höhe. Verankern das Steuerelement an das Ende seiner Formular oder Containersteuerelement kann nicht das Steuerelement seine Höhe überschreiten erzwingen.  
  
 Geerbte Steuerelemente muss `Protected` verankert werden können. Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen `Modifiers` Eigenschaft in der **Eigenschaften** Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Gewusst wie: Andocken von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen mithilfe von Abständen, Rändern und der AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
