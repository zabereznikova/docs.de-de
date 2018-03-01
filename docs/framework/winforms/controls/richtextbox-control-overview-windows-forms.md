---
title: "Übersicht über das RichTextBox-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6ed04ab478cc6c20d88ec97934f5e45528558c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="richtextbox-control-overview-windows-forms"></a>Übersicht über das RichTextBox-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement zum Anzeigen, eingeben und Bearbeiten von Text mit Formatierung verwendet wird. Die <xref:System.Windows.Forms.RichTextBox> Steuerelement ist alles, was die <xref:System.Windows.Forms.TextBox> Steuerelement bewirkt, kann jedoch auch anzeigen, Schriftarten, Farben und Links; Text und eingebettete Bilder aus einer Datei laden und angegebene Zeichen gefunden. Die <xref:System.Windows.Forms.RichTextBox> Steuerelement wird normalerweise verwendet, geben Sie die Bearbeitung von Text und Anzeigen von Funktionen, wie Textverarbeitungsprogramm erstellten Anwendungen wie Microsoft Word. Wie die <xref:System.Windows.Forms.TextBox> -Steuerelement, das <xref:System.Windows.Forms.RichTextBox> Steuerelement Bildlaufleisten anzeigen kann jedoch im Gegensatz zu der <xref:System.Windows.Forms.TextBox> -Steuerelement, die Standardeinstellung ist horizontale und vertikale Bildlaufleisten angezeigt, nach Bedarf, und er verfügt über zusätzliche Scrollbar-Einstellungen.  
  
## <a name="working-with-the-richtextbox-control"></a>Arbeiten mit dem RichTextBox-Steuerelement  
 Wie bei der <xref:System.Windows.Forms.TextBox> Steuerelement angezeigte Text wird festgelegt, durch die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft. Die <xref:System.Windows.Forms.RichTextBox> Steuerelement verfügt über zahlreiche Eigenschaften, um Text zu formatieren. Ausführliche Informationen zu diesen Eigenschaften finden Sie unter [Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) und [Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Zum Bearbeiten von Dateien, die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> und <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> Methoden anzeigen und mehrere Dateiformate einschließlich nur-Text, Unicode-nur-Text und Rich-Text-Format (RTF) zu schreiben. Sind die möglichen Formate aufgeführt <xref:System.Windows.Forms.RichTextBoxStreamType>. Sie können die <xref:System.Windows.Forms.RichTextBox.Find%2A> Methode zum Suchen von Zeichenfolgen oder bestimmte Zeichen.  
  
 Können Sie auch eine <xref:System.Windows.Forms.RichTextBox> -Steuerelement für Weblinks durch Festlegen der <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> Eigenschaft `true` und Schreiben von Code zum Behandeln der <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Sie können verhindern, dass den Benutzer bearbeiten einiger oder aller der Text im Steuerelement durch Festlegen der <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> Eigenschaft `true`.  
  
 Können Sie rückgängig machen und wiederholen Sie die meisten Bearbeitungsvorgänge in einem <xref:System.Windows.Forms.RichTextBox> Steuerelement durch Aufrufen der <xref:System.Windows.Forms.TextBoxBase.Undo%2A> und <xref:System.Windows.Forms.RichTextBox.Redo%2A> Methoden. Die <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> Methode können Sie bestimmen, ob es sich bei der letzte Vorgang rückgängig gemachte wurde an das Steuerelement erneut angewendet werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
