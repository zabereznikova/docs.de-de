---
title: Übersicht über das NumericUpDown-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740798"
---
# <a name="numericupdown-control-overview-windows-forms"></a>Übersicht über das NumericUpDown-Steuerelement (Windows Forms)
Das <xref:System.Windows.Forms.NumericUpDown> Steuerelement sieht wie eine Kombination aus einem Textfeld und einem Paar von Pfeilen aus, auf das der Benutzer klicken kann, um einen Wert anzupassen. Das-Steuerelement zeigt einen einzelnen numerischen Wert aus einer Liste mit festgelegten numerischen Wert Optionen an und legt diesen fest. Der Benutzer kann die Zahl vergrößern und verkleinern, indem er auf die Pfeile nach oben und nach unten klickt, indem er die nach-oben-oder nach-unten-Taste drückt oder eine Zahl in das Textfeld des Steuer Elements eingeben. Durch Klicken auf die nach-oben-Taste wird die Zahl in den maximalen Wert verschoben; durch Klicken auf die nach-unten-Taste wird die Zahl in den Minimalwert verschoben.  
  
 Aufgrund der vielseitigen Funktionalität ist dieses Steuerelement eine offensichtliche Wahl, z. b. Wenn Sie ein Volume-Steuerelement für eine Music Player-Anwendung erstellen möchten. Das <xref:System.Windows.Forms.NumericUpDown>-Steuerelement wird in vielen Windows-System Steuerungsanwendungen verwendet.  
  
## <a name="key-properties-and-methods"></a>Schlüsseleigenschaften und-Methoden  
 Die im Textfeld des Steuer Elements angezeigten Zahlen können in einer Vielzahl von Formaten vorliegen, einschließlich hexadezimal. Weitere Informationen finden Sie unter Gewusst [wie: Festlegen des Formats für das Windows Forms NumericUpDown-Steuer](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)Element. Die Schlüsseleigenschaften des-Steuer Elements sind <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (Standardwert 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (Standardwert 0) und <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (Standardwert 1). Die <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft legt die aktuelle Zahl fest, die im-Steuerelement ausgewählt ist. Die <xref:System.Windows.Forms.NumericUpDown.Increment%2A>-Eigenschaft legt den Betrag fest, mit dem die Anzahl von angepasst wird, wenn der Benutzer auf einen nach-oben-oder nach-unten Wenn der Fokus vom Steuerelement bewegt wird, werden alle typisierten Eingaben mit dem minimalen und maximalen numerischen Wert überprüft. Sie können die Geschwindigkeit erhöhen, mit der das-Steuerelement durch Zahlen bewegt wird, wenn der Benutzer den Pfeil nach oben oder nach unten mit der <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>-Eigenschaft drückt. Die Schlüsselmethoden des Steuer Elements sind <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
