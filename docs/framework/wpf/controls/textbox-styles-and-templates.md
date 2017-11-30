---
title: TextBox-Stile und -Vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f5cfd1c0715c7f9610f85201cd40a3973a2be64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="2e123-102">TextBox-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e123-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="2e123-103">In diesem Thema wird beschrieben, die Stile und Vorlagen für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="2e123-104">Sie können den Standardwert ändern <xref:System.Windows.Controls.ControlTemplate> auf dem Steuerelement ein einzigartiges aussehen zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="2e123-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2e123-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="2e123-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="2e123-106">TextBox-Teile</span><span class="sxs-lookup"><span data-stu-id="2e123-106">TextBox Parts</span></span>  
 <span data-ttu-id="2e123-107">Die folgende Tabelle enthält die benannten Teile für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="2e123-108">Segment</span><span class="sxs-lookup"><span data-stu-id="2e123-108">Part</span></span>|<span data-ttu-id="2e123-109">Typ</span><span class="sxs-lookup"><span data-stu-id="2e123-109">Type</span></span>|<span data-ttu-id="2e123-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e123-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2e123-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="2e123-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="2e123-112">Ein visuelles Element, das enthalten kann eine <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="2e123-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="2e123-113">Der Text, der die <xref:System.Windows.Controls.TextBox> wird in diesem Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e123-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="2e123-114">TextBox-Zustände</span><span class="sxs-lookup"><span data-stu-id="2e123-114">TextBox States</span></span>  
 <span data-ttu-id="2e123-115">Die folgende Tabelle enthält die visueller Zustände für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="2e123-116">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="2e123-116">VisualState Name</span></span>|<span data-ttu-id="2e123-117">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="2e123-117">VisualStateGroup Name</span></span>|<span data-ttu-id="2e123-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e123-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="2e123-119">Normal</span><span class="sxs-lookup"><span data-stu-id="2e123-119">Normal</span></span>|<span data-ttu-id="2e123-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e123-120">CommonStates</span></span>|<span data-ttu-id="2e123-121">Der Standardzustand</span><span class="sxs-lookup"><span data-stu-id="2e123-121">The default state.</span></span>|  
|<span data-ttu-id="2e123-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="2e123-122">MouseOver</span></span>|<span data-ttu-id="2e123-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e123-123">CommonStates</span></span>|<span data-ttu-id="2e123-124">Der Mauszeiger befindet sich auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="2e123-125">Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="2e123-125">Disabled</span></span>|<span data-ttu-id="2e123-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e123-126">CommonStates</span></span>|<span data-ttu-id="2e123-127">Das Steuerelement ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e123-127">The control is disabled.</span></span>|  
|<span data-ttu-id="2e123-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="2e123-128">ReadOnly</span></span>|<span data-ttu-id="2e123-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="2e123-129">CommonStates</span></span>|<span data-ttu-id="2e123-130">Der Benutzer kann nicht geändert werden den Text in der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2e123-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="2e123-131">Mit Fokus</span><span class="sxs-lookup"><span data-stu-id="2e123-131">Focused</span></span>|<span data-ttu-id="2e123-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2e123-132">FocusStates</span></span>|<span data-ttu-id="2e123-133">Der Fokus liegt auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-133">The control has focus.</span></span>|  
|<span data-ttu-id="2e123-134">Ohne Fokus</span><span class="sxs-lookup"><span data-stu-id="2e123-134">Unfocused</span></span>|<span data-ttu-id="2e123-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="2e123-135">FocusStates</span></span>|<span data-ttu-id="2e123-136">Der Fokus liegt nicht auf dem Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="2e123-137">Gültig</span><span class="sxs-lookup"><span data-stu-id="2e123-137">Valid</span></span>|<span data-ttu-id="2e123-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e123-138">ValidationStates</span></span>|<span data-ttu-id="2e123-139">Das Steuerelement verwendet die <xref:System.Windows.Controls.Validation> Klasse und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="2e123-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2e123-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2e123-140">InvalidFocused</span></span>|<span data-ttu-id="2e123-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e123-141">ValidationStates</span></span>|<span data-ttu-id="2e123-142">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` weist das Steuerelement den Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="2e123-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2e123-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2e123-143">InvalidUnfocused</span></span>|<span data-ttu-id="2e123-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2e123-144">ValidationStates</span></span>|<span data-ttu-id="2e123-145">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft `true` hat das Steuerelement verfügt nicht über den Fokus.</span><span class="sxs-lookup"><span data-stu-id="2e123-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="2e123-146">Beispiel für Textfeld ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2e123-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="2e123-147">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.ControlTemplate> für die <xref:System.Windows.Controls.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e123-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="2e123-148">Im vorhergehenden Beispiel wird mindestens eine der folgenden Ressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e123-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2e123-149">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="2e123-149">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e123-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e123-150">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="2e123-151">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e123-151">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="2e123-152">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2e123-152">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="2e123-153">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2e123-153">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="2e123-154">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="2e123-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
