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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="f2bfc-102">Vorgehensweise: Festlegen des Formats für das NumericUpDown-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2bfc-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="f2bfc-103">Sie können konfigurieren, wie Werte im Windows Forms <xref:System.Windows.Forms.NumericUpDown> Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="f2bfc-104">Die <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> -Eigenschaft bestimmt, wie viele Zahlen nach dem Dezimaltrennzeichen angezeigt werden. der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="f2bfc-105">Die <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> -Eigenschaft bestimmt, ob zwischen allen drei Dezimalziffern ein Trennzeichen eingefügt wird. der `false`Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="f2bfc-106">Das-Steuerelement kann Werte im Hexadezimal Format anstelle des Dezimal Formats <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> anzeigen, wenn die `true`-Eigenschaft auf fest `false`gelegt ist. der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="f2bfc-107">So formatieren Sie den numerischen Wert</span><span class="sxs-lookup"><span data-stu-id="f2bfc-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="f2bfc-108">Zeigen Sie einen Dezimalwert an, <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> indem Sie die-Eigenschaft auf eine <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> ganze Zahl festlegen `false`und die-Eigenschaft auf `true` oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="f2bfc-109">-oder-</span><span class="sxs-lookup"><span data-stu-id="f2bfc-109">-or-</span></span>  
  
- <span data-ttu-id="f2bfc-110">Zeigen Sie einen Hexadezimalwert an <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> , indem `true`Sie die-Eigenschaft auf festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="f2bfc-111">Auch wenn der Wert im Formular als hexadezimal angezeigt wird, testen alle Tests, die Sie <xref:System.Windows.Forms.NumericUpDown.Value%2A> für die Eigenschaft ausführen, den Dezimalwert.</span><span class="sxs-lookup"><span data-stu-id="f2bfc-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bfc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2bfc-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="f2bfc-113">NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f2bfc-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="f2bfc-114">Übersicht über das NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f2bfc-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
