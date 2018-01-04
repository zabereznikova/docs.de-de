---
title: GroupBox-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99150de10fcbd45d3617621a916793ad5cfe72db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="a2caf-102">GroupBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2caf-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="a2caf-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2caf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="a2caf-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="a2caf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a2caf-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a2caf-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="a2caf-106">GroupBox-Teile</span><span class="sxs-lookup"><span data-stu-id="a2caf-106">GroupBox Parts</span></span>  
 <span data-ttu-id="a2caf-107">Die <xref:System.Windows.Controls.GroupBox> Steuerelement enthält keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="a2caf-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="a2caf-108">GroupBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="a2caf-108">GroupBox States</span></span>  
 <span data-ttu-id="a2caf-109">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2caf-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="a2caf-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="a2caf-110">VisualState Name</span></span>|<span data-ttu-id="a2caf-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="a2caf-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a2caf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2caf-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a2caf-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="a2caf-113">Valid</span></span>|<span data-ttu-id="a2caf-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2caf-114">ValidationStates</span></span>|<span data-ttu-id="a2caf-115">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="a2caf-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a2caf-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a2caf-116">InvalidFocused</span></span>|<span data-ttu-id="a2caf-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2caf-117">ValidationStates</span></span>|<span data-ttu-id="a2caf-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="a2caf-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a2caf-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a2caf-119">InvalidUnfocused</span></span>|<span data-ttu-id="a2caf-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2caf-120">ValidationStates</span></span>|<span data-ttu-id="a2caf-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="a2caf-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="a2caf-122">Beispiel für GroupBox-ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a2caf-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="a2caf-123">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a2caf-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="a2caf-124">Die <xref:System.Windows.Controls.ControlTemplate> verwendet wird, eine oder mehrere der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a2caf-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a2caf-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a2caf-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2caf-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2caf-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a2caf-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2caf-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a2caf-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a2caf-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a2caf-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a2caf-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a2caf-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a2caf-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
