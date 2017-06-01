---
title: "Gewusst wie: Erstellen eines schreibgesch&#252;tzten Textfelds (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Schreibgeschützte Textfelder"
  - "Textfelder, Schreibgeschützt"
  - "TextBox-Steuerelement [Windows Forms], Schreibgeschützt"
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen eines schreibgesch&#252;tzten Textfelds (Windows&#160;Forms)
Ein editierbares Textfeld für Windows Forms kann problemlos in ein schreibgeschütztes Steuerelement umgewandelt werden.  Im Textfeld wird z. B. ein Wert angezeigt, der zwar normalerweise bearbeitet wird, dessen Bearbeitung aufgrund des Anwendungszustands jedoch gegenwärtig nicht möglich ist.  
  
### So erstellen Sie ein schreibgeschütztes Textfeld  
  
1.  Legen Sie die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>\-Eigenschaft des <xref:System.Windows.Forms.TextBox>\-Steuerelements auf `true` fest.  Wenn für diese Eigenschaft `true` festgelegt wird, kann der Benutzer weiterhin den Bildlauf durchführen und Text in einem Textfeld hervorheben, es sind jedoch keine Änderungen möglich.  Textfelder unterstützen den Befehl **Kopieren**; die Befehle **Ausschneiden** und **Einfügen** sind nicht verfügbar.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>\-Eigenschaft beeinflusst nur Benutzerinteraktionen zur Laufzeit.  Sie können den Inhalt des Textfelds weiterhin programmgesteuert zur Laufzeit ändern, indem Sie die <xref:System.Windows.Forms.TextBox.Text%2A>\-Eigenschaft des Textfelds ändern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TextBox>   
 [Übersicht über das TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Gewusst wie: Steuern der Einfügemarke in einem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Gewusst wie: Erstellen eines Kennwort\-Textfelds mit dem TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Setzen von Anführungszeichen in Zeichenfolgen](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Gewusst wie: Programmgesteuertes Auswählen von Text im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Gewusst wie: Anzeigen mehrerer Zeilen im TextBox\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox\-Steuerelement](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)