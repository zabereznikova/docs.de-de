---
title: 'Vorgehensweise: Festlegen der Aktivierreihenfolge in Windows Forms'
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
ms.openlocfilehash: 3f566dfb5dbc118c5a6be7f874b5b4857756075a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705878"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Vorgehensweise: Festlegen der Aktivierreihenfolge in Windows Forms
Die Aktivierreihenfolge ist die Reihenfolge, in der ein Benutzer den Fokus von einem Steuerelement zu einem anderen wechselt durch Drücken der TAB-Taste. Jedes Formular verfügt über eine eigene Aktivierreihenfolge. Standardmäßig entspricht die Aktivierreihenfolge der Reihenfolge, in der Sie die Steuerelemente erstellt. Aktivierreihenfolge Nummerierung beginnt mit 0 (null).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-tab-order-of-a-control"></a>Festlegen die Aktivierreihenfolge eines Steuerelements  
  
1.  Auf der **Ansicht** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
     Dadurch wird den Auswahlmodus der Aktivierreihenfolge auf dem Formular aktiviert. Eine Zahl (darstellt der <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft) in der oberen linken Ecke eines Steuerelements angezeigt wird.  
  
2.  Klicken Sie auf die Steuerelemente, nacheinander, um die Aktivierreihenfolge herstellen sollen.  
  
    > [!NOTE]
    >  Die Position eines Steuerelements in der Aktivierreihenfolge kann auf einen beliebigen Wert größer als oder gleich 0 festgelegt werden. Beim Auftreten von Duplikaten die Z-Reihenfolge der beiden Steuerelemente ausgewertet, und das Steuerelement im Vordergrund ist zunächst im Registerkartenformat. (Die Z-Reihenfolge ist für die Schichtung der Steuerelemente in einem Formular entlang des Formulars z-Achse [Tiefe]. Die Z-Reihenfolge bestimmt, welche Steuerelemente vor den anderen Steuerelementen sind.) Weitere Informationen zur Z-Anordnung finden Sie unter [Überlagern von Objekten in Windows Forms](how-to-layer-objects-on-windows-forms.md).  
  
3.  Wenn Sie fertig sind, klicken Sie auf **Aktivierreihenfolge** auf die **Ansicht** im Menü erneut aus, um die Reihenfolge registerkartenmodus lassen.  
  
    > [!NOTE]
    >  Steuerelemente, die den Fokus erhalten können nicht als auch deaktivierte und nicht sichtbare Steuerelemente müssen keine <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft und sind nicht in der Aktivierreihenfolge enthalten. Wenn der Benutzer die TAB-Taste drückt, wird diese Steuerelemente werden übersprungen.  
  
 Alternativ kann Aktivierreihenfolge festgelegt werden, in den Eigenschaften unter Verwendung der <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft. Die <xref:System.Windows.Forms.Control.TabIndex%2A> Eigenschaft eines Steuerelements bestimmt, wo es positioniert ist, in der Aktivierreihenfolge. Standardmäßig das erste Steuerelement gezeichnet hat eine <xref:System.Windows.Forms.Control.TabIndex%2A> Wert von 0 (null), die die zweite hat eine <xref:System.Windows.Forms.Control.TabIndex%2A> 1 und So weiter.  
  
 Darüber hinaus wird standardmäßig ein <xref:System.Windows.Forms.GroupBox> Steuerelement verfügt über eine eigene <xref:System.Windows.Forms.Control.TabIndex%2A> -Wert, der eine ganze Zahl ist. Ein <xref:System.Windows.Forms.GroupBox> -Steuerelement selbst kann nicht den Fokus haben, zur Laufzeit. Daher jedes Steuerelement eine <xref:System.Windows.Forms.GroupBox> verfügt über eine eigene Decimal <xref:System.Windows.Forms.Control.TabIndex%2A> Wert.0 ab. Natürlich als die <xref:System.Windows.Forms.Control.TabIndex%2A> von einem <xref:System.Windows.Forms.GroupBox> -Steuerelements erhöht wird, werden der darin enthaltenen Steuerelemente entsprechend erhöht werden. Wenn Sie geändert haben eine <xref:System.Windows.Forms.Control.TabIndex%2A> Wert zwischen 5 und 6, die <xref:System.Windows.Forms.Control.TabIndex%2A> Wert, der das erste Steuerelement in der Gruppe ändert sich automatisch in 6.0 und So weiter.  
  
 Schließlich kann jedes Steuerelement der zahlreichen in Ihrem Formular in der Aktivierreihenfolge übersprungen werden. In der Regel Drücken von TAB nacheinander an die Laufzeit wählt jedes Steuerelement in der Aktivierreihenfolge. Durch Deaktivieren der <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft, können Sie ein Steuerelement in der Aktivierreihenfolge des Formulars übergeben werden, über vornehmen.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>So entfernen Sie ein Steuerelement aus der Aktivierreihenfolge  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.TabStop%2A> Eigenschaft `false` im Eigenschaftenfenster angezeigt.  
  
     Ein Steuerelement, dessen <xref:System.Windows.Forms.Control.TabStop%2A> eingestellt wurde `false` verwaltet seine Position in der Aktivierreihenfolge nach wie vor, auch wenn das Steuerelement wird übersprungen, wenn Sie die Steuerelemente mit der TAB-Taste durchlaufen.  
  
    > [!NOTE]
    >  Eine Gruppe von Optionsfeldern verfügt über eine einzelne Registerkarte, die zur Laufzeit zu beenden. Die ausgewählte Schaltfläche (, also auf die Schaltfläche mit der <xref:System.Windows.Forms.RadioButton.Checked%2A> -Eigenschaft auf festgelegt `true`) verfügt über seine <xref:System.Windows.Forms.Control.TabStop%2A> Eigenschaft automatisch festgelegt, um `true`, während die anderen Schaltflächen haben ihre <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft auf festgelegt `false`. Weitere Informationen zum Gruppieren <xref:System.Windows.Forms.RadioButton> Steuerelemente finden Sie [Gruppieren von Windows Forms RadioButton-Steuerelementen in als Satz](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).  
  
## <a name="see-also"></a>Siehe auch
- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
