---
title: "Gewusst wie: Festlegen und Zur&#252;ckgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Numerische Werte, Windows Forms"
  - "NumericUpDown-Steuerelement [Windows Forms], Festlegen und Zurückgeben von Werten"
  - "Windows Forms-Steuerelemente, NumericUpDown"
  - "Windows Forms, Numerische Werte"
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Festlegen und Zur&#252;ckgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows&#160;Forms
Der numerische Wert des <xref:System.Windows.Forms.NumericUpDown>\-Steuerelements in Windows Forms wird durch seine <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft bestimmt.  Für den Wert des Steuerelements können Sie ebenso wie für alle anderen Eigenschaften Bedingungsabfragen schreiben.  Sobald die <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft festgelegt wurde, können Sie diese direkt durch Code zum Ausführen von Operationen oder durch Aufrufen der Methoden <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> anpassen.  
  
### So legen Sie den numerischen Wert fest  
  
1.  Weisen Sie der <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft im Code oder im Eigenschaftenfenster einen Wert zu.  
  
    ```vb  
    NumericUpDown1.Value = 55  
  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     \- oder \-  
  
2.  Rufen Sie die Methode <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oder <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> auf, um den Wert entsprechend der Angabe in der <xref:System.Windows.Forms.NumericUpDown.Increment%2A>\-Eigenschaft zu erhöhen oder zu verringern.  
  
    ```vb  
    NumericUpDown1.UpButton()  
  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### So geben Sie den numerischen Wert zurück  
  
-   Greifen Sie im Code auf die <xref:System.Windows.Forms.NumericUpDown.Value%2A>\-Eigenschaft zu.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>   
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=fullName>   
 [NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Übersicht über das NumericUpDown\-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)