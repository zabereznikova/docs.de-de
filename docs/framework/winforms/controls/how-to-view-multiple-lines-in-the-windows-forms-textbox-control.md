---
title: "Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Wagenrücklauf"
  - "CRLF"
  - "Zeilenende"
  - "Zeilenvorschub"
  - "MultiLine-Eigenschaft in TextBox-Steuerelement"
  - "Zeilenumbruch"
  - "ScrollBars-Eigenschaft, In TextBox-Steuerelement"
  - "TextBox-Steuerelement [Windows Forms], Anzeigen mehrerer Zeilen"
  - "WordWrap-Eigenschaft"
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows&#160;Forms
Das <xref:System.Windows.Forms.TextBox>\-Steuerelement in Windows Forms enthält standardmäßig eine einzelne Textzeile, und es werden keine Schiebeleisten angezeigt.  Wenn der Text zu lang ist, wird er nur teilweise angezeigt.  Sie können dieses Standardverhalten ändern, indem Sie für die Eigenschaften <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> entsprechende Werte festlegen.  
  
### So zeigen Sie im TextBox\-Steuerelement einen Wagenrücklauf an  
  
-   Um in einem mehrzeiligen <xref:System.Windows.Forms.TextBox> einen Wagenrücklauf anzuzeigen, verwenden Sie die <xref:System.Environment.NewLine%2A>\-Eigenschaft.  
  
     Beachten Sie, dass die Interpretation der Escapezeichen \(\\\) sprachspezifisch ist.  Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagenrücklauf\- und Zeilenvorschubzeichen.  
  
### So lassen Sie mehrere Zeilen im TextBox\-Steuerelement anzeigen  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A>\-Eigenschaft auf `true` fest.  Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> auf `true` \(Standard\) festgelegt ist, wird der im Steuerelement enthaltene Text in einem oder mehreren Absätzen dargestellt. Andernfalls wird er in Form einer Liste angezeigt, wobei einige Zeilen, die über den Rand des Steuerelements hinausgehen, abgeschnitten sein können.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>\-Eigenschaft auf einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |----------|------------------|  
    |<xref:System.Windows.Forms.ScrollBars>|Verwenden Sie diesen Wert, wenn der Text als Absatz formatiert ist, der in den meisten Fällen vollständig im Steuerelement angezeigt werden kann.  Falls der Text aufgrund seiner Länge nicht vollständig angezeigt wird, kann der Benutzer mithilfe der Maus im Steuerelement navigieren.|  
    |<xref:System.Windows.Forms.ScrollBars>|Verwenden Sie diesen Wert, um mehrere Zeilen aufzulisten, von denen einige möglicherweise über die Breite des <xref:System.Windows.Forms.TextBox>\-Steuerelements hinausgehen.|  
    |<xref:System.Windows.Forms.ScrollBars>|Verwenden Sie diesen Wert, wenn die Liste länger ist, und die Höhe des Steuerelements überschritten wird.|  
  
3.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>\-Eigenschaft auf einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |----------|------------------|  
    |`false`|Der Text im Steuerelement wird nicht automatisch umbrochen und bis zum Erreichen des Zeilenumbruchs nach rechts fortgesetzt.  Verwenden Sie diesen Wert, wenn Sie oben den Wert <xref:System.Windows.Forms.ScrollBars> oder <xref:System.Windows.Forms.ScrollBars> für Schiebeleisten festgelegt haben.|  
    |`true` \(Standardwert\)|Es wird keine horizontale Schiebeleiste angezeigt.  Verwenden Sie diesen Wert, wenn Sie oben zur Anzeige eines oder mehrerer Absätze den Wert <xref:System.Windows.Forms.ScrollBars> oder <xref:System.Windows.Forms.ScrollBars> für Schiebeleisten festgelegt haben.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)