---
title: Festlegen des Formats für das NumericUpDown-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742174"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms
Sie können konfigurieren, wie Werte im Windows Forms <xref:System.Windows.Forms.NumericUpDown>-Steuerelement angezeigt werden. Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>-Eigenschaft bestimmt, wie viele Zahlen nach dem Dezimaltrennzeichen angezeigt werden. der Standardwert ist 0. Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>-Eigenschaft bestimmt, ob zwischen allen drei Dezimalziffern ein Trennzeichen eingefügt wird. der Standardwert ist `false`. Das-Steuerelement kann Werte im Hexadezimal Format anstelle des Dezimal Formats anzeigen, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>-Eigenschaft auf `true`festgelegt ist. der Standardwert ist `false`.  
  
### <a name="to-format-the-numeric-value"></a>So formatieren Sie den numerischen Wert  
  
- Zeigen Sie einen Dezimalwert an, indem Sie die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>-Eigenschaft auf eine ganze Zahl festlegen und die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>-Eigenschaft auf `true` oder `false`festlegen.  
  
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
  
     Oder  
  
- Zeigen Sie einen Hexadezimalwert an, indem Sie die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>-Eigenschaft auf `true`festlegen.  
  
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
    > Auch wenn der Wert im Formular als hexadezimal angezeigt wird, testen alle Tests, die Sie für die <xref:System.Windows.Forms.NumericUpDown.Value%2A>-Eigenschaft ausführen, den Dezimalwert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Übersicht über das NumericUpDown-Steuerelement](numericupdown-control-overview-windows-forms.md)
