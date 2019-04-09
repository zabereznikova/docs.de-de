---
title: 'Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: 990fc996cfb5ecf4d9fde255ad026e3f46a24718
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185782"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="d78b4-102">Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern</span><span class="sxs-lookup"><span data-stu-id="d78b4-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="d78b4-103">Sie können ein Steuerelement am Formularrand ausrichten, indem Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="d78b4-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="d78b4-104">Diese Eigenschaft legt fest, wo auf dem Formular das Steuerelement sich befindet.</span><span class="sxs-lookup"><span data-stu-id="d78b4-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="d78b4-105">Die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft kann auf einen der folgenden Werte festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="d78b4-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="d78b4-106">Einstellung</span><span class="sxs-lookup"><span data-stu-id="d78b4-106">Setting</span></span>|<span data-ttu-id="d78b4-107">Auswirkung auf das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d78b4-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="d78b4-108">Wird im unteren Bereich des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="d78b4-109">Füllt den gesamten verbleibenden Platz im Formular aus.</span><span class="sxs-lookup"><span data-stu-id="d78b4-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="d78b4-110">Wird an der linken Seite des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="d78b4-111">Wird nicht angedockt und wird an der mit der <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft angegebenen Position angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="d78b4-112">Wird an der rechten Seite des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="d78b4-113">Wird im oberen Bereich des Formulars angedockt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="d78b4-114">Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d78b4-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="d78b4-115">So legen Sie die Dock-Eigenschaft für das Steuerelement zur Laufzeit fest</span><span class="sxs-lookup"><span data-stu-id="d78b4-115">To set the Dock property for your control at run time</span></span>  
  
1.  <span data-ttu-id="d78b4-116">Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft im Code auf den geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="d78b4-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d78b4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d78b4-117">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d78b4-118">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d78b4-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="d78b4-119">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d78b4-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="d78b4-120">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d78b4-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d78b4-121">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d78b4-121">AutoSize Property Overview</span></span>](autosize-property-overview.md)
