---
title: ToolTip-Formate und Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 626d0b4d49d653f820d1506f0aa09f06d26352c2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458644"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="ff535-102">ToolTip-Formate und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ff535-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="ff535-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.ToolTip>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff535-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="ff535-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="ff535-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ff535-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ff535-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="ff535-106">QuickInfo-Teile</span><span class="sxs-lookup"><span data-stu-id="ff535-106">ToolTip Parts</span></span>  
 <span data-ttu-id="ff535-107">Das <xref:System.Windows.Controls.ToolTip>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="ff535-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="ff535-108">QuickInfo-Zustände</span><span class="sxs-lookup"><span data-stu-id="ff535-108">ToolTip States</span></span>  
 <span data-ttu-id="ff535-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.ToolTip>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ff535-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="ff535-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="ff535-110">VisualState Name</span></span>|<span data-ttu-id="ff535-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="ff535-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ff535-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff535-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ff535-113">Closed</span><span class="sxs-lookup"><span data-stu-id="ff535-113">Closed</span></span>|<span data-ttu-id="ff535-114">Openstates</span><span class="sxs-lookup"><span data-stu-id="ff535-114">OpenStates</span></span>|<span data-ttu-id="ff535-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="ff535-115">The default state.</span></span>|  
|<span data-ttu-id="ff535-116">Öffnen</span><span class="sxs-lookup"><span data-stu-id="ff535-116">Open</span></span>|<span data-ttu-id="ff535-117">Openstates</span><span class="sxs-lookup"><span data-stu-id="ff535-117">OpenStates</span></span>|<span data-ttu-id="ff535-118">Der <xref:System.Windows.Controls.ToolTip> ist sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ff535-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="ff535-119">Gültig</span><span class="sxs-lookup"><span data-stu-id="ff535-119">Valid</span></span>|<span data-ttu-id="ff535-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ff535-120">ValidationStates</span></span>|<span data-ttu-id="ff535-121">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ff535-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ff535-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ff535-122">InvalidFocused</span></span>|<span data-ttu-id="ff535-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ff535-123">ValidationStates</span></span>|<span data-ttu-id="ff535-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="ff535-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ff535-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ff535-125">InvalidUnfocused</span></span>|<span data-ttu-id="ff535-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ff535-126">ValidationStates</span></span>|<span data-ttu-id="ff535-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="ff535-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="ff535-128">QuickInfo-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff535-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="ff535-129">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.ToolTip>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="ff535-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="ff535-130">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff535-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ff535-131">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ff535-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff535-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff535-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ff535-133">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="ff535-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ff535-134">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ff535-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ff535-135">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ff535-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ff535-136">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ff535-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
