---
title: Übersicht über das NumericUpDown-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 218eb685e546acac76a18450612a1601ab87276b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61805755"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Übersicht über das NumericUpDown-Steuerelement (Windows Forms)
Die <xref:System.Windows.Forms.NumericUpDown> Steuerelement sieht wie eine Kombination aus einem Textfeld und einem Paar Pfeilen, die der Benutzer klicken kann, um einen Wert anzupassen. Das Steuerelement zeigt an, und legt einen einzelnen numerischen Wert aus einer Liste von Optionen für feste numerischen Werten. Der Benutzer kann zu erhöhen und verringern Sie die Anzahl durch Klicken auf den Pfeil nach oben und nach unten weisenden Pfeil, durch Drücken der nach-oben und nach-unten-Pfeiltasten oder durch Eingabe einer Zahl in Textfeldteil des Steuerelements. Durch Drücken der nach-oben-Taste wird die Zahl für die maximale Anzahl; durch Drücken der nach-unten-Taste wird die Zahl in Richtung Minimum.  
  
 Dieses Steuerelement ist naheliegend, aufgrund der vielseitigen Funktionalität z. B. an, wenn Sie ein Volume-Steuerelement für eine Musik-Player-Anwendung erstellen möchten. Die <xref:System.Windows.Forms.NumericUpDown> Steuerelement wird in vielen Anwendungen für Windows-Systemsteuerung verwendet.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Die Zahlen im Text des Steuerelements angezeigten können in einer Vielzahl von Formaten, einschließlich Hexadezimalzahl sein. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des Formats für die NumericUpDown-Steuerelement in der Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (Standardwert 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (Standardwert 0), und <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (Standardwert: 1). Die <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft legt fest, die aktuelle Anzahl, die im Steuerelement ausgewählt. Die <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Eigenschaft legt fest, den Betrag, um die Anzahl von klickt der Benutzer auf eine nach-oben oder nach-unten angepasst wird. Wenn Fokus das Steuerelement verschoben wird, wird die Eingabe für die minimalen und maximalen numerischen Werte überprüft werden. Sie können die Geschwindigkeit, die das Steuerelement über Zahlen, verschoben werden, wenn der Benutzer die auf- bzw. ab-erhöhen, mit der <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> Eigenschaft. Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Vorgehensweise: Legen Sie das Format für das NumericUpDown-Steuerelement in Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
