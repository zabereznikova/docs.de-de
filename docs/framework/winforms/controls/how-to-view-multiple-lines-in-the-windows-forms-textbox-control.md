---
title: "Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dca8d0f869702dee50bf851a2099317c45aa842
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms
Standardmäßig werden in Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement zeigt eine einzelne Textzeile an und zeigt keine Bildlaufleisten. Wenn der Text länger als der verfügbare Platz ist, ist nur ein Teil des Texts sichtbar. Sie können dieses Standardverhalten ändern, indem Sie die Einstellung der <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaften auf die entsprechenden Werte.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Um einen Wagenrücklauf in das Textfeld-Steuerelement anzuzeigen.  
  
-   Einen Wagenrücklauf in das mehrzeilige anzuzeigende <xref:System.Windows.Forms.TextBox>, verwenden Sie die <xref:System.Environment.NewLine%2A> Eigenschaft.  
  
     Beachten Sie, die Interpretation von Escapezeichen (\\) ist sprachspezifisch. Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagenrücklauf und Zeilenvorschubzeichen.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>So zeigen Sie mehrere Zeilen im TextBox-Steuerelement an  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A>-Eigenschaft auf `true` fest. Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> ist `true` (Standard), dann erscheint der Text im Steuerelement als ein oder mehrere Absätze; andernfalls erscheint als eine Liste, in dem einige Zeilen am Rand des Steuerelements abgeschnitten werden können.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Verwenden Sie diesen Wert, wenn der Text eines Absatzes sein soll, die fast immer passt das Steuerelement. Der Benutzer können den Mauszeiger auf das Steuerelement navigieren, wenn der Text für alle auf einmal anzeigen zu lang ist.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Verwenden Sie diesen Wert aus, wenn Sie eine Liste der Zeilen anzuzeigen, von denen einige möglicherweise länger als die Breite des möchten die <xref:System.Windows.Forms.TextBox> Steuerelement.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Verwenden Sie diesen Wert, wenn die Liste mehr als die Höhe des Steuerelements sein kann.|  
  
3.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Text im Steuerelement wird nicht automatisch umbrochen, damit es Bildlauf nach rechts wird erst ein Zeilenumbruch erreicht wird. Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Horizontal> Bildlaufleisten oder <xref:System.Windows.Forms.ScrollBars.Both>oben.|  
    |`true` (Standardwert)|Die horizontale Bildlaufleiste wird nicht angezeigt. Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Vertical> Bildlaufleisten oder <xref:System.Windows.Forms.ScrollBars.None>oben, um einen oder mehrere Absätze anzuzeigen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
