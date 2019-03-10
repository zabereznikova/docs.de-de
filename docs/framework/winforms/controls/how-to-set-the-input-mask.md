---
title: 'Vorgehensweise: Festlegen des Eingabeformats'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 53bb8d0e301f83c25ab292b1cb6324dd5f21f100
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702359"
---
# <a name="how-to-set-the-input-mask"></a>Vorgehensweise: Festlegen des Eingabeformats
Das maskierte Textfeld-Steuerelement ist eine erweiterte Textfeld-Steuerelement, das eine deklarative Syntax unterstützt, zum Akzeptieren oder Ablehnen der Benutzereingabe. Wenn Sie die Mask-Eigenschaft festlegen, können Sie die zulässigen Benutzereingaben ohne schreiben eine benutzerdefinierte Validierungslogik in Ihrer Anwendung angeben. Weitere Informationen finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox> Klasse.  
  
## <a name="setting-the-mask-property-manually"></a>Die Mask-Eigenschaft festlegen manuell  
 Wenn Sie mit den Zeichen vertraut, die die Mask-Eigenschaft unterstützt sind, können Sie es manuell eingeben. Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
#### <a name="to-set-the-mask-property-manually"></a>Die Mask-Eigenschaft manuell festlegen.  
  
1.  In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  In der **Eigenschaften** Fenster Suchen der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
3.  Geben Sie die Maske, die Sie möchten. Geben Sie beispielsweise Folgendes ein: `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Mithilfe des Dialogfelds Eingabemaske  
 Das Input Mask-Dialogfeld bietet einige vordefinierte Eingabeformate. Sie können auch vordefinierten Masken ändern oder eigene Maske manuell eingeben.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>So öffnen Sie die Input Mask-Dialogfeld  
  
1.  In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Klicken Sie auf das Smarttag, öffnen Sie die **MaskedTextBox-Aufgaben** Bereich.  
  
    2.  Klicken Sie auf **Maske festlegen**.  
  
     \- oder –  
  
    1.  In der **Eigenschaften** wählen Sie im Fenster der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
    2.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, in der Spalte mit dem Eigenschaftswert.  
  
     Die **Eingabeformat** Dialogfeld wird angezeigt.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>Zum Verwenden der Input Mask-Dialogfelds  
  
1.  (Optional) Klicken Sie auf eine der vordefinierten Masken in der Liste.  
  
2.  (Optional) Bearbeiten Sie die vordefinierten Maske in die **Maske** Feld.  
  
3.  (Optional) Geben Sie eine neue Maske in die **Maske** Feld. Sie müssen, also nicht eine der vordefinierten Masken verwenden.  
  
    > [!NOTE]
    >  Das Feld Vorschau zeigt die Zeichen, die dem Benutzer angezeigt, in wird der <xref:System.Windows.Forms.MaskedTextBox>. Diese Zeichen sind eine Anleitung für die Benutzer die Daten richtig eingeben können.  
  
4.  Aktivieren oder deaktivieren Sie die **verwenden ValidatingType** Kontrollkästchen. Die **verwenden ValidatingType** Kontrollkästchen gibt an, ob ein Datentyp verwendet wird, um zu überprüfen, ob die Dateneingabe durch den Benutzer. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>-Eigenschaft.  
  
5.  Klicken Sie auf **OK**.  
  
     Die Maske wird eingegeben die **Maske** -Eigenschaft in der **Eigenschaften** Fenster.  
  
## <a name="see-also"></a>Siehe auch
- [Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement](walkthrough-working-with-the-maskedtextbox-control.md)
