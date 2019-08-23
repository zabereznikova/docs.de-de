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
ms.openlocfilehash: 6db7a1b2aeb7282c3ac827cb8319706ed348fc22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949152"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms
Sie können konfigurieren, wie Werte im Windows Forms <xref:System.Windows.Forms.NumericUpDown> Steuerelement angezeigt werden. Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> -Eigenschaft bestimmt, wie viele Zahlen nach dem Dezimaltrennzeichen angezeigt werden. der Standardwert ist 0. Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> -Eigenschaft bestimmt, ob zwischen allen drei Dezimalziffern ein Trennzeichen eingefügt wird. der `false`Standardwert ist. Das-Steuerelement kann Werte im Hexadezimal Format anstelle des Dezimal Formats <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> anzeigen, wenn die `true`-Eigenschaft auf fest `false`gelegt ist. der Standardwert ist.  
  
### <a name="to-format-the-numeric-value"></a>So formatieren Sie den numerischen Wert  
  
- Zeigen Sie einen Dezimalwert an, <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> indem Sie die-Eigenschaft auf eine <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> ganze Zahl festlegen `false`und die-Eigenschaft auf `true` oder festlegen.  
  
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
  
     -oder-  
  
- Zeigen Sie einen Hexadezimalwert an <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> , indem `true`Sie die-Eigenschaft auf festlegen.  
  
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
    > Auch wenn der Wert im Formular als hexadezimal angezeigt wird, testen alle Tests, die Sie <xref:System.Windows.Forms.NumericUpDown.Value%2A> für die Eigenschaft ausführen, den Dezimalwert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown-Steuerelement](numericupdown-control-windows-forms.md)
- [Übersicht über das NumericUpDown-Steuerelement](numericupdown-control-overview-windows-forms.md)
