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
ms.openlocfilehash: c73200eb1c373f1d723ba82f2e6be5b625496b59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902225"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="9acde-102">Vorgehensweise: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9acde-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="9acde-103">Der numerische Wert, der die Windows-Formulare <xref:System.Windows.Forms.NumericUpDown> Steuerelement richtet sich nach der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9acde-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="9acde-104">Sie können bedingte Tests für den Wert des Steuerelements genau wie bei einer anderen Eigenschaft schreiben.</span><span class="sxs-lookup"><span data-stu-id="9acde-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="9acde-105">Nach der <xref:System.Windows.Forms.NumericUpDown.Value%2A> festgelegt wird, können Sie sie direkt vom Schreiben von Code zum Ausführen von Operationen anpassen oder Sie rufen die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="9acde-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="9acde-106">Zum Festlegen des numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="9acde-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="9acde-107">Weisen Sie einen Wert, der <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft im Code oder in das Fenster "Eigenschaften".</span><span class="sxs-lookup"><span data-stu-id="9acde-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="9acde-108">- oder - </span><span class="sxs-lookup"><span data-stu-id="9acde-108">-or-</span></span>  
  
2. <span data-ttu-id="9acde-109">Rufen Sie die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oder <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methode zu erhöhen oder verringern Sie den Wert entsprechend der Angabe in der <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9acde-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="9acde-110">Den numerischen Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9acde-110">To return the numeric value</span></span>  
  
- <span data-ttu-id="9acde-111">Zugriff die <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft im Code.</span><span class="sxs-lookup"><span data-stu-id="9acde-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9acde-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9acde-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9acde-113">NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9acde-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="9acde-114">Übersicht über das NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9acde-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
