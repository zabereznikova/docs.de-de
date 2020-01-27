---
title: Layout von Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: ed8603e997e7d0c1ed7a2ebda6dc960726d32f45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745249"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="a8af3-102">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a8af3-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="a8af3-103">Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="a8af3-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="a8af3-104">Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace bietet Ihnen viele Layouttools, um dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a8af3-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a8af3-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a8af3-105">In This Section</span></span>

<span data-ttu-id="a8af3-106">[Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a8af3-106">[AutoSize Property Overview](autosize-property-overview.md)</span></span>\
<span data-ttu-id="a8af3-107">Beschreibt die <xref:System.Windows.Forms.Control.AutoSize%2A>-Eigenschaft und ihre Rolle im Layout.</span><span class="sxs-lookup"><span data-stu-id="a8af3-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="a8af3-108">[Margin und Padding in Windows Forms Steuerelementen](margin-and-padding-in-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="a8af3-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)</span></span>\
<span data-ttu-id="a8af3-109">Beschreibt die Eigenschaften von <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> sowie deren Rollen im Layout.</span><span class="sxs-lookup"><span data-stu-id="a8af3-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="a8af3-110">Gewusst [wie: Ausrichten eines Steuer Elements an den Kanten von Formularen](how-to-align-a-control-to-the-edges-of-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8af3-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)</span></span>\
<span data-ttu-id="a8af3-111">Veranschaulicht, wie Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft verwenden, um das Steuerelement an der Kante des Formulars auszurichten, das es einnimmt.</span><span class="sxs-lookup"><span data-stu-id="a8af3-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="a8af3-112">Gewusst [wie: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span><span class="sxs-lookup"><span data-stu-id="a8af3-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span></span>\
<span data-ttu-id="a8af3-113">Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft verwendet wird, um ein Steuerelement zu gliedern.</span><span class="sxs-lookup"><span data-stu-id="a8af3-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="a8af3-114">Gewusst [wie: Implementieren eines benutzerdefinierten Layoutmoduls](how-to-implement-a-custom-layout-engine.md)</span><span class="sxs-lookup"><span data-stu-id="a8af3-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)</span></span>\
<span data-ttu-id="a8af3-115">Veranschaulicht, wie eine <xref:System.Windows.Forms.Layout.LayoutEngine> zum Anordnen von Windows Forms Steuerelementen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a8af3-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="a8af3-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="a8af3-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="a8af3-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a8af3-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="a8af3-118">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a8af3-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8af3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8af3-119">See also</span></span>

- [<span data-ttu-id="a8af3-120">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8af3-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="a8af3-121">Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8af3-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="a8af3-122">Gewusst wie: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="a8af3-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="a8af3-123">Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a8af3-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
