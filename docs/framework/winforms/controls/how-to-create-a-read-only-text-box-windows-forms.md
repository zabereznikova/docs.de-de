---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670341"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)
Sie können ein bearbeitbares Windows Forms-Text-Feld in ein schreibgeschütztes Steuerelement umwandeln. Beispielsweise kann im Textfeld einen Wert angezeigt, der in der Regel bearbeitet wird, aber möglicherweise nicht aktuell, aufgrund des Zustands der Anwendung.  
  
### <a name="to-create-a-read-only-text-box"></a>Erstellen ein schreibgeschützten Textfelds  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft `true`. Die Eigenschaft auf festgelegt `true`, Benutzer können weiterhin scrollen und Hervorheben von Text in einem Textfeld ohne Änderungen. Ein **Kopie** Befehl funktioniert in einem Textfeld, aber **Ausschneiden** und **einfügen** Befehle sind nicht.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf eine Benutzerinteraktion bei der Ausführung. Sie können weiterhin textfeldinhalte programmgesteuert ändern zur Laufzeit durch Ändern der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
