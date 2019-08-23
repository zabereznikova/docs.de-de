---
title: 'Vorgehensweise: Festlegen des Eingabeformats'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949145"
---
# <a name="how-to-set-the-input-mask"></a>Vorgehensweise: Festlegen des Eingabeformats
Das maskierte Textfeld-Steuerelement ist ein erweitertes Textfeld-Steuerelement, das eine deklarative Syntax zum akzeptieren oder ablehnen von Benutzereingaben unterstützt. Indem Sie die Mask-Eigenschaft festlegen, können Sie die zulässige Benutzereingabe angeben, ohne benutzerdefinierte Validierungs Logik in Ihre Anwendung schreiben zu müssen. Weitere Informationen finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox> -Klasse.  
  
## <a name="setting-the-mask-property-manually"></a>Manuelles Festlegen der Mask-Eigenschaft  
 Wenn Sie mit den Zeichen vertraut sind, die von der Mask-Eigenschaft unterstützt werden, können Sie Sie manuell eingeben. Eine Zusammenfassung der Zeichen, die von der Mask-Eigenschaft unterstützt werden, finden Sie <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> im Abschnitt "Hinweise" der-Eigenschaft.  
  
### <a name="to-set-the-mask-property-manually"></a>So legen Sie die Mask-Eigenschaft manuell fest  
  
1. Wählen Sie in der **Entwurfs** Ansicht <xref:System.Windows.Forms.MaskedTextBox>einen aus.  
  
2. Suchen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> -Eigenschaft.  
  
3. Geben Sie die gewünschte Maske ein. Geben Sie beispielsweise Folgendes ein: `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Verwenden des Dialog Felds Eingabemaske  
 Das Dialogfeld Eingabemaske bietet einige vordefinierte Eingabemasken. Sie können auch die vordefinierten Masken ändern oder eine eigene Maske manuell eingeben.  
  
### <a name="to-open-the-input-mask-dialog-box"></a>So öffnen Sie das Dialogfeld "Eingabemaske"  
  
1. Wählen Sie in der **Entwurfs** Ansicht <xref:System.Windows.Forms.MaskedTextBox>einen aus.  
  
    1. Klicken Sie auf das Smarttag, um das **Aufgaben Panel MaskedTextBox** zu öffnen.  
  
    2. Klicken Sie auf **Maske festlegen**.  
  
     \- oder –  
  
    1. Wählen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> -Eigenschaft aus.  
  
    2. Klicken Sie in der Spalte Eigenschaften Wert auf die Schaltfläche mit den Auslassungs Zeichen  
  
     Das Dialogfeld **Eingabemaske** wird angezeigt.  
  
### <a name="to-use-the-input-mask-dialog-box"></a>So verwenden Sie das Dialogfeld "Eingabemaske"  
  
1. Optionale Klicken Sie in der Liste auf eine der vordefinierten Masken.  
  
2. Optionale Bearbeiten Sie die vordefinierte Maske im Feld **Maske** .  
  
3. Optionale Geben Sie eine neue Maske in das Feld **Maske** ein. Das heißt, dass Sie nicht eine der vordefinierten Masken verwenden müssen.  
  
    > [!NOTE]
    > Im Feld Vorschau werden die Zeichen angezeigt, die dem Benutzer in <xref:System.Windows.Forms.MaskedTextBox>der angezeigt werden. Diese Zeichen sind eine Anleitung, mit deren Hilfe der Benutzer die Daten ordnungsgemäß eingeben können.  
  
4. Aktivieren oder deaktivieren Sie das Kontrollkästchen **ValidatingType verwenden** . Das Kontrollkästchen **use ValidatingType** gibt an, ob ein Datentyp verwendet wird, um die Dateneingabe durch den Benutzer zu überprüfen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>-Eigenschaft.  
  
5. Klicken Sie auf **OK**.  
  
     Die Maske wird in der **Mask** -Eigenschaft im **Eigenschaften** Fenster eingegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement](walkthrough-working-with-the-maskedtextbox-control.md)
