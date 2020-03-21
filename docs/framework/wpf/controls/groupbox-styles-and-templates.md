---
title: GroupBox-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187475"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="062db-102">GroupBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="062db-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="062db-103">In diesem Thema werden die <xref:System.Windows.Controls.GroupBox> Stile und Vorlagen für das Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="062db-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="062db-104">Sie können die <xref:System.Windows.Controls.ControlTemplate> Standardeinstellung ändern, um dem Steuerelement ein eindeutiges Erscheinungsbild zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="062db-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="062db-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein Steuerelement](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="062db-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="062db-106">GroupBox-Teile</span><span class="sxs-lookup"><span data-stu-id="062db-106">GroupBox Parts</span></span>  
 <span data-ttu-id="062db-107">Das <xref:System.Windows.Controls.GroupBox> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="062db-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="062db-108">GroupBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="062db-108">GroupBox States</span></span>  
 <span data-ttu-id="062db-109">In der folgenden Tabelle sind <xref:System.Windows.Controls.GroupBox> die visuellen Zustände für das Steuerelement aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="062db-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="062db-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="062db-110">VisualState Name</span></span>|<span data-ttu-id="062db-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="062db-111">VisualStateGroup Name</span></span>|<span data-ttu-id="062db-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="062db-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="062db-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="062db-113">Valid</span></span>|<span data-ttu-id="062db-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="062db-114">ValidationStates</span></span>|<span data-ttu-id="062db-115">Das Steuerelement <xref:System.Windows.Controls.Validation> verwendet die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Klasse, `false`und die angefügte Eigenschaft ist .</span><span class="sxs-lookup"><span data-stu-id="062db-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="062db-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="062db-116">InvalidFocused</span></span>|<span data-ttu-id="062db-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="062db-117">ValidationStates</span></span>|<span data-ttu-id="062db-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft hat das Steuerelement hat den Fokus.</span><span class="sxs-lookup"><span data-stu-id="062db-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="062db-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="062db-119">InvalidUnfocused</span></span>|<span data-ttu-id="062db-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="062db-120">ValidationStates</span></span>|<span data-ttu-id="062db-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte `true` Eigenschaft hat das Steuerelement hat keinen Fokus.</span><span class="sxs-lookup"><span data-stu-id="062db-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="062db-122">GroupBox ControlTemplate Beispiel</span><span class="sxs-lookup"><span data-stu-id="062db-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="062db-123">Das folgende Beispiel zeigt, <xref:System.Windows.Controls.ControlTemplate> wie <xref:System.Windows.Controls.GroupBox> sie eine für das Steuerelement definieren.</span><span class="sxs-lookup"><span data-stu-id="062db-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="062db-124">Der <xref:System.Windows.Controls.ControlTemplate> verwendet eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="062db-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="062db-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="062db-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062db-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="062db-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="062db-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="062db-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="062db-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="062db-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="062db-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="062db-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="062db-130">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="062db-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
