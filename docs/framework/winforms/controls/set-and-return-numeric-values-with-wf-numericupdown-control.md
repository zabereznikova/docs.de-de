---
title: "Gewusst wie: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms"
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
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7bd296fb8a761527e132aecfed9310208f56222
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="23de2-102">Gewusst wie: Festlegen und Zurückgeben von numerischen Werten mit dem NumericUpDown-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23de2-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="23de2-103">Der numerische Wert des Windows Forms <xref:System.Windows.Forms.NumericUpDown> Steuerelement richtet sich nach seiner <xref:System.Windows.Forms.NumericUpDown.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23de2-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="23de2-104">Sie können die bedingte Tests für den Wert des Steuerelements wie bei einer anderen Eigenschaft schreiben.</span><span class="sxs-lookup"><span data-stu-id="23de2-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="23de2-105">Einmal die <xref:System.Windows.Forms.NumericUpDown.Value%2A> festgelegt wird, können Sie es direkt durch Schreiben von Code zum Ausführen von Vorgängen auf Anpassen oder Sie erreichen die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> und <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="23de2-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="23de2-106">Zum Festlegen des numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="23de2-106">To set the numeric value</span></span>  
  
1.  <span data-ttu-id="23de2-107">Weisen Sie einen Wert, der <xref:System.Windows.Forms.NumericUpDown.Value%2A> -Eigenschaft im Code oder im Eigenschaftenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23de2-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="23de2-108">- oder - </span><span class="sxs-lookup"><span data-stu-id="23de2-108">-or-</span></span>  
  
2.  <span data-ttu-id="23de2-109">Rufen Sie die <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> oder <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> Methode zu erhöhen oder verringern Sie den Wert entsprechend der Angabe der <xref:System.Windows.Forms.NumericUpDown.Increment%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23de2-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="23de2-110">Um den numerischen Wert zurückzugeben</span><span class="sxs-lookup"><span data-stu-id="23de2-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="23de2-111">Zugriff der <xref:System.Windows.Forms.NumericUpDown.Value%2A> -Eigenschaft im Code.</span><span class="sxs-lookup"><span data-stu-id="23de2-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23de2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23de2-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="23de2-113">NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="23de2-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="23de2-114">Übersicht über das NumericUpDown-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="23de2-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
