---
title: Bezeichnungsformate und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: d2bb348fc9c0348fd8093452e022df7ab4e0b3f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696248"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="45442-102">Bezeichnungsformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="45442-102">Label Styles and Templates</span></span>
<span data-ttu-id="45442-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="45442-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="45442-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement eine unverwechselbare Darstellung verleihen.</span><span class="sxs-lookup"><span data-stu-id="45442-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="45442-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="45442-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="45442-106">Bezeichnung Teilen</span><span class="sxs-lookup"><span data-stu-id="45442-106">Label Parts</span></span>  
 <span data-ttu-id="45442-107">Die <xref:System.Windows.Controls.Label> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="45442-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="45442-108">Label-Status</span><span class="sxs-lookup"><span data-stu-id="45442-108">Label States</span></span>  
 <span data-ttu-id="45442-109">Die folgende Tabelle enthält die visuellen Zustände für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="45442-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="45442-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="45442-110">VisualState Name</span></span>|<span data-ttu-id="45442-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="45442-111">VisualStateGroup Name</span></span>|<span data-ttu-id="45442-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45442-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="45442-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="45442-113">Valid</span></span>|<span data-ttu-id="45442-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45442-114">ValidationStates</span></span>|<span data-ttu-id="45442-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="45442-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="45442-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="45442-116">InvalidFocused</span></span>|<span data-ttu-id="45442-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45442-117">ValidationStates</span></span>|<span data-ttu-id="45442-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="45442-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="45442-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="45442-119">InvalidUnfocused</span></span>|<span data-ttu-id="45442-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45442-120">ValidationStates</span></span>|<span data-ttu-id="45442-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement keinen Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="45442-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="45442-122">Label-ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="45442-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="45442-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.Label> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="45442-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="45442-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="45442-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="45442-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="45442-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45442-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45442-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="45442-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="45442-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="45442-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="45442-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="45442-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="45442-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="45442-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="45442-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
