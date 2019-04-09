---
title: 'Vorgehensweise: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: 281fbbd4459230056fcac2e6c684422c91dc0817
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119885"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Vorgehensweise: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms
Der numerische Wert, der die Windows-Formulare <xref:System.Windows.Forms.NumericUpDown> Steuerelement richtet sich nach der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft. Sie können bedingte Tests für den Wert des Steuerelements genau wie bei einer anderen Eigenschaft schreiben. Nach der <xref:System.Windows.Forms.NumericUpDown.Value%2A> festgelegt wird, können Sie sie direkt vom Schreiben von Code zum Ausführen von Operationen anpassen oder Sie rufen die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methoden.  
  
### <a name="to-set-the-numeric-value"></a>Zum Festlegen des numerischen Werts  
  
1.  Weisen Sie einen Wert, der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft im Code oder in das Fenster "Eigenschaften".  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     - oder -   
  
2.  Rufen Sie die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oder <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methode zu erhöhen oder verringern Sie den Wert entsprechend der Angabe in der <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Eigenschaft.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Den numerischen Wert zurückgegeben.  
  
-   Zugriff die <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft im Code.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Übersicht über das NumericUpDown-Steuerelement](numericupdown-control-overview-windows-forms.md)
