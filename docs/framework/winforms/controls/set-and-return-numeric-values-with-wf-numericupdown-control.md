---
title: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement
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
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743022"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Gewusst wie: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms
Der numerische Wert des Windows Forms <xref:System.Windows.Forms.NumericUpDown> Steuer Elements wird durch seine <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft bestimmt. Sie können bedingte Tests für den Wert des Steuer Elements wie jede andere Eigenschaft schreiben. Nachdem Sie die <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft festgelegt haben, können Sie Sie direkt anpassen, indem Sie Code zum Ausführen von Vorgängen schreiben, oder Sie können die Methoden <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> aufzurufen.  
  
### <a name="to-set-the-numeric-value"></a>So legen Sie den numerischen Wert fest  
  
1. Weisen Sie der <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft im Code oder in der Eigenschaftenfenster einen Wert zu.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     \- oder -  
  
2. Ruft den <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oder <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methode auf, um den Wert um den in der <xref:System.Windows.Forms.NumericUpDown.Increment%2A>-Eigenschaft angegebenen Betrag zu vergrößern oder zu verkleinern.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>So geben Sie den numerischen Wert zurück  
  
- Greifen Sie im Code auf die <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft zu.  
  
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
