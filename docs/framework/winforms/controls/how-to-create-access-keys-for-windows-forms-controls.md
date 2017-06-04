---
title: "Gewusst wie: Erstellen von Zugriffstasten f&#252;r Windows&#160;Forms-Steuerelemente | Microsoft Docs"
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
  - "ALT-TASTE"
  - "Kaufmännisches Und-Zeichen in Tastenkombination"
  - "Button-Steuerelement [Windows Forms], Zugriffstasten"
  - "Steuerelemente [Windows Forms], Zugriffstasten"
  - "Dialogfeldsteuerelemente, Zugriffstasten"
  - "Beispiele [Windows Forms], Steuerelemente"
  - "Tastenkombinationen, Erstellen für Steuerelemente"
  - "Zugriffstasten"
  - "Zugriffstasten, Hinzufügen zu Dialogfeld-Steuerelementen"
  - "Text-Eigenschaft, Angeben von Zugriffstasten für Steuerelemente"
  - "Windows Forms-Steuerelemente, Zugriffstasten"
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Erstellen von Zugriffstasten f&#252;r Windows&#160;Forms-Steuerelemente
Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs oder Menüelements oder in der Beschriftung eines Steuerelements, z. B. einer Schaltfläche.  Somit können die Benutzer durch gleichzeitiges Drücken der ALT\-TASTE und der vordefinierten Zugriffstaste auf eine Schaltfläche "klicken".  Ein Beispiel: Wenn eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und ihre `Text`\-Eigenschaft daher auf "Drucken" festgelegt ist, wird der Buchstabe "D" durch Hinzufügen eines kaufmännischen Und\-Zeichens vor diesem Buchstaben zur Laufzeit im Schaltflächentext unterstrichen angezeigt.  Der Benutzer kann den der Schaltfläche zugeordneten Befehl durch Drücken von ALT\+P ausführen.  Tastenkombinationen für Steuerelemente, die den Fokus nicht erhalten können, sind nicht zulässig.  
  
### So erstellen Sie eine Tastenkombination für ein Steuerelement  
  
1.  Legen Sie für die `Text`\-Eigenschaft eine Zeichenfolge fest, die ein kaufmännisches Und\-Zeichen \(&\) vor dem Buchstaben der Tastenkombination enthält.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Wenn Sie in einer Beschriftung ein kaufmännisches Und\-Zeichen einfügen möchten, ohne eine Zugriffstaste zu erstellen, verwenden Sie zwei kaufmännische Und\-Zeichen \(&&\).  Nur ein einzelnes kaufmännisches Und\-Zeichen wird in der Beschriftung angezeigt, und es werden keine Zeichen unterstrichen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Button>   
 [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Gewusst wie: Festlegen des durch ein Windows Forms\-Steuerelement angezeigten Textes](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)