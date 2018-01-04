---
title: "Gewusst wie: Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4645e502544072cbc6268ae07e054ea5450d9c5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Gewusst wie: Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement von Windows Forms
Standardmäßig werden in Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement horizontale und vertikale Bildlaufleisten angezeigt, nach Bedarf. Es gibt sieben mögliche Werte für die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> Eigenschaft von der <xref:System.Windows.Forms.RichTextBox> -Steuerelement, das in der folgenden Tabelle beschrieben werden.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Zum Anzeigen von Bildlaufleisten im RichTextBox-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.Multiline%2A>-Eigenschaft auf `true` fest. Kein Typ der Bildlaufleiste, einschließlich horizontal wird angezeigt, wenn die <xref:System.Windows.Forms.RichTextBox.Multiline%2A> -Eigenschaftensatz auf `false`.  
  
2.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> auf einen geeigneten Wert der Eigenschaft der <xref:System.Windows.Forms.RichTextBoxScrollBars> Enumeration.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (Standardwert)|Horizontale oder vertikale Bildlaufleisten angezeigt oder beides, nur, wenn der Text die Breite bzw. Höhe des Steuerelements überschreitet.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Nie zeigt Bildlaufleiste angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Zeigt eine horizontale Bildlaufleiste nur, wenn der Text die Breite des Steuerelements überschreitet. (Damit dies eintritt, die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> Eigenschaft muss festgelegt werden, um `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Zeigt eine vertikale Bildlaufleiste nur, wenn der Text der Höhe des Steuerelements überschreitet.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Zeigt eine horizontale Bildlaufleiste bei der <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> -Eigenschaftensatz auf `false`. Wenn der Text nicht über die Breite des Steuerelements überschreitet die Bildlaufleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Zeigt immer eine vertikale Bildlaufleiste angezeigt. Wenn der Text nicht die Länge des Steuerelements überschreitet die Bildlaufleiste abgeblendet angezeigt.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Zeigt immer eine vertikale Bildlaufleiste an. Zeigt eine horizontale Bildlaufleiste bei der <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> -Eigenschaftensatz auf `false`. Wenn der Text nicht über die Breite bzw. Höhe des Steuerelements überschreitet die Bildlaufleisten abgeblendet angezeigt.|  
  
3.  Legen Sie für die <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>-Eigenschaft einen geeigneten Wert fest.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |`false`|Text im Steuerelement wird nicht automatisch angepasst, um die Breite des Steuerelements anzupassen, damit es Bildlauf nach rechts wird erst ein Zeilenumbruch erreicht wird. Verwenden Sie diesen Wert, wenn Sie horizontale Bildlaufleisten oder beides oben ausgewählt haben.|  
    |`true` (Standardwert)|Text im Steuerelement wird automatisch angepasst, um die Breite des Steuerelements. Die horizontale Bildlaufleiste wird nicht angezeigt. Verwenden Sie diesen Wert, wenn Sie vertikale Bildlaufleisten oder keine "," oben einen oder mehrere Absätze anzeigen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
