---
title: Übersicht über das Button-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 505b75d362cea0eddec2b51dc398e2cd8c8d4db8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713389"
---
# <a name="button-control-overview-windows-forms"></a>Übersicht über das Button-Steuerelement (Windows Forms)
Das Windows Forms <xref:System.Windows.Forms.Button>-Steuerelement ermöglicht es dem Benutzer, durch Klicken eine Aktion auszuführen. Wenn der Benutzer auf die Schaltfläche klickt, wird sie als gedrückt bzw. nicht gedrückt angezeigt. Wenn der Benutzer eine Schaltfläche klickt. die <xref:System.Windows.Forms.Control.Click> Ereignishandler aufgerufen. Sie fügen Sie Code in die <xref:System.Windows.Forms.Control.Click> Ereignishandler keine Aktion, die Sie auswählen.  
  
 Auf der Schaltfläche angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft. Wenn der Text die Breite der Schaltfläche überschreitet, wird es in die nächste Zeile umbrochen. Allerdings wird es abgeschnitten, wenn das Steuerelement nicht die gesamte Höhe aufnehmen kann. Weitere Informationen finden Sie unter [Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement](how-to-set-the-text-displayed-by-a-windows-forms-control.md). Die <xref:System.Windows.Forms.Control.Text%2A> -Eigenschaft kann eine Zugriffstaste, die einem Benutzer ermöglicht, die das Steuerelement "click", durch Drücken der ALT-Taste durch den Zugriffsschlüssel enthalten. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows-Steuerelemente Forms](how-to-create-access-keys-for-windows-forms-controls.md). Die Darstellung des Texts wird gesteuert, indem die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft und die <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> Eigenschaft.  
  
 Die <xref:System.Windows.Forms.Button> Steuerelement kann auch Images mit Anzeigen der <xref:System.Windows.Forms.ButtonBase.Image%2A> und <xref:System.Windows.Forms.ButtonBase.ImageList%2A> Eigenschaften. Weitere Informationen finden Sie unter [Vorgehensweise: Das Bild angezeigt, die von einer Windows Forms-Steuerelement](how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Button>
- [Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt](how-to-respond-to-windows-forms-button-clicks.md)
- [Methoden zur Auswahl eines Button-Steuerelements in Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Vorgehensweise: Definieren Sie eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Vorgehensweise: Festlegen einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button-Steuerelement](button-control-windows-forms.md)
