---
title: "Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4ff6d8e584e65482285012af351ebd1a669b806
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Gewusst wie: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms
Sie können konfigurieren, wie Werte in Windows Forms angezeigt werden <xref:System.Windows.Forms.NumericUpDown> Steuerelement. Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft bestimmt, wie viele Ziffern nach dem Dezimaltrennzeichen angezeigt werden; der Standard ist 0. Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> -Eigenschaft bestimmt, ob eine Trennzeichen zwischen allen drei Dezimalstellen eingefügt wird; der Standardwert ist `false`. Das Steuerelement kann Werte im Hexadezimalformat statt Dezimalformat anzeigen, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> -Eigenschaftensatz auf `true`; der Standardwert ist `false`.  
  
### <a name="to-format-the-numeric-value"></a>So formatieren Sie den numerischen Wert  
  
-   Zeigen Sie einen Dezimalwert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft auf eine ganze Zahl und das Festlegen der <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft, um `true` oder `false`.  
  
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
  
-   Anzeigen von einem hexadezimalen Wert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> Eigenschaft `true`.  
  
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
    >  Auch wenn der Wert auf das Formular als eine Hexadezimalzeichenfolge angezeigt wird, alle Tests ausführen auf der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft Tests einen Dezimalwert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Übersicht über das NumericUpDown-Steuerelement](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
