---
title: "Gewusst wie: Erstellen von Zugriffstasten mit Windows&#160;Forms-Steuerelementen | Microsoft Docs"
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
  - "Zugriffstasten, Erstellen für Steuerelemente"
  - "Zugriffstasten, Windows Forms"
  - "Steuerelemente [Windows Forms], Zugriffstasten"
  - "Dialogfeldsteuerelemente, Zugriffstasten"
  - "Tastenkombinationen, Erstellen für Steuerelemente"
  - "Label-Steuerelement [Windows Forms], Erstellen von Zugriffstasten"
  - "Zugriffstasten"
  - "Zugriffstasten, Hinzufügen zu Dialogfeld-Steuerelementen"
  - "UseMnemonic-Eigenschaft, Label-Steuerelement"
  - "Windows Forms-Steuerelemente, Zugriffstasten"
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erstellen von Zugriffstasten mit Windows&#160;Forms-Steuerelementen
Mit <xref:System.Windows.Forms.Label>\-Steuerelementen in Windows Forms können Sie Zugriffstasten für andere Steuerelemente definieren.  Wenn Sie eine Zugriffstaste in einem **Label**\-Steuerelement definieren, kann der Benutzer den Fokus auf das nächste Steuerelement in der Aktivierreihenfolge verschieben, indem er die ALT\-TASTE zusammen mit dem jeweiligen Buchstaben drückt.  Da der Fokus nicht auf Bezeichnungsfeldern liegen kann, wird er automatisch zum nächsten Steuerelement in der Aktivierreihenfolge verschoben.  Sie verwenden dieses Verfahren, um Textfeldern, Kombinationsfeldern, Listenfeldern und Datenblättern Zugriffstasten zuzuweisen.  
  
### So weisen Sie einem Steuerelement mithilfe eines Bezeichnungsfelds eine Zugriffstaste zu  
  
1.  Zeichnen Sie zunächst das Bezeichnungsfeld und dann das andere Steuerelement.  
  
     \- oder \-  
  
     Zeichnen Sie die Steuerelemente in beliebiger Reihenfolge, und legen Sie die <xref:System.Windows.Forms.Control.TabIndex%2A>\-Eigenschaft des Bezeichnungsfelds auf einen Wert fest, der um 1 niedriger ist als der des anderen Steuerelements.  
  
2.  Legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>\-Eigenschaft der Bezeichnung auf `true` fest.  
  
3.  Um dem Bezeichnungsfeld eine Zugriffstaste zuzuweisen, verwenden Sie in der <xref:System.Windows.Forms.Label.Text%2A>\-Eigenschaft des Bezeichnungsfelds das kaufmännische Und\-Zeichen \(&\).  Weitere Informationen finden Sie unter [Erstellen von Zugriffstasten für Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Es kann jedoch vorkommen, dass Sie das kaufmännische Und\-Zeichen in einem Label\-Steuerelement als Text und nicht für die Definition einer Zugriffstaste verwenden,  beispielsweise, wenn Sie ein **Label**\-Steuerelement an ein Recordsetfeld binden, das kaufmännische Und\-Zeichen enthält.  Um das kaufmännische Und\-Zeichen in einem Label\-Steuerelement als Text anzuzeigen, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>\-Eigenschaft auf `false` fest.  Wenn Sie mit dem kaufmännischen Und\-Zeichen gleichzeitig Text anzeigen und eine Zugriffstaste definieren, legen Sie die <xref:System.Windows.Forms.Label.UseMnemonic%2A>\-Eigenschaft auf `true` fest und geben für die Zugriffstaste ein kaufmännisches Und\-Zeichen \(&\) und für Text zwei kaufmännische Und\-Zeichen ein.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## Siehe auch  
 [Gewusst wie: Anpassen der Größe des Label\-Steuerelements in Windows Forms an seinen Inhalt](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [Übersicht über das Label\-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)   
 [Label\-Steuerelement](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)