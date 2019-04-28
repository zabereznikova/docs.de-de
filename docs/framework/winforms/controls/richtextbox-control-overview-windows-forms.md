---
title: Übersicht über das RichTextBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0827c1919597e9eb85bfa41721676008b76564d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902498"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Übersicht über das RichTextBox-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> Steuerelement zum Anzeigen, eingeben und Bearbeiten von Text mit Formatierung verwendet wird. Die <xref:System.Windows.Forms.RichTextBox> -Steuerelement besitzt dieselben Funktionen der <xref:System.Windows.Forms.TextBox> -Steuerelement, kann jedoch auch anzeigen, Schriftarten, Farben und Links, Text und eingebettete Bilder aus einer Datei laden und nach bestimmten Zeichen suchen. Die <xref:System.Windows.Forms.RichTextBox> Steuerelement dient normalerweise zum Bereitstellen und Anzeigen von Funktionen, wie Sie Textverarbeitungsprogrammen wie Microsoft Word. Wie die <xref:System.Windows.Forms.TextBox> -Steuerelement, das <xref:System.Windows.Forms.RichTextBox> -Steuerelement Schiebeleisten können angezeigt werden, aber im Gegensatz zu der <xref:System.Windows.Forms.TextBox> -Steuerelement, die Standardeinstellung beträgt, horizontale und vertikale Scrollleisten angezeigt, je nach Bedarf und kann zusätzliche Einstellungen.  
  
## <a name="working-with-the-richtextbox-control"></a>Arbeiten mit dem RichTextBox-Steuerelement  
 Wie bei der <xref:System.Windows.Forms.TextBox> -Steuerelement angezeigte Text wird festgelegt, durch die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft. Die <xref:System.Windows.Forms.RichTextBox> -Steuerelement besitzt zahlreiche Eigenschaften, um Text zu formatieren. Weitere Informationen zu diesen Eigenschaften finden Sie unter [Vorgehensweise: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement in der Windows Forms](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) und [Vorgehensweise: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement in Windows Forms](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Zum Bearbeiten von Dateien, die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> und <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> Methoden angezeigt und mehrere Dateiformate einschließlich nur-Text, Unicode-Standardtext und Rich Text Format (RTF) geschrieben. Die möglichen Dateiformate finden Sie in <xref:System.Windows.Forms.RichTextBoxStreamType>. Sie können die <xref:System.Windows.Forms.RichTextBox.Find%2A> Methode, um die Zeichenfolgen oder bestimmten Zeichen suchen.  
  
 Können Sie auch eine <xref:System.Windows.Forms.RichTextBox> -Steuerelement für Weblinks durch Festlegen der <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> Eigenschaft `true` und Schreiben von Code zum Behandeln der <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Hyperlinks mit dem Windows Forms-RichTextBox-Steuerelement](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Sie können verhindern, dass den Benutzer bearbeiten einiger oder aller der Text im Steuerelement durch Festlegen der <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> Eigenschaft `true`.  
  
 Rückgängigmachen und wiederholen Sie die meisten Bearbeitungsvorgänge in einem <xref:System.Windows.Forms.RichTextBox> Steuerelement durch Aufrufen der <xref:System.Windows.Forms.TextBoxBase.Undo%2A> und <xref:System.Windows.Forms.RichTextBox.Redo%2A> Methoden. Die <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> Methode können Sie bestimmen, ob es sich bei der letzte Vorgang rückgängig wurde für das Steuerelement wiederhergestellt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
