---
title: Anzeigen mehrerer Zeilen im TextBox-Steuerelement
ms.date: 03/30/2017
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
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728287"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Gewusst wie: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms
Standardmäßig zeigt das Windows Forms <xref:System.Windows.Forms.TextBox>-Steuerelement eine einzelne Textzeile an und zeigt keine Schiebe leisten an. Wenn der Text länger als der verfügbare Platz ist, ist nur ein Teil des Texts sichtbar. Sie können dieses Standardverhalten ändern, indem Sie die Eigenschaften <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> auf entsprechende Werte festlegen.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>So zeigen Sie einen Wagen Rücklauf im TextBox-Steuerelement an  
  
- Um einen Wagen Rücklauf in einer mehrzeiligen <xref:System.Windows.Forms.TextBox>anzuzeigen, verwenden Sie die <xref:System.Environment.NewLine%2A>-Eigenschaft.  
  
     Beachten Sie, dass die Interpretation von Escapezeichen (\\) sprachspezifisch ist. Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagen Rücklauf und Zeilenvorschub Zeichen.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>So zeigen Sie mehrere Zeilen im TextBox-Steuerelement an  
  
1. Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> -Eigenschaft auf `true`fest. Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (Standard) ist, wird der Text im-Steuerelement in einem oder mehreren Absätzen angezeigt. Andernfalls wird Sie als Liste angezeigt, in der einige Zeilen am Rand des Steuer Elements abgeschnitten werden können.  
  
2. Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |{2&gt;Wert&lt;2}|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Verwenden Sie diesen Wert, wenn es sich bei dem Text um einen Absatz handelt, der fast immer dem Steuerelement entspricht. Der Benutzer kann mit dem Mauszeiger im Steuerelement navigieren, wenn der Text zu lang ist, um alle gleichzeitig anzuzeigen.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Verwenden Sie diesen Wert, wenn Sie eine Liste von Zeilen anzeigen möchten, von denen einige möglicherweise länger als die Breite des <xref:System.Windows.Forms.TextBox> Steuer Elements sind.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Verwenden Sie diesen Wert, wenn die Liste möglicherweise länger als die Höhe des Steuer Elements ist.|  
  
3. Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |{2&gt;Wert&lt;2}|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Der Text im-Steuerelement wird nicht automatisch umschließt, sodass er nach rechts verschoben wird, bis ein Zeilenumbruch erreicht ist. Verwenden Sie diesen Wert, wenn Sie oben <xref:System.Windows.Forms.ScrollBars.Horizontal> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.Both>ausgewählt haben.|  
    |`true` (Standard)|Die horizontale Scrollleiste wird nicht angezeigt. Verwenden Sie diesen Wert, wenn Sie <xref:System.Windows.Forms.ScrollBars.Vertical> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.None>oben ausgewählt haben, um einen oder mehrere Absätze anzuzeigen.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
