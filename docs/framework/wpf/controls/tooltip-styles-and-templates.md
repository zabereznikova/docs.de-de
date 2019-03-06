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
ms.openlocfilehash: 424cfc196474d342f1efdc049350acb71b8fb1eb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375362"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="fbf3c-102">ToolTip-Formate und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fbf3c-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="fbf3c-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="fbf3c-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fbf3c-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="fbf3c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="fbf3c-106">ToolTip-Teile</span><span class="sxs-lookup"><span data-stu-id="fbf3c-106">ToolTip Parts</span></span>  
 <span data-ttu-id="fbf3c-107">Die <xref:System.Windows.Controls.ToolTip> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="fbf3c-108">QuickInfo-Zustände</span><span class="sxs-lookup"><span data-stu-id="fbf3c-108">ToolTip States</span></span>  
 <span data-ttu-id="fbf3c-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="fbf3c-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="fbf3c-110">VisualState Name</span></span>|<span data-ttu-id="fbf3c-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="fbf3c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fbf3c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbf3c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="fbf3c-113">Closed</span><span class="sxs-lookup"><span data-stu-id="fbf3c-113">Closed</span></span>|<span data-ttu-id="fbf3c-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="fbf3c-114">OpenStates</span></span>|<span data-ttu-id="fbf3c-115">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="fbf3c-115">The default state.</span></span>|  
|<span data-ttu-id="fbf3c-116">Öffnen</span><span class="sxs-lookup"><span data-stu-id="fbf3c-116">Open</span></span>|<span data-ttu-id="fbf3c-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="fbf3c-117">OpenStates</span></span>|<span data-ttu-id="fbf3c-118">Die <xref:System.Windows.Controls.ToolTip> sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="fbf3c-119">Gültig</span><span class="sxs-lookup"><span data-stu-id="fbf3c-119">Valid</span></span>|<span data-ttu-id="fbf3c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf3c-120">ValidationStates</span></span>|<span data-ttu-id="fbf3c-121">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="fbf3c-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fbf3c-122">InvalidFocused</span></span>|<span data-ttu-id="fbf3c-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf3c-123">ValidationStates</span></span>|<span data-ttu-id="fbf3c-124">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="fbf3c-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fbf3c-125">InvalidUnfocused</span></span>|<span data-ttu-id="fbf3c-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fbf3c-126">ValidationStates</span></span>|<span data-ttu-id="fbf3c-127">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="fbf3c-128">QuickInfo-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbf3c-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="fbf3c-129">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.ToolTip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="fbf3c-130">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="fbf3c-131">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fbf3c-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf3c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbf3c-132">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fbf3c-133">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="fbf3c-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="fbf3c-134">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="fbf3c-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="fbf3c-135">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fbf3c-135">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="fbf3c-136">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fbf3c-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
