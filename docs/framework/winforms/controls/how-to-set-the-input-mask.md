---
title: 'Gewusst wie: Festlegen des Eingabeformats'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68bfe46462a374899a0782903804edea0e93f161
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-input-mask"></a>Gewusst wie: Festlegen des Eingabeformats
Das maskierte Textfeld-Steuerelement ist eine verbesserte Textfeld-Steuerelement, die eine deklarative Syntax zum Akzeptieren oder ablehnen von Benutzereingaben unterstützt. Durch Festlegen der Mask-Eigenschaft, können Sie die zulässigen Benutzereingaben angeben, ohne dass eine benutzerdefinierte Validierungslogik in der Anwendung geschrieben. Weitere Informationen finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox> Klasse.  
  
## <a name="setting-the-mask-property-manually"></a>Manuelles Festlegen der Mask-Eigenschaft  
 Wenn Sie mit den Zeichen vertraut, die die Mask-Eigenschaft unterstützt sind, können Sie es manuell eingeben. Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
#### <a name="to-set-the-mask-property-manually"></a>Die Mask-Eigenschaft manuell festlegen.  
  
1.  In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  In der **Eigenschaften** Fenster, suchen Sie die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
3.  Geben Sie die Maske, die Sie möchten. Geben Sie z. B. `###`.  
  
## <a name="using-the-input-mask-dialog-box"></a>Mithilfe des Dialogfelds Eingabeformat  
 Die Input Mask-Dialogfeld stellt einige vordefinierte Eingabeformate bereit. Sie können auch vordefinierten Masken ändern oder eigene Maske manuell eingeben.  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>So öffnen das Dialogfeld Eingabeformat  
  
1.  In **Entwurf** wählen eine <xref:System.Windows.Forms.MaskedTextBox>.  
  
    1.  Klicken Sie auf das Smarttag, öffnen Sie die **MaskedTextBox-Aufgaben** Bereich.  
  
    2.  Klicken Sie auf **Maske festlegen**.  
  
     \- oder –  
  
    1.  In der **Eigenschaften** wählen die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
    2.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, in der Eigenschaft-Wert-Spalte.  
  
     Die **Eingabeformat** Dialogfeld wird angezeigt.  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>Zum Verwenden der Input Mask-Dialogfelds  
  
1.  (Optional) Klicken Sie auf eine der vordefinierten Masken in der Liste.  
  
2.  (Optional) Bearbeiten Sie die vordefinierte Maske in die **Maske** Feld.  
  
3.  (Optional) Geben Sie eine neue Maske in die **Maske** Feld. Sie haben also nicht eine der vordefinierten Masken verwenden.  
  
    > [!NOTE]
    >  Das Feld Vorschau zeigt die Zeichen, die dem Benutzer angezeigt, in wird der <xref:System.Windows.Forms.MaskedTextBox>. Diese Zeichen sind eine Anleitung für die Benutzer die Daten ordnungsgemäß eingeben helfen.  
  
4.  Aktivieren oder Deaktivieren der **verwenden ValidatingType** Kontrollkästchen. Die **verwenden ValidatingType** Kontrollkästchen gibt an, ob ein Datentyp verwendet wird, um zu überprüfen, ob die Dateneingabe vom Benutzer. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>-Eigenschaft.  
  
5.  Klicken Sie auf **OK**.  
  
     Die Maske eingegeben wird, der **Maske** Eigenschaft in der **Eigenschaften** Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
