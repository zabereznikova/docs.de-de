---
title: "Gewusst wie: Festlegen des Eingabeformats | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.MaskPropertyEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MaskedTextBox-Steuerelement [Windows Forms]"
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Festlegen des Eingabeformats
Das maskierte Textfeld\-Steuerelement ist ein verbessertes Textfeld\-Steuerelement und unterstützt eine deklarative Syntax zum Akzeptieren oder Ablehnen von Benutzereingaben.  Mit der Mask\-Eigenschaft können Sie die zulässigen Benutzereingaben festlegen, ohne eine benutzerdefinierte Validierungslogik in der Anwendung zu schreiben.  Weitere Informationen finden Sie in den Hinweisen zur <xref:System.Windows.Forms.MaskedTextBox>\-Klasse.  
  
## Manuelles Festlegen der Mask\-Eigenschaft  
 Wenn Sie mit den von der Mask\-Eigenschaft unterstützten Zeichen vertraut sind, können Sie sie manuell eingeben.  Eine Übersicht der von der Mask\-Eigenschaft unterstützten Zeichen finden Sie in den Hinweisen zur <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft.  
  
#### So legen Sie die Mask\-Eigenschaft manuell fest  
  
1.  Wählen Sie in der **Entwurfsansicht** <xref:System.Windows.Forms.MaskedTextBox> aus.  
  
2.  Suchen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft.  
  
3.  Geben Sie die gewünschte Maske ein.  Beispiel: `###`.  
  
## Verwenden des Dialogfelds Eingabeformat  
 Im Dialogfeld Eingabeformat werden einige vordefinierte Eingabeformate bereitgestellt.  Sie können die vordefinierten Masken auch ändern oder eine eigene Maske manuell eingeben.  
  
#### So öffnen Sie das Dialogfeld Eingabeformat  
  
1.  Wählen Sie in der **Entwurfsansicht** <xref:System.Windows.Forms.MaskedTextBox> aus.  
  
    1.  Klicken Sie auf das Smarttag, um den Bereich **MaskedTextBox\-Aufgaben** zu öffnen.  
  
    2.  Klicken Sie auf **Maske festlegen**.  
  
     \- oder \-  
  
    1.  Wählen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>\-Eigenschaft aus.  
  
    2.  Klicken Sie in der Spalte mit Eigenschaftswerten auf die Schaltfläche mit den Auslassungszeichen \(…\).  
  
     Das Dialogfeld **Eingabeformat** wird angezeigt.  
  
#### So verwenden Sie das Dialogfeld Eingabeformat  
  
1.  \(Optional\) Klicken Sie in der Liste auf eine der vordefinierten Masken.  
  
2.  \(Optional\) Bearbeiten Sie die vordefinierte Maske im Feld **Maske**.  
  
3.  \(Optional\) Geben Sie im Feld **Maske** eine neue Maske ein.  Sie müssen also keine der vordefinierten Masken verwenden.  
  
    > [!NOTE]
    >  Das Feld Vorschau zeigt die Zeichen an, die der Benutzer im <xref:System.Windows.Forms.MaskedTextBox> sieht.  Diese Zeichen dienen als Leitfaden, damit der Benutzer die Daten ordnungsgemäß eingeben kann.  
  
4.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **ValidatingType verwenden**.  Das Kontrollkästchen **ValidatingType verwenden** gibt an, ob ein Datentyp verwendet wird, um die Dateneingabe des Benutzers zu überprüfen.  Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>\-Eigenschaft.  
  
5.  Klicken Sie auf **OK**.  
  
     Die Maske wird in der **Mask**\-Eigenschaft im **Eigenschaftenfenster** eingegeben.  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)