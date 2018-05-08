---
title: 'Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: e067966b606d77ceb9d11d2784c0d5f73ad332a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt
Windows Forms <xref:System.Windows.Forms.Label> Steuerelement kann es sich um einzeilige oder mehrzeilige und können werden entweder eine feste Größe oder können automatisch ändern, ihre Beschriftung angepasst. Die <xref:System.Windows.Forms.Label.AutoSize%2A> -Eigenschaft hilft Ihnen bei der Steuerelemente größere oder kleinere Beschriftungen, Anpassen der ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Um ein Bezeichnungsfeld-Steuerelement dynamisch angepasst seinen Inhalt zu machen.  
  
1.  Legen Sie dessen <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft `true`.  
  
 Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf festgelegt ist `false`, den angegebenen Wörtern in der <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft nach Möglichkeit die nächste Zeile umbrochen, aber das Steuerelement wird nicht vergrößert.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Übersicht über das Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
