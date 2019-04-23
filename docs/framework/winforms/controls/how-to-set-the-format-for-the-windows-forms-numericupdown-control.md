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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186140"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="cb04e-102">Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb04e-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="cb04e-103">Sie können konfigurieren, wie Werte in Windows Forms angezeigt werden <xref:System.Windows.Forms.NumericUpDown> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cb04e-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="cb04e-104">Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft bestimmt, wie viele Ziffern nach dem Dezimaltrennzeichen angezeigt; der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="cb04e-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="cb04e-105">Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft bestimmt, ob eine Trennzeichen zwischen allen drei Dezimalstellen eingefügt wird; der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="cb04e-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="cb04e-106">Das Steuerelement kann Werte im Hexadezimalformat statt decimal-Format angezeigt, wenn die <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> -Eigenschaftensatz auf `true`; der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="cb04e-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="cb04e-107">Den numerischen Wert formatiert.</span><span class="sxs-lookup"><span data-stu-id="cb04e-107">To format the numeric value</span></span>  
  
-   <span data-ttu-id="cb04e-108">Zeigen Sie einen Dezimalwert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> Eigenschaft eine ganze Zahl und die Einstellung der <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> Eigenschaft `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="cb04e-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="cb04e-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="cb04e-109">-or-</span></span>  
  
-   <span data-ttu-id="cb04e-110">Zeigen Sie einen hexadezimalen Wert durch Festlegen der <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="cb04e-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="cb04e-111">Auch wenn der Wert auf das Formular als eine Hexadezimalzeichenfolge angezeigt wird, alle Tests ausführen auf der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft wird der decimal-Wert testen.</span><span class="sxs-lookup"><span data-stu-id="cb04e-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb04e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb04e-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="cb04e-113">NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb04e-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="cb04e-114">Übersicht über das NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cb04e-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
