---
title: "Gewusst wie: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms"
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
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42ae53e143942201359baebdfa8929647e7e35cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="d16a6-102">Gewusst wie: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d16a6-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="d16a6-103">Die <xref:System.Windows.Forms.ToolStrip> Steuerelement vollständig unterstützt Layoutfunktionen, z. B. das Ändern der Größe, des Abstands des <xref:System.Windows.Forms.ToolStripItem> steuert im Verhältnis zueinander, die Anordnung der Steuerelemente auf die <xref:System.Windows.Forms.ToolStrip>, und der Abstand der Steuerelemente relativ zu den <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d16a6-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="d16a6-104">Da der Standardwert der <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft ist `true`, Steuerelemente werden automatisch angepasst, es sei denn, Sie legen die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="d16a6-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="d16a6-105">Manuell auf einem ToolStripItem Größe anpassen</span><span class="sxs-lookup"><span data-stu-id="d16a6-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="d16a6-106">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft `false` für das zugeordnete Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d16a6-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="d16a6-107">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Size%2A> Eigenschaft wie gewünscht für den zugeordneten <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="d16a6-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="d16a6-108">Die Abstand zwischen einem ToolStripItem festlegen</span><span class="sxs-lookup"><span data-stu-id="d16a6-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="d16a6-109">Fügen Sie die gewünschten Werte in Pixel in der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft des zugeordneten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="d16a6-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="d16a6-110">Die Werte der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft geben den Abstand zwischen dem Element und angrenzenden Elementen in dieser Reihenfolge: linken, oberen, rechten und unteren.</span><span class="sxs-lookup"><span data-stu-id="d16a6-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="d16a6-111">Ausrichten ein ToolStripItem auf die rechte Seite des ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d16a6-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="d16a6-112">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripItemAlignment.Right> für das zugeordnete Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d16a6-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="d16a6-113">Standardmäßig <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> festgelegt ist, um <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, Steuerelemente auf der linken Seite des richtet die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d16a6-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="d16a6-114">ToolStrip-Elementen auf der Toolleiste anordnen</span><span class="sxs-lookup"><span data-stu-id="d16a6-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="d16a6-115">Legen Sie die <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> auf den Wert der Eigenschaft <xref:System.Windows.Forms.ToolStripLayoutStyle> , die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="d16a6-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d16a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d16a6-116">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="d16a6-117">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d16a6-117">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="d16a6-118">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="d16a6-118">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="d16a6-119">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="d16a6-119">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
