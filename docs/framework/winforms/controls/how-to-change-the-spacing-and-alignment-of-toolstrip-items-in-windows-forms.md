---
title: 'Vorgehensweise: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 954087fa893baf3aa623c912efb081491304d3fb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719441"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="6ad17-102">Vorgehensweise: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ad17-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="6ad17-103">Die <xref:System.Windows.Forms.ToolStrip> Steuerelement vollständig unterstützt Funktionen wie z. B. das Ändern der Größe, des Abstands des <xref:System.Windows.Forms.ToolStripItem> Steuerelemente relativ zueinander und die Anordnung von Steuerelementen auf der <xref:System.Windows.Forms.ToolStrip>, und der Abstand der Steuerelemente relativ zu den <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ad17-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="6ad17-104">Da der Standardwert der <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> -Eigenschaft ist `true`, Steuerelemente werden automatisch angepasst, es sei denn, Sie legen die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft, um `false`.</span><span class="sxs-lookup"><span data-stu-id="6ad17-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="6ad17-105">Manuell auf einem ToolStripItem Größe</span><span class="sxs-lookup"><span data-stu-id="6ad17-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="6ad17-106">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft `false` für das zugeordnete Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6ad17-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="6ad17-107">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Size%2A> Eigenschaft wie gewünscht, für das zugeordnete <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="6ad17-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="6ad17-108">Um den Abstand eines ToolStripItem festzulegen</span><span class="sxs-lookup"><span data-stu-id="6ad17-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="6ad17-109">Legen Sie die gewünschten Werte in Pixel in der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft des zugeordneten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="6ad17-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="6ad17-110">Die Werte der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft geben den Abstand zwischen dem Element und angrenzenden Elementen in der folgenden Reihenfolge: Links, oben, rechts und unten.</span><span class="sxs-lookup"><span data-stu-id="6ad17-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="6ad17-111">Ausrichten ein ToolStripItem auf die rechte Seite des ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6ad17-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="6ad17-112">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripItemAlignment.Right> für das zugeordnete Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6ad17-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="6ad17-113">Standardmäßig <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> nastaven NA hodnotu <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, die Steuerelemente auf der linken Seite des richtet die <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ad17-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="6ad17-114">ToolStrip-Elementen auf der Toolleiste anordnen</span><span class="sxs-lookup"><span data-stu-id="6ad17-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="6ad17-115">Legen Sie die <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Eigenschaft, um den Wert der <xref:System.Windows.Forms.ToolStripLayoutStyle> , die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="6ad17-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ad17-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ad17-116">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="6ad17-117">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6ad17-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="6ad17-118">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="6ad17-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="6ad17-119">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="6ad17-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
