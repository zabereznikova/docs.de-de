---
title: "Übersicht über das NumericUpDown-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1afb128fd5e098a59fa2636f09998a2a463c926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a>Übersicht über das NumericUpDown-Steuerelement (Windows Forms)
Die <xref:System.Windows.Forms.NumericUpDown> -Steuerelement sieht wie eine Kombination aus einem Textfeld und einem pfeilepaar zusammenlaufen, die der Benutzer klicken kann, um einen Wert anzupassen. Das Steuerelement zeigt an, und legt einen einzelnen numerischen Wert aus einer Liste von Optionen für feste numerischen Werten. Der Benutzer kann zu erhöhen und verringern Sie die Anzahl durch Klicken auf den nach-oben und nach unten weisenden Pfeil, durch Drücken der nach-oben und nach unten-Taste oder durch Eingabe einer Zahl in die Text-Feld-Teil des Steuerelements. Durch Drücken der nach-oben-Taste wird die Zahl für die maximale Anzahl; durch Drücken der nach-unten-Taste wird die Zahl in Richtung der Mindestwert.  
  
 Dieses Steuerelement ist ein naheliegend aufgrund seiner vielseitigen Funktionen z. B. an, wenn Sie ein Volume-Steuerelement für einen Musik-Player-Anwendung erstellen möchten. Die <xref:System.Windows.Forms.NumericUpDown> Steuerelement wird in vielen Anwendungen für Windows-Systemsteuerung verwendet.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Die Zahlen im Textfeld des Steuerelements angezeigten können in einer Vielzahl von Formaten, z. B. eine Hexadezimalzahl sein. Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md). Die wichtigsten Eigenschaften des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (Standardwert 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (Standardwert 0), und <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (Standardwert 1). Die <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft legt die aktuelle Anzahl, die im Steuerelement ausgewählt. Die <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Eigenschaft legt fest, wie die Anzahl von klickt der Benutzer auf eine nach-oben oder nach-unten angepasst wird. Wenn deaktiviert das Steuerelement den Fokus verschoben wird, wird die Eingabe für die minimalen und maximalen numerischen Werte überprüft. Sie können die Geschwindigkeit, die das Steuerelement über Zahlen, verschoben, wenn der Benutzer die auf- oder nach-unten, erhöhen, mit der <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> Eigenschaft. Die wichtigsten Methoden des Steuerelements sind <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
