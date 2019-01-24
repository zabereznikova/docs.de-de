---
title: 'Vorgehensweise: Anzeigen von Bildlaufleisten in der Windows Forms-RichTextBox-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 6b6cfb8c21c8f3a48bb85a0591f3390d5b5575b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610395"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Vorgehensweise: Anzeigen von Bildlaufleisten in der Windows Forms-RichTextBox-Steuerelement
Standardmäßig wird die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> -Steuerelement zeigt die horizontale und vertikale Bildlaufleisten nach Bedarf. Es gibt sieben mögliche Werte für die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> Eigenschaft der <xref:System.Windows.Forms.RichTextBox> -Steuerelement, das in der folgenden Tabelle beschrieben werden.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Zum Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.Multiline%2A> -Eigenschaft auf `true`fest. Kein Typ der Schiebeleiste, einschließlich horizontal wird angezeigt, wenn die <xref:System.Windows.Forms.RichTextBox.Multiline%2A> -Eigenschaftensatz auf `false`.  
  
2.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> Eigenschaft, um einen geeigneten Wert aus der <xref:System.Windows.Forms.RichTextBoxScrollBars> Enumeration.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (Standardwert)|Horizontale oder vertikale Bildlaufleisten angezeigt oder für beide nur, wenn Text die Breite bzw. Höhe des Steuerelements überschreitet.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Nie zeigt jede Art von Bildlaufleiste angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Zeigt eine horizontale Schiebeleiste nur, wenn der Text die Breite des Steuerelements überschreitet. (Damit dies eintritt, die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> Eigenschaft muss festgelegt werden, um `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Zeigt eine vertikale scrollleiste an, nur, wenn der Text der Höhe des Steuerelements überschreitet.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Zeigt eine horizontale Schiebeleiste bei der <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> -Eigenschaftensatz auf `false`. Wenn der Text die Breite des Steuerelements nicht überschreitet, wird von die Bildlaufleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Zeigt immer eine vertikale Bildlaufleiste angezeigt. Wenn der Text die Länge des Steuerelements nicht überschreitet, wird von die Bildlaufleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Zeigt immer eine vertikale Bildlaufleiste an. Zeigt eine horizontale Schiebeleiste bei der <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> -Eigenschaftensatz auf `false`. Wenn der Text die Breite bzw. Höhe des Steuerelements nicht überschreitet, werden die Bildlaufleisten abgeblendet angezeigt.|  
  
3.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Text im Steuerelement wird nicht automatisch angepasst, um die Breite des Steuerelements anpassen, damit sie nach rechts Scrollen wird, bis ein Zeilenumbruch eingefügt erreicht ist. Verwenden Sie diesen Wert, wenn Sie horizontale Scrollleisten oder beide, oben ausgewählt haben.|  
    |`true` (Standardwert)|Text im Steuerelement wird automatisch angepasst, um die Breite des Steuerelements passt. Die horizontale Bildlaufleiste wird nicht angezeigt. Verwenden Sie diesen Wert, wenn Sie vertikale Bildlaufleisten oder none, oben, einen oder mehrere Absätze anzeigen.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
