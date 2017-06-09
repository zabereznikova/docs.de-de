---
title: "Gewusst wie: Festlegen von Einz&#252;gen, h&#228;ngenden Einz&#252;gen und Abs&#228;tzen mit Aufz&#228;hlungszeichen mit dem RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - ".rtf-Dateien, Formatieren im RichTextBox-Steuerelement"
  - "Beispiele [Windows Forms], Textfelder"
  - "RichTextBox-Steuerelement [Windows Forms], Einstellen von Einzügen und Aufzählungszeichen"
  - "RTF-Dateien, Formatieren im RichTextBox-Steuerelement"
  - "Textfelder, Aufzählungszeichen"
  - "Textfelder, Festlegen von Einzügen"
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen von Einz&#252;gen, h&#228;ngenden Einz&#252;gen und Abs&#228;tzen mit Aufz&#228;hlungszeichen mit dem RichTextBox-Steuerelement von Windows&#160;Forms
Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms stellt zahlreiche Formatierungsoptionen für den in ihm angezeigten Text bereit.  Sie können markierte Absätze als Aufzählungen formatieren, indem Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>\-Eigenschaft festlegen.  Mit den Eigenschaften <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> und <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> können Sie außerdem den Einzug der Absätze relativ zum linken und rechten Rand des Steuerelements sowie zum linken Rand anderer Textzeilen festlegen.  
  
### So formatieren Sie einen Absatz als Aufzählung  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>\-Eigenschaft auf `true` fest.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### So legen Sie einen Einzug für einen Absatz fest  
  
1.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>\-Eigenschaft eine ganze Zahl fest, die den Abstand zwischen linkem Steuerelementrand und linkem Textrand in Pixel angibt.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>\-Eigenschaft eine ganze Zahl fest, die den Abstand zwischen dem linken Rand der ersten Textzeile im Absatz und dem linken Rand der folgenden Zeilen im selben Absatz in Pixel angibt.  Der Wert der <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>\-Eigenschaft wird nur auf Zeilen in einem Absatz angewendet, die nach der ersten Zeile umbrochen wurden.  
  
3.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>\-Eigenschaft eine ganze Zahl fest, die den Abstand zwischen rechtem Steuerelementrand und rechtem Textrand in Pixel angibt.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  Alle genannten Eigenschaften wirken sich auf sämtliche Absätze aus, in denen Text markiert ist, sowie auf nach der aktuellen Einfügemarke eingegebenen Text.  Wenn ein Benutzer beispielsweise ein Wort in einem Absatz markiert und dann den Einzug anpasst, wird die neue Einstellung auf den gesamten Absatz, in dem dieses Wort steht, und auf alle Absätze angewendet, die hinter diesem Absatz eingegeben werden.  Weitere Informationen über das programmgesteuerte Markieren von Text finden Sie unter [TextBoxBase.Select\-Methode](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)