---
title: "Gewusst wie: Festlegen des Formats f&#252;r das NumericUpDown-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "NumericUpDown-Steuerelement [Windows Forms], Formatieren von Werten"
  - "Auf-Ab-Steuerelemente, Formatieren von numerischen Werten"
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Festlegen des Formats f&#252;r das NumericUpDown-Steuerelement in Windows&#160;Forms
Sie können konfigurieren, wie Werte im <xref:System.Windows.Forms.NumericUpDown>\-Steuerelement in Windows Forms angezeigt werden.  Mit der <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>\-Eigenschaft wird die Anzahl der nach dem Dezimalkomma angezeigten Ziffern festgelegt; der Standardwert ist 0.  Mit der <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>\-Eigenschaft wird festgelegt, ob nach jeder dritten Dezimalstelle ein Trennzeichen eingefügt wird; der Standardwert ist `false`.  Im Steuerelement werden Werte im Hexadezimalformat statt im Dezimalformat angezeigt, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>\-Eigenschaft auf `true` festgelegt wird; der Standardwert ist `false`.  
  
### So formatieren Sie den numerischen Wert  
  
-   Zeigen Sie einen Dezimalwert an, indem Sie für die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>\-Eigenschaft eine ganze Zahl und für die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>\-Eigenschaft den Wert `true` oder `false` festlegen.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     \- oder \-  
  
-   Zeigen Sie einen Hexadezimalwert an, indem Sie für die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>\-Eigenschaft den Wert `true` festlegen.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Auch wenn der Wert auf dem Formular im Hexadezimalformat angezeigt wird, wird bei allen mit der <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft durchgeführten Tests der Dezimalwert verwendet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Übersicht über das NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)