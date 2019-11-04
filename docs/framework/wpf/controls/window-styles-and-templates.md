---
title: Window-Stile und -Vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 48fe5887ebad86efad1b1aae39ba03a26fda3bd8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460018"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="8eb01-102">Window-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8eb01-102">Window Styles and Templates</span></span>
<span data-ttu-id="8eb01-103">In diesem Thema werden die Stile und Vorlagen für das <xref:System.Windows.Window>-Steuerelement beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8eb01-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="8eb01-104">Sie können die Standard <xref:System.Windows.Controls.ControlTemplate> ändern, um dem Steuerelement eine eindeutige Darstellung zu verschaffen.</span><span class="sxs-lookup"><span data-stu-id="8eb01-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8eb01-105">Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8eb01-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="8eb01-106">Fensterteile</span><span class="sxs-lookup"><span data-stu-id="8eb01-106">Window Parts</span></span>  
 <span data-ttu-id="8eb01-107">Das <xref:System.Windows.Window>-Steuerelement verfügt über keine benannten Teile.</span><span class="sxs-lookup"><span data-stu-id="8eb01-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="8eb01-108">Fenster Zustände</span><span class="sxs-lookup"><span data-stu-id="8eb01-108">Window States</span></span>  
 <span data-ttu-id="8eb01-109">In der folgenden Tabelle werden die visuellen Zustände für das <xref:System.Windows.Window>-Steuerelement aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="8eb01-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="8eb01-110">VisualState-Name</span><span class="sxs-lookup"><span data-stu-id="8eb01-110">VisualState Name</span></span>|<span data-ttu-id="8eb01-111">VisualStateGroup-Name</span><span class="sxs-lookup"><span data-stu-id="8eb01-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8eb01-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8eb01-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8eb01-113">Gültig</span><span class="sxs-lookup"><span data-stu-id="8eb01-113">Valid</span></span>|<span data-ttu-id="8eb01-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8eb01-114">ValidationStates</span></span>|<span data-ttu-id="8eb01-115">Das-Steuerelement verwendet die <xref:System.Windows.Controls.Validation>-Klasse, und die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte-Eigenschaft ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8eb01-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8eb01-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8eb01-116">InvalidFocused</span></span>|<span data-ttu-id="8eb01-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8eb01-117">ValidationStates</span></span>|<span data-ttu-id="8eb01-118">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true` hat, dass das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="8eb01-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8eb01-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8eb01-119">InvalidUnfocused</span></span>|<span data-ttu-id="8eb01-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8eb01-120">ValidationStates</span></span>|<span data-ttu-id="8eb01-121">Die <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> angefügte Eigenschaft ist `true`, wenn das Steuerelement keinen Fokus hat.</span><span class="sxs-lookup"><span data-stu-id="8eb01-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="8eb01-122">Fenster ControlTemplate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="8eb01-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="8eb01-123">Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.ControlTemplate> für das <xref:System.Windows.Window>-Steuerelement definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8eb01-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="8eb01-124">Der <xref:System.Windows.Controls.ControlTemplate> verwendet mindestens eine der folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="8eb01-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8eb01-125">Das vollständige Beispiel finden Sie unter [Beispiel zum Formatieren mit ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8eb01-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb01-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8eb01-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8eb01-127">Steuerelementformate und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="8eb01-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8eb01-128">Anpassung von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="8eb01-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8eb01-129">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8eb01-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8eb01-130">Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8eb01-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
