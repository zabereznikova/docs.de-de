---
title: Größe eines Label-Steuer Elements an seinen Inhalt anpassen
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743776"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt
Das Windows Forms <xref:System.Windows.Forms.Label>-Steuerelement kann einzeilige oder mehrzeilige Elemente sein, und es kann entweder die Größe oder die Größe automatisch ändern, um die Beschriftung zu unterstützen. Mit der <xref:System.Windows.Forms.Label.AutoSize%2A>-Eigenschaft können Sie die Größe der Steuerelemente für größere oder kleinere Untertitel anpassen. Dies ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>So ändern Sie die Größe eines Label-Steuer Elements dynamisch, um seinen Inhalt anzupassen  
  
1. Legen Sie die <xref:System.Windows.Forms.Label.AutoSize%2A>-Eigenschaft auf `true`fest.  
  
 Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf `false`festgelegt ist, werden die in der <xref:System.Windows.Forms.Label.Text%2A>-Eigenschaft angegebenen Wörter nach Möglichkeit in die nächste Zeile eingebunden, aber das Steuerelement wird nicht vergrößert.  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Übersicht über das Label-Steuerelement](label-control-overview-windows-forms.md)
- [Label-Steuerelement](label-control-windows-forms.md)
