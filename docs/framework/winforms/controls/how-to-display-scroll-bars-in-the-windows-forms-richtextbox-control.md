---
title: "Gewusst wie: Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - "RichTextBox-Steuerelement [Windows Forms], Anzeigen von Bildlaufleisten"
  - "Bildlaufleisten, Anzeigen in Steuerelementen"
  - "Textfelder, Anzeigen von Bildlaufleisten"
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement von Windows&#160;Forms
In der Standardeinstellung werden im <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms bei Bedarf horizontale und vertikale Schiebeleisten angezeigt.  Für die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>\-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>\-Steuerelements sind sieben Werte zulässig, die in der unten stehenden Tabelle beschrieben werden.  
  
### So zeigen Sie Schiebeleisten in einem RichTextBox\-Steuerelement an  
  
1.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.Multiline%2A>\-Eigenschaft `true` fest.  Wenn für die <xref:System.Windows.Forms.RichTextBox.Multiline%2A>\-Eigenschaft `false` festgelegt wurde, werden weder horizontale noch andere Arten von Schiebeleisten angezeigt.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>\-Eigenschaft einen geeigneten Wert aus der <xref:System.Windows.Forms.RichTextBoxScrollBars>\-Enumeration fest.  
  
    |Wert|Beschreibung|  
    |----------|------------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars> \(Standardwert\)|Zeigt horizontale oder vertikale bzw. horizontale und vertikale Schiebeleisten nur dann an, wenn der Text über die Breite bzw. Höhe des Steuerelements hinausgeht.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt niemals Schiebeleisten an, unabhängig von der Art der Schiebeleiste.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt nur dann eine horizontale Schiebeleiste an, wenn der Text über die Breite des Steuerelements hinausgeht.  \(Hierzu muss für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>\-Eigenschaft der Wert `false` festgelegt werden.\)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt nur dann eine vertikale Schiebeleiste an, wenn der Text über die Höhe des Steuerelements hinausgeht.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt eine horizontale Schiebeleiste an, wenn für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>\-Eigenschaft `false` festgelegt wurde.  Wenn der Text nicht über die Breite des Steuerelements hinausgeht, wird die Schiebeleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt immer eine vertikale Schiebeleiste an.  Wenn der Text nicht über die Höhe des Steuerelements hinausgeht, wird die Schiebeleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars>|Zeigt immer eine vertikale Schiebeleiste an.  Zeigt eine horizontale Schiebeleiste an, wenn für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>\-Eigenschaft `false` festgelegt wurde.  Wenn der Text nicht über die Breite bzw. Höhe des Steuerelements hinausgeht, werden die Schiebeleisten abgeblendet angezeigt.|  
  
3.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>\-Eigenschaft auf einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |----------|------------------|  
    |`false`|Die Breite des Textes im Steuerelement wird nicht automatisch der Breite des Steuerelements angepasst. Daher wird der Text bis zum Erreichen eines Zeilenumbruchs nach rechts fortgesetzt.  Verwenden Sie diesen Wert, wenn Sie oben den Wert **Horizontal** der **Both** für Schiebeleisten festgelegt haben.|  
    |`true` \(Standardwert\)|Die Breite des Textes im Steuerelement wird automatisch der Breite des Steuerelements angepasst.  Es wird keine horizontale Schiebeleiste angezeigt.  Verwenden Sie diesen Wert, wenn Sie oben zur Anzeige eines oder mehrerer Absätze den Wert **Vertical** oder **None** für Schiebeleisten festgelegt haben.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)