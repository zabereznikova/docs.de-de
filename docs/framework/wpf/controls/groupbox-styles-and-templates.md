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
ms.openlocfilehash: e5befffc86f26176da4accfc01239a08d4978713
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283766"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="afffa-102">GroupBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="afffa-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="afffa-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Controls.GroupBox>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afffa-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="afffa-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="afffa-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="afffa-105">Weitere Informationen finden Sie unter [Erstellen einer Vorlage für ein-Steuer](../../../desktop-wpf/themes/how-to-create-apply-template.md)Element.</span><span class="sxs-lookup"><span data-stu-id="afffa-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="afffa-106">GroupBox-Teile</span><span class="sxs-lookup"><span data-stu-id="afffa-106">GroupBox Parts</span></span>  
 <span data-ttu-id="afffa-107">Das <xref:System.Windows.Controls.GroupBox>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="afffa-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="afffa-108">GroupBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="afffa-108">GroupBox States</span></span>  
 <span data-ttu-id="afffa-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Controls.GroupBox>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="afffa-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="afffa-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="afffa-110">VisualState Name</span></span>|<span data-ttu-id="afffa-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="afffa-111">VisualStateGroup Name</span></span>|<span data-ttu-id="afffa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afffa-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="afffa-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="afffa-113">Valid</span></span>|<span data-ttu-id="afffa-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afffa-114">ValidationStates</span></span>|<span data-ttu-id="afffa-115">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="afffa-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="afffa-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="afffa-116">InvalidFocused</span></span>|<span data-ttu-id="afffa-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afffa-117">ValidationStates</span></span>|<span data-ttu-id="afffa-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="afffa-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="afffa-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="afffa-119">InvalidUnfocused</span></span>|<span data-ttu-id="afffa-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="afffa-120">ValidationStates</span></span>|<span data-ttu-id="afffa-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="afffa-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="afffa-122">GroupBox ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="afffa-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="afffa-123">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Controls.GroupBox>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="afffa-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="afffa-124">Der <xref:System.Windows.Controls.ControlTemplate> verwendet mindestens eine der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="afffa-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="afffa-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="afffa-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afffa-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afffa-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="afffa-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="afffa-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="afffa-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="afffa-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="afffa-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="afffa-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="afffa-130">Erstellen einer Vorlage für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="afffa-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
