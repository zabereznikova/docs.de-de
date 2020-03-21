---
title: 'Gewusst wie: Ändern des Abstands und der Ausrichtung von ToolStrip-Elementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182231"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="5b00b-102">Gewusst wie: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b00b-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="5b00b-103">Das <xref:System.Windows.Forms.ToolStrip> Steuerelement unterstützt Layout-Features wie die <xref:System.Windows.Forms.ToolStripItem> Größenänderung, den Abstand der Steuerelemente <xref:System.Windows.Forms.ToolStrip>relativ zueinander, die <xref:System.Windows.Forms.ToolStrip>Anordnung von Steuerelementen auf dem und den Abstand von Steuerelementen relativ zum .</span><span class="sxs-lookup"><span data-stu-id="5b00b-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="5b00b-104">Da der Standardwert <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> der `true`Eigenschaft ist , werden <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Steuerelemente `false`automatisch angepasst, es sei denn, Sie legen die Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="5b00b-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="5b00b-105">So vergrößern Sie ein ToolStripItem manuell</span><span class="sxs-lookup"><span data-stu-id="5b00b-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="5b00b-106">Legen <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Sie `false` die Eigenschaft für das zugeordnete Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="5b00b-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="5b00b-107">Legen <xref:System.Windows.Forms.ToolStripItem.Size%2A> Sie die Eigenschaft so <xref:System.Windows.Forms.ToolStripItem>fest, wie Sie es für die zugeordnete benötigen.</span><span class="sxs-lookup"><span data-stu-id="5b00b-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="5b00b-108">So legen Sie den Abstand eines ToolStripItem fest</span><span class="sxs-lookup"><span data-stu-id="5b00b-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="5b00b-109">Fügen Sie die gewünschten Werte in <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Pixel in die Eigenschaft des zugeordneten Steuerelements ein.</span><span class="sxs-lookup"><span data-stu-id="5b00b-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="5b00b-110">Die Werte <xref:System.Windows.Forms.ToolStripItem.Margin%2A> der Eigenschaft geben den Abstand zwischen dem Element und benachbarten Elementen in dieser Reihenfolge an: Links, Oben, Rechts und Unten.</span><span class="sxs-lookup"><span data-stu-id="5b00b-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="5b00b-111">So richten Sie ein ToolStripItem auf der rechten Seite des ToolStrip aus</span><span class="sxs-lookup"><span data-stu-id="5b00b-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="5b00b-112">Legen <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Sie <xref:System.Windows.Forms.ToolStripItemAlignment.Right> die Eigenschaft für das zugeordnete Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="5b00b-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="5b00b-113">Standardmäßig ist <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> auf <xref:System.Windows.Forms.ToolStripItemAlignment.Left>festgelegt, das Steuerelemente auf der <xref:System.Windows.Forms.ToolStrip>linken Seite des ausrichtet.</span><span class="sxs-lookup"><span data-stu-id="5b00b-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="5b00b-114">So ordnen Sie ToolStrip-Elemente auf dem ToolStrip an</span><span class="sxs-lookup"><span data-stu-id="5b00b-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="5b00b-115">Legen <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Sie die Eigenschaft <xref:System.Windows.Forms.ToolStripLayoutStyle> auf den gewünschten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="5b00b-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b00b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b00b-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="5b00b-117">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b00b-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="5b00b-118">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5b00b-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="5b00b-119">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="5b00b-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
