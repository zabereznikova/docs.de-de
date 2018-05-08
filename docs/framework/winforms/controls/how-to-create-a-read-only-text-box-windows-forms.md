---
title: 'Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)
Sie können ein bearbeitbares Windows Forms-Text-Feld in ein schreibgeschütztes Steuerelement umwandeln. Beispielsweise kann das Textfeld einen Wert angezeigt, der in der Regel bearbeitet wird, aber möglicherweise nicht aktuell aufgrund des Status der Anwendung.  
  
### <a name="to-create-a-read-only-text-box"></a>So erstellen ein nur-Lese Textfeld  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft `true`. Mit der Eigenschaft auf festgelegt `true`, Benutzer können weiterhin einen Bildlauf durchführen und Hervorheben von Text in einem Textfeld ohne dass Änderungen. Ein **Kopie** Befehl ist in einem Textfeld funktionsfähig, aber **Ausschneiden** und **einfügen** Befehle sind nicht.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf ein Eingreifen des Benutzers zur Laufzeit. Sie können immer noch ändern Textfeldinhalt programmgesteuert zur Laufzeit durch Ändern der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TextBox>  
 [Übersicht über das TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
