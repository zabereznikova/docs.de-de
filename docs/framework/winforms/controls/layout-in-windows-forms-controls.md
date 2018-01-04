---
title: Layout in Windows Forms-Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windws Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9112269da02bd7eff9838509673db7adbc3fb53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="aea95-102">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="aea95-102">Layout in Windows Forms Controls</span></span>
<span data-ttu-id="aea95-103">Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="aea95-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="aea95-104">Die <xref:System.Windows.Forms?displayProperty=nameWithType> Namespace bietet Ihnen viele Layout-Tools, um dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="aea95-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aea95-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aea95-105">In This Section</span></span>  
 [<span data-ttu-id="aea95-106">Übersicht über die AutoSize-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="aea95-106">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 <span data-ttu-id="aea95-107">Beschreibt die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft und der Rolle im Layout.</span><span class="sxs-lookup"><span data-stu-id="aea95-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>  
  
 [<span data-ttu-id="aea95-108">Rand und Abstand in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="aea95-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)  
 <span data-ttu-id="aea95-109">Beschreibt die <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaften und ihre Rollen im Layout.</span><span class="sxs-lookup"><span data-stu-id="aea95-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>  
  
 [<span data-ttu-id="aea95-110">Gewusst wie: Ausrichten eines Steuerelements an Formularrändern</span><span class="sxs-lookup"><span data-stu-id="aea95-110">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 <span data-ttu-id="aea95-111">Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft, um das Steuerelement an den Rand des Formulars auszurichten es einnimmt.</span><span class="sxs-lookup"><span data-stu-id="aea95-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="aea95-112">Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abständen</span><span class="sxs-lookup"><span data-stu-id="aea95-112">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)  
 <span data-ttu-id="aea95-113">Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft ein Steuerelements werden kann.</span><span class="sxs-lookup"><span data-stu-id="aea95-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>  
  
 [<span data-ttu-id="aea95-114">Gewusst wie: Implementieren eines benutzerdefinierten Layoutmoduls</span><span class="sxs-lookup"><span data-stu-id="aea95-114">How to: Implement a Custom Layout Engine</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)  
 <span data-ttu-id="aea95-115">Veranschaulicht das Implementieren einer <xref:System.Windows.Forms.Layout.LayoutEngine> zum Anordnen von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="aea95-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aea95-116">Verweis</span><span class="sxs-lookup"><span data-stu-id="aea95-116">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="aea95-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aea95-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="aea95-118">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aea95-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea95-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aea95-119">See Also</span></span>  
 [<span data-ttu-id="aea95-120">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aea95-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="aea95-121">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aea95-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="aea95-122">Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="aea95-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="aea95-123">Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="aea95-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
