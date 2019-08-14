---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971944"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)

Sie können eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Steuerelement umwandeln. Beispielsweise kann im Textfeld ein Wert angezeigt werden, der normalerweise bearbeitet wird, aber aufgrund des Status der Anwendung möglicherweise nicht aktuell ist.

## <a name="to-create-a-read-only-text-box"></a>So erstellen Sie ein Schreib geschütztes Textfeld

1. Legen Sie <xref:System.Windows.Forms.TextBox> die- <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft des `true`-Steuer Elements auf fest. Wenn die-Eigenschaft auf `true`festgelegt ist, können Benutzer einen Bildlauf durchführen und Text in einem Textfeld hervorheben, ohne Änderungen zuzulassen. Ein **Kopier** Befehl ist in einem Textfeld funktionsfähig, **Ausschneide** -und **Einfüge** Befehle hingegen nicht.

    > [!NOTE]
    > Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> -Eigenschaft wirkt sich nur auf die Benutzerinteraktion zur Laufzeit aus. Text Feldinhalte können zur Laufzeit weiterhin Programm gesteuert geändert werden, indem Sie die <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft des Textfelds ändern.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem Windows Forms TextBox-Steuerelement](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Textfeld "Kennwort" mit dem Windows Forms TextBox-Steuerelement erstellen](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anführungszeichen in eine Zeichenfolge einfügen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Text im TextBox-Steuerelement Windows Forms auswählen](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
