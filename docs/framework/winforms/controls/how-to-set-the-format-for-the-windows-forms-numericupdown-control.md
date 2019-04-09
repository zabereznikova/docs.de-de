---
title: 'Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186140"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms
Sie können konfigurieren, wie Werte in Windows Forms angezeigt werden <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft bestimmt, wie viele Ziffern nach dem Dezimaltrennzeichen angezeigt; der Standardwert ist 0. Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft bestimmt, ob eine Trennzeichen zwischen allen drei Dezimalstellen eingefügt wird; der Standardwert ist `false`. Das Steuerelement kann Werte im Hexadezimalformat statt decimal-Format angezeigt, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> -Eigenschaftensatz auf `true`; der Standardwert ist `false`.  
  
### <a name="to-format-the-numeric-value"></a>Den numerischen Wert formatiert.  
  
-   Zeigen Sie einen Dezimalwert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft eine ganze Zahl und die Einstellung der <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft `true` oder `false`.  
  
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
  
     - oder -   
  
-   Zeigen Sie einen hexadezimalen Wert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> Eigenschaft `true`.  
  
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
    >  Auch wenn der Wert auf das Formular als eine Hexadezimalzeichenfolge angezeigt wird, alle Tests ausführen auf der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft wird der decimal-Wert testen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Übersicht über das NumericUpDown-Steuerelement](numericupdown-control-overview-windows-forms.md)
