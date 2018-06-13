---
title: 'Gewusst wie: Horizontales Teilen eines Fensters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 1e097ce5623fab4c3c8c1d59d9bc8c9206abee2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533126"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="97771-102">Gewusst wie: Horizontales Teilen eines Fensters</span><span class="sxs-lookup"><span data-stu-id="97771-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="97771-103">Im folgenden Codebeispiel wird der Splitter generiert, durch die dividiert das <xref:System.Windows.Forms.SplitContainer> Steuerelement Horizontal.</span><span class="sxs-lookup"><span data-stu-id="97771-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97771-104">Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft von der <xref:System.Windows.Forms.SplitContainer> Steuerelement bestimmt die Richtung des Splitters, nicht des Steuerelements selbst.</span><span class="sxs-lookup"><span data-stu-id="97771-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="97771-105">Um ein Fenster horizontal teilen</span><span class="sxs-lookup"><span data-stu-id="97771-105">To split a window horizontally</span></span>  
  
1.  <span data-ttu-id="97771-106">Innerhalb einer Prozedur Festlegen der <xref:System.Windows.Forms.SplitContainer.Orientation%2A> Eigenschaft von der <xref:System.Windows.Forms.SplitContainer> die Steuerung an <xref:System.Windows.Forms.Orientation.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="97771-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97771-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97771-107">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="97771-108">SplitContainer-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="97771-108">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
