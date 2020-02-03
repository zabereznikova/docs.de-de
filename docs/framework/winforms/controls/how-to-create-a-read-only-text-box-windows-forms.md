---
title: 'Gewusst wie: Erstellen eines schreibgeschützten Textfelds'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731274"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)

Sie können eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Steuerelement umwandeln. Beispielsweise kann im Textfeld ein Wert angezeigt werden, der normalerweise bearbeitet wird, aber aufgrund des Status der Anwendung möglicherweise nicht aktuell ist.

## <a name="to-create-a-read-only-text-box"></a>So erstellen Sie ein Schreib geschütztes Textfeld

1. Legen Sie die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>-Eigenschaft des <xref:System.Windows.Forms.TextBox>-Steuer Elements auf `true`fest. Wenn die-Eigenschaft auf `true`festgelegt ist, können Benutzer einen Bildlauf durchführen und Text in einem Textfeld hervorheben, ohne Änderungen zuzulassen. Ein **Kopier** Befehl ist in einem Textfeld funktionsfähig, **Ausschneide** -und **Einfüge** Befehle hingegen nicht.

    > [!NOTE]
    > Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>-Eigenschaft wirkt sich nur auf die Benutzerinteraktion zur Laufzeit aus. Sie können Text Feldinhalte weiterhin Programm gesteuert zur Laufzeit ändern, indem Sie die <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft des Textfelds ändern.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
