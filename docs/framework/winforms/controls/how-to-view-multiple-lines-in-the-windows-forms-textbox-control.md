---
title: 'Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: f7a0e3a14d14f0629bd9995dbecd3f0b98bea1d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190911"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms
Standardmäßig wird die Windows-Formulare <xref:System.Windows.Forms.TextBox> -Steuerelement zeigt eine einzelne Textzeile an und zeigt keine Bildlaufleisten. Wenn der Text länger als der verfügbare Speicherplatz ist, ist nur ein Teil des Texts angezeigt. Sie können dieses Standardverhalten ändern, durch Festlegen der <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, und <xref:System.Windows.Forms.TextBox.ScrollBars%2A> Eigenschaften auf die entsprechenden Werte.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Um einen Wagenrücklauf in der TextBox-Steuerelement anzuzeigen.  
  
-   Zum Anzeigen von eines Wagenrücklauf in ein mehrzeiliges <xref:System.Windows.Forms.TextBox>, verwenden Sie die <xref:System.Environment.NewLine%2A> Eigenschaft.  
  
     Beachten Sie, die die Interpretation von Escapezeichen (\\) ist sprachspezifisch. Visual Basic verwendet `Chr$(13) & Chr$(10)` für die Kombination aus Wagenrücklauf- und Zeilenvorschubzeichen.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Um mehrere Zeilen im TextBox-Steuerelement anzuzeigen.  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> -Eigenschaft auf `true`fest. Wenn <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> ist `true` (Standardeinstellung), dann wird der Text im Steuerelement als eine oder mehrere Absätze angezeigt; andernfalls wird es als eine Liste, in dem einige Zeilen können, am Rand des Steuerelements abgeschnitten werden angezeigt.  
  
2.  Legen Sie für die <xref:System.Windows.Forms.TextBox.ScrollBars%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Verwenden Sie diesen Wert aus, wenn der Text eines Absatzes sein soll, die fast immer passt das Steuerelement. Benutzer können den Mauszeiger auf das Steuerelement bewegen, wenn der Text zu lang, um alle auf einmal anzeigen.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Verwenden Sie diesen Wert sollten Sie eine Liste der Zeilen anzuzeigen, von denen einige möglicherweise länger als die Breite der <xref:System.Windows.Forms.TextBox> Steuerelement.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Verwenden Sie diesen Wert, wenn die Liste mehr als die Höhe des Steuerelements sein kann.|  
  
3.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Text im Steuerelement wird nicht automatisch umbrochen, damit sie nach rechts Scrollen wird, bis ein Zeilenumbruch eingefügt erreicht ist. Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Horizontal> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.Both>weiter oben.|  
    |`true` (Standard)|Die horizontale Bildlaufleiste wird nicht angezeigt. Wenn Sie ausgewählt haben, verwenden Sie diesen Wert <xref:System.Windows.Forms.ScrollBars.Vertical> Scrollleisten oder <xref:System.Windows.Forms.ScrollBars.None>weiter oben, um einen oder mehrere Absätze anzuzeigen.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines schreibgeschützten Textfelds](how-to-create-a-read-only-text-box-windows-forms.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
