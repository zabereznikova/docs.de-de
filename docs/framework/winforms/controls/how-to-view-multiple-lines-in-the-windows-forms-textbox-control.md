---
title: Anzeigen mehrerer Zeilen im TextBox-Steuerelement
description: Erfahren Sie, wie Sie mehrere Zeilen im TextBox-Steuerelement Windows Forms anzeigen, indem Sie die Multiline-, WordWrap-und ScrollBars-Eigenschaften festlegen.
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
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174470"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms
Standardmäßig zeigt das Windows Forms <xref:System.Windows.Forms.TextBox> Steuerelement eine einzelne Textzeile an und zeigt keine Schiebe leisten an. Wenn der Text länger als der verfügbare Platz ist, ist nur ein Teil des Texts sichtbar. Sie können dieses Standardverhalten ändern, indem Sie <xref:System.Windows.Forms.TextBox.Multiline%2A> die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> Eigenschaften, und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> auf die entsprechenden Werte festlegen.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>So zeigen Sie einen Wagen Rücklauf im TextBox-Steuerelement an  
  
- Verwenden Sie die-Eigenschaft, um einen Wagen Rücklauf in einer mehrzeiligen Zeile anzuzeigen <xref:System.Windows.Forms.TextBox> <xref:System.Environment.NewLine%2A> .  
  
     Beachten Sie, dass die Interpretation von Escapezeichen ( \\ ) sprachspezifisch ist. Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagen Rücklauf und Zeilenvorschub Zeichen.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>So zeigen Sie mehrere Zeilen im TextBox-Steuerelement an  
  
1. Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> -Eigenschaft auf `true`fest. Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (der Standardwert) ist, wird der Text im-Steuerelement als ein oder mehrere Absätze angezeigt. andernfalls wird er als Liste angezeigt, in der einige Zeilen am Rand des Steuer Elements abgeschnitten werden können.  
  
2. Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Verwenden Sie diesen Wert, wenn es sich bei dem Text um einen Absatz handelt, der fast immer dem Steuerelement entspricht. Der Benutzer kann mit dem Mauszeiger im Steuerelement navigieren, wenn der Text zu lang ist, um alle gleichzeitig anzuzeigen.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Verwenden Sie diesen Wert, wenn Sie eine Liste von Zeilen anzeigen möchten, von denen einige möglicherweise länger als die Breite des <xref:System.Windows.Forms.TextBox> Steuer Elements sind.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Verwenden Sie diesen Wert, wenn die Liste möglicherweise länger als die Höhe des Steuer Elements ist.|  
  
3. Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Der Text im-Steuerelement wird nicht automatisch umschließt, sodass er nach rechts verschoben wird, bis ein Zeilenumbruch erreicht ist. Verwenden Sie diesen Wert, wenn Sie <xref:System.Windows.Forms.ScrollBars.Horizontal> Scrollleisten oder oben ausgewählt haben <xref:System.Windows.Forms.ScrollBars.Both> .|  
    |`true` (Standardwert)|Die horizontale Scrollleiste wird nicht angezeigt. Verwenden Sie diesen Wert, wenn Sie <xref:System.Windows.Forms.ScrollBars.Vertical> Scrollleisten ausgewählt haben oder <xref:System.Windows.Forms.ScrollBars.None> oben, um einen oder mehrere Absätze anzuzeigen.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
