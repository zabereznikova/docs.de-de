---
title: 'Gewusst wie: Festlegen der Aktivierreihenfolge in Windows Forms'
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
ms.openlocfilehash: ca5b9c29d9138d4e17fbf187e35951dbec614aab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Gewusst wie: Festlegen der Aktivierreihenfolge in Windows Forms
Die Aktivierreihenfolge ist die Reihenfolge, in der ein Benutzer von einem Steuerelement zu einem anderen Fokus durch Drücken der TAB-Taste. Jedes Formular verfügt über eine eigene Aktivierreihenfolge. Standardmäßig ist die Reihenfolge der Registerkarten identisch mit der Reihenfolge, in der Sie die Steuerelemente erstellt. Reihenfolge der Registerkarten Nummerierung beginnt mit 0 (null).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Festlegen die Aktivierreihenfolge eines Steuerelements  
  
1.  Auf der **Ansicht** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
     Dadurch wird den Auswahlmodus Reihenfolge der Registerkarten auf dem Formular aktiviert. Eine Zahl (darstellt der <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft) wird in der oberen linken Ecke der einzelnen Steuerelemente angezeigt.  
  
2.  Klicken Sie auf die Steuerelemente nacheinander, um die Reihenfolge der Registerkarten herstellen soll.  
  
    > [!NOTE]
    >  Die Position eines Steuerelements in der Aktivierreihenfolge kann auf einen beliebigen Wert größer als oder gleich 0 festgelegt werden. Beim Auftreten von Duplikaten wird die Z-Reihenfolge von zwei Steuerelementen wird ausgewertet, und das Steuerelement an erster Stelle wird zuerst im Registerkartenformat. (Z-Reihenfolge ist die Schichtung der Steuerelemente in einem Formular auf das Formular z-Achse [Tiefe]. Die Z-Reihenfolge bestimmt, welche Steuerelemente vor anderen Steuerelemente sind.) Weitere Informationen auf der Z-Reihenfolge finden Sie unter [Überlagern von Objekten in Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).  
  
3.  Wenn Sie fertig sind, klicken Sie auf **Aktivierreihenfolge** auf die **Ansicht** Menü erneut aus, um die Registerkarte Reihenfolge Modus zu verlassen.  
  
    > [!NOTE]
    >  Steuerelemente, die den Fokus erhalten können nicht als auch deaktivierte und nicht sichtbare Steuerelemente verfügen nicht über eine <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft und sind nicht in der Aktivierreihenfolge enthalten. Diese Steuerelemente werden übersprungen, da ein Benutzer die TAB-Taste drückt.  
  
 Alternativ kann Aktivierreihenfolge festgelegt werden, in das Eigenschaften unter Verwendung der <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft. Die <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft eines Steuerelements bestimmt, wo es positioniert ist, in der Aktivierreihenfolge. Wird standardmäßig das erste Steuerelement gezeichnet wurde eine <xref:System.Windows.Forms.Control.TabIndex%2A> Wert von 0 (null) hat die zweite eine <xref:System.Windows.Forms.Control.TabIndex%2A> 1 und So weiter.  
  
 Darüber hinaus wird standardmäßig ein <xref:System.Windows.Forms.GroupBox> Steuerelement verfügt über eine eigene <xref:System.Windows.Forms.Control.TabIndex%2A> Wert, der eine ganze Zahl ist. Ein <xref:System.Windows.Forms.GroupBox> Steuerelement selbst keine Fokus zur Laufzeit. Deshalb jedes Steuerelement in ein <xref:System.Windows.Forms.GroupBox> verfügt über einen eigenen Decimal <xref:System.Windows.Forms.Control.TabIndex%2A> Wert.0 ab. Natürlich als die <xref:System.Windows.Forms.Control.TabIndex%2A> von einem <xref:System.Windows.Forms.GroupBox> Steuerelement erhöht wird, werden der darin enthaltenen Steuerelemente entsprechend erhöht werden. Wenn Sie geändert haben eine <xref:System.Windows.Forms.Control.TabIndex%2A> Wert zwischen 5 und 6, die <xref:System.Windows.Forms.Control.TabIndex%2A> Wert des ersten Steuerelements in einer Gruppe, die automatisch in 6.0 usw. geändert werden.  
  
 Schließlich kann Kontrolle über die zahlreichen auf dem Formular in der Aktivierreihenfolge übersprungen werden. In der Regel Drücken von TAB nacheinander zur Laufzeit wählt jedes Steuerelement in der Aktivierreihenfolge. Durch das Deaktivieren der <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft, können Sie ein Steuerelement in der Aktivierreihenfolge des Formulars vornehmen.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>So entfernen Sie ein Steuerelement aus der Aktivierreihenfolge  
  
1.  Legen Sie das Steuerelement <xref:System.Windows.Forms.Control.TabStop%2A> Eigenschaft `false` im Eigenschaftenfenster angezeigt.  
  
     Ein Steuerelement, dessen <xref:System.Windows.Forms.Control.TabStop%2A> Eigenschaft vorsieht `false` weiterhin seine Position in der Aktivierreihenfolge verwaltet, auch wenn das Steuerelement wird übersprungen, wenn Sie die Steuerelemente mit der TAB-Taste durchlaufen.  
  
    > [!NOTE]
    >  Eine Gruppe von Optionsfeldern verfügt über eine einzelne Registerkarte zur Laufzeit zu beenden. Die Schaltfläche mit den ausgewählten (also auf die Schaltfläche mit seine <xref:System.Windows.Forms.RadioButton.Checked%2A> -Eigenschaftensatz auf `true`) hat seine <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft automatisch festgelegt, um `true`, während die anderen Schaltflächen haben ihre <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaftensatz auf `false`. Weitere Informationen zum Gruppieren <xref:System.Windows.Forms.RadioButton> -Steuerelemente finden Sie unter [gruppieren "RadioButton" Steuerelementen in Windows Forms-Funktion als ein Satz](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
