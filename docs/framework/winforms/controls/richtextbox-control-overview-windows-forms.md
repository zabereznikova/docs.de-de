---
title: Übersicht über das RichTextBox-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742397"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Übersicht über das RichTextBox-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement wird zum Anzeigen, eingeben und Bearbeiten von Text mit Formatierung verwendet. Das <xref:System.Windows.Forms.RichTextBox> Steuerelement erledigt alles, was das <xref:System.Windows.Forms.TextBox> Steuerelement bewirkt, aber es kann auch Schriftarten, Farben und Links anzeigen. Laden von Text und eingebetteten Bildern aus einer Datei und suchen nach angegebenen Zeichen. Das <xref:System.Windows.Forms.RichTextBox> Steuerelement wird in der Regel verwendet, um Textbearbeitung und Features anzuzeigen, ähnlich wie bei Textverarbeitungsanwendungen wie z. b. Microsoft Word. Wie das <xref:System.Windows.Forms.TextBox> Steuerelement kann das <xref:System.Windows.Forms.RichTextBox> Steuerelement Scrollleisten anzeigen. im Gegensatz zum <xref:System.Windows.Forms.TextBox>-Steuerelement ist die Standardeinstellung jedoch, bei Bedarf sowohl horizontale als auch vertikale Scrollleisten anzuzeigen, und Sie verfügt über zusätzliche Bild Lauf Leiste-Einstellungen.  
  
## <a name="working-with-the-richtextbox-control"></a>Arbeiten mit dem RichTextBox-Steuerelement  
 Wie beim <xref:System.Windows.Forms.TextBox> Steuerelement wird der angezeigte Text durch die <xref:System.Windows.Forms.RichTextBox.Text%2A>-Eigenschaft festgelegt. Das <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Eigenschaften zum Formatieren von Text. Ausführliche Informationen zu diesen Eigenschaften finden Sie unter [Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) und [Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Um Dateien zu bearbeiten, können die Methoden <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> und <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> mehrere Dateiformate anzeigen und schreiben, einschließlich nur-Text, Unicode-nur-Text und RTF (Rich Text Format). Die möglichen Dateiformate sind in <xref:System.Windows.Forms.RichTextBoxStreamType>aufgeführt. Sie können die <xref:System.Windows.Forms.RichTextBox.Find%2A>-Methode verwenden, um Text Zeichenfolgen oder bestimmte Zeichen zu suchen.  
  
 Sie können auch ein <xref:System.Windows.Forms.RichTextBox>-Steuerelement für Webstil Verknüpfungen verwenden, indem Sie die Eigenschaft <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> auf `true` und Code schreiben, um das <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis zu behandeln. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Sie können verhindern, dass der Benutzer den Text im Steuerelement bearbeitet, indem Sie die <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A>-Eigenschaft auf `true`festlegen.  
  
 Sie können die meisten Bearbeitungsvorgänge in einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement rückgängig machen und wiederholen, indem Sie die Methoden <xref:System.Windows.Forms.TextBoxBase.Undo%2A> und <xref:System.Windows.Forms.RichTextBox.Redo%2A> aufrufen. Die <xref:System.Windows.Forms.RichTextBox.CanRedo%2A>-Methode ermöglicht Ihnen, zu bestimmen, ob der letzte Vorgang, den der Benutzer rückgängig gemacht hat, erneut auf das Steuerelement angewendet werden kann.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
