---
title: "&#220;bersicht &#252;ber das RichTextBox-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RichTextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "RichTextBox-Steuerelement [Windows Forms], Informationen über das RichTextBox-Steuerelement"
  - "Textfelder, Informationen über Textfelder"
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# &#220;bersicht &#252;ber das RichTextBox-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.RichTextBox>\-Steuerelement in Windows Forms wird Text angezeigt, eingegeben und mit Formatierungsoptionen bearbeitet.  Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement besitzt dieselben Funktionen wie das <xref:System.Windows.Forms.TextBox>\-Steuerelement. Zusätzlich können Sie damit Schriftarten, Farben und Links anzeigen, Text und eingebettete Bilder aus einer Datei laden sowie nach bestimmten Zeichen suchen.  Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement wird normalerweise zum Bereitstellen von Textbearbeitungs\- und Anzeigefeatures verwendet, die mit Textverarbeitungsprogrammen wie Microsoft Word vergleichbar sind.  Wie das <xref:System.Windows.Forms.TextBox>\-Steuerelement kann auch das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement Schiebeleisten anzeigen. Anders als beim <xref:System.Windows.Forms.TextBox>\-Steuerelement werden standardmäßig jedoch horizontale und vertikale Schiebeleisten angezeigt. Außerdem stehen mehr Einstellungen für Schiebeleisten zur Verfügung.  
  
## Arbeiten mit dem RichTextBox\-Steuerelement  
 Wie beim <xref:System.Windows.Forms.TextBox>\-Steuerelement wird der angezeigte Text ebenfalls mit der <xref:System.Windows.Forms.RichTextBox.Text%2A>\-Eigenschaft festgelegt.  Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement besitzt zahlreiche Eigenschaften zum Formatieren von Text.  Ausführliche Informationen zu diesen Eigenschaften finden Sie unter [Gewusst wie: Festlegen von Schriftartattributen für das RichTextBox\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) und [Gewusst wie: Festlegen von Einzügen, hängenden Einzügen und Absätzen mit Aufzählungszeichen mit dem RichTextBox\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md).  Um Dateien zu bearbeiten, können mit der <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>\-Methode und der <xref:System.Windows.Forms.RichTextBox.SaveFile%2A>\-Methode mehrere Dateiformate angezeigt und geschrieben werden, wie Standardtext, Unicode\-Standardtext und Rich Text Format \(RTF\).  Die möglichen Dateiformate werden in der [RichTextBoxStreamType\-Enumeration](frlrfSystemWindowsFormsRichTextBoxStreamTypeClassTopic) aufgeführt.  Mit der <xref:System.Windows.Forms.RichTextBox.Find%2A>\-Methode können Sie nach Zeichenfolgen oder bestimmten Zeichen suchen.  
  
 Sie können das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement auch für Weblinks verwenden, indem Sie für die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>\-Eigenschaft `true` festlegen und Code zur Behandlung des <xref:System.Windows.Forms.RichTextBox.LinkClicked>\-Ereignisses schreiben.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md).  Um zu verhindern, dass Benutzer den Text im Steuerelement komplett oder auch nur teilweise ändern, legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A>\-Eigenschaft `true` fest.  
  
 Sie können die meisten Bearbeitungsvorgänge in einem <xref:System.Windows.Forms.RichTextBox>\-Steuerelement rückgängig machen oder wiederherstellen, indem Sie die <xref:System.Windows.Forms.TextBoxBase.Undo%2A>\-Methode und <xref:System.Windows.Forms.RichTextBox.Redo%2A>\-Methode aufrufen.  Mit der <xref:System.Windows.Forms.RichTextBox.CanRedo%2A>\-Methode ermitteln Sie, ob der letzte rückgängig gemachte Vorgang für das Steuerelement wiederhergestellt werden kann.  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)