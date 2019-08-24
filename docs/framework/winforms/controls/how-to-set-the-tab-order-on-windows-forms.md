---
title: 'Vorgehensweise: Festlegen der Aktivierreihenfolge in Windows Forms'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8a0a1c76b996f10de0ca963c5d8bdc2325a3f6b6
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987104"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Vorgehensweise: Legen Sie die Aktivier Reihenfolge auf Windows Forms

Die Aktivier Reihenfolge ist die Reihenfolge, in der ein Benutzer den Fokus von einem Steuerelement zum anderen verschiebt, indem er die Tab-Taste drückt Jedes Formular hat eine eigene Aktivier Reihenfolge. Standardmäßig ist die Aktivier Reihenfolge mit der Reihenfolge identisch, in der Sie die Steuerelemente erstellt haben. Die Nummerierung der Tab-Reihenfolge beginnt bei Null.

## <a name="to-set-the-tab-order-of-a-control"></a>So legen Sie die Aktivier Reihenfolge eines Steuer Elements

1. Wählen Sie in Visual Studio im Menü **Ansicht** die Option Aktivier **Reihenfolge**aus.

   Dadurch wird der Auswahlmodus für die Registerkarten Reihenfolge im Formular aktiviert. Eine Zahl (die die <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft darstellt) wird in der oberen linken Ecke jedes Steuer Elements angezeigt.

2. Klicken Sie nacheinander auf die Steuerelemente, um die gewünschte Aktivier Reihenfolge festzulegen.

   > [!NOTE]
   > Die Position eines Steuer Elements in der Aktivier Reihenfolge kann auf einen beliebigen Wert größer oder gleich 0 (null) festgelegt werden. Wenn Duplikate auftreten, wird die z-Reihenfolge der beiden Steuerelemente ausgewertet, und das Steuerelement oben wird zuerst als Registerkarte angezeigt. (Die z-Reihenfolge ist das visuelle Schichten von Steuerelementen in einem Formular entlang der z-Achse des Formulars [Tiefe]. Die z-Reihenfolge bestimmt, welche Steuerelemente vor anderen Steuerelementen stehen.) Weitere Informationen zur z-Reihenfolge finden Sie unter [Layering objects on Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. Wenn Sie fertig sind, wählen Sie im Menü **Ansicht** erneut **Tab-Reihenfolge** aus, um den Tab-Reihen Folgen Modus zu verlassen.

   > [!NOTE]
   > Steuerelemente, die den Fokus nicht erhalten können, sowie deaktivierte und unsichtbare Steuerelemente verfügen <xref:System.Windows.Forms.Control.TabIndex%2A> nicht über eine-Eigenschaft und sind nicht in der Aktivier Reihenfolge enthalten. Wenn ein Benutzer die Tab-Taste drückt, werden diese Steuerelemente übersprungen.

Alternativ kann die Aktivier Reihenfolge in der Eigenschaftenfenster mit <xref:System.Windows.Forms.Control.TabIndex%2A> der-Eigenschaft festgelegt werden. Die <xref:System.Windows.Forms.Control.TabIndex%2A> -Eigenschaft eines-Steuer Elements bestimmt, wo es in der Aktivier Reihenfolge positioniert ist. Standardmäßig hat <xref:System.Windows.Forms.Control.TabIndex%2A> das erste gezeichnete Steuerelement den Wert 0, das zweite <xref:System.Windows.Forms.Control.TabIndex%2A> hat den Wert 1 usw.

Außerdem verfügt ein <xref:System.Windows.Forms.GroupBox> Steuerelement standardmäßig über einen eigenen <xref:System.Windows.Forms.Control.TabIndex%2A> Wert, der eine ganze Zahl ist. Ein <xref:System.Windows.Forms.GroupBox> Steuerelement kann keinen Fokus zur Laufzeit haben. Folglich hat jedes Steuerelement in <xref:System.Windows.Forms.GroupBox> einem seinen eigenen Dezimal <xref:System.Windows.Forms.Control.TabIndex%2A> Wert, beginnend mit. 0. Da <xref:System.Windows.Forms.Control.TabIndex%2A> der<xref:System.Windows.Forms.GroupBox> eines Steuer Elements inkrementiert wird, werden die darin enthaltenen Steuerelemente auf natürliche Weise inkrementiert. Wenn Sie einen <xref:System.Windows.Forms.Control.TabIndex%2A> Wert von 5 in 6 geändert haben, <xref:System.Windows.Forms.Control.TabIndex%2A> ändert sich der Wert des ersten Steuer Elements in der Gruppe automatisch in 6,0 usw.

Schließlich können alle Steuerelemente auf dem Formular in der Aktivier Reihenfolge übersprungen werden. Normalerweise wählt die Tab-Taste zur Laufzeit jedes Steuerelement in der Aktivier Reihenfolge aus. Durch Deaktivieren der <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft können Sie ein Steuerelement in der Aktivier Reihenfolge des Formulars übergeben.

## <a name="to-remove-a-control-from-the-tab-order"></a>So entfernen Sie ein Steuerelement aus Aktivier Reihenfolge

Legen Sie im Fenster <xref:System.Windows.Forms.Control.TabStop%2A> **Eigenschaften** die-Eigenschaft des Steuer Elements auf **false** fest.

Ein-Steuer <xref:System.Windows.Forms.Control.TabStop%2A> Element, dessen-Eigenschaft `false` auf festgelegt wurde, behält seine Position weiterhin in der Aktivier Reihenfolge, obwohl das Steuerelement übersprungen wird, wenn Sie die Steuerelemente mit der Tab-Taste durchlaufen.

> [!NOTE]
> Eine Optionsfeld Gruppe verfügt zur Laufzeit über einen einzelnen Tabstopp. Die ausgewählte Schaltfläche (d. h. die- <xref:System.Windows.Forms.RadioButton.Checked%2A> Schaltfläche, `true`bei der die <xref:System.Windows.Forms.Control.TabStop%2A> -Eigenschaft auf fest `true`gelegt ist) ist <xref:System.Windows.Forms.Control.TabStop%2A> für die-Eigenschaft automatisch auf `false`festgelegt, während die-Eigenschaft der anderen Schaltflächen auf Weitere Informationen zum Gruppieren <xref:System.Windows.Forms.RadioButton> von Steuerelementen finden [Sie unter Gruppieren von Windows Forms RadioButton-Steuerelementen, die als Gruppe fungieren](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
