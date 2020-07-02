---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds'
description: Erfahren Sie, wie Sie eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Windows Forms Textfeld transformieren.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619363"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)

Sie können eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Steuerelement umwandeln. Beispielsweise kann im Textfeld ein Wert angezeigt werden, der normalerweise bearbeitet wird, aber aufgrund des Status der Anwendung möglicherweise nicht aktuell ist.

## <a name="to-create-a-read-only-text-box"></a>So erstellen Sie ein Schreib geschütztes Textfeld

1. Legen <xref:System.Windows.Forms.TextBox> Sie die-Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> auf fest `true` . Wenn die-Eigenschaft auf festgelegt `true` ist, können Benutzer einen Bildlauf durchführen und Text in einem Textfeld hervorheben, ohne Änderungen zuzulassen. Ein **Kopier** Befehl ist in einem Textfeld funktionsfähig, **Ausschneide** -und **Einfüge** Befehle hingegen nicht.

    > [!NOTE]
    > Die- <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf die Benutzerinteraktion zur Laufzeit aus. Text Feldinhalte können zur Laufzeit weiterhin Programm gesteuert geändert werden, indem Sie die- <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds ändern.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- [Übersicht über das TextBox-Steuerelement](textbox-control-overview-windows-forms.md)
- [Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox-Steuerelement](textbox-control-windows-forms.md)
