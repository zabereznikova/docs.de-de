---
title: "Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ece907b23772504990ef334f446d7b6072f5d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="986c2-102">Exemplarische Vorgehensweisen: Erstellen einer benutzerdefinierten animierten Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="986c2-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="986c2-103">Wie der Name andeutet, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] eignet sich hervorragend für umfangreiche Erfahrungen Kunden zu stellen.</span><span class="sxs-lookup"><span data-stu-id="986c2-103">As its name suggests, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="986c2-104">In diesen exemplarischen Vorgehensweisen zeigen, wie das Aussehen und Verhalten einer Schaltfläche (einschließlich Animationen) anpassen.</span><span class="sxs-lookup"><span data-stu-id="986c2-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="986c2-105">Diese Anpassung erfolgt über einen Stil und eine Vorlage, damit Sie diese benutzerdefinierte Schaltfläche leicht auf alle Schaltflächen in der Anwendung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="986c2-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="986c2-106">Die folgende Abbildung zeigt der benutzerdefinierten Schaltfläche, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="986c2-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="986c2-107">![Die benutzerdefinierte Schaltfläche, die Sie erstellen](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "Custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="986c2-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="986c2-108">Die Vektorgrafiken für die Darstellung der Schaltfläche Erstellung erfolgt mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="986c2-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="986c2-109">ähnelt HTML leistungsfähiger und erweiterbar ist.</span><span class="sxs-lookup"><span data-stu-id="986c2-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="986c2-110">über Microsoft Visual Studio oder Editor manuell eingegeben werden können, oder können Sie visuelle Design-Tool wie Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="986c2-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="986c2-111">Expression Blend funktioniert durch das Erstellen der zugrunde liegenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, sodass beide Methoden die gleichen Grafiken erstellen.</span><span class="sxs-lookup"><span data-stu-id="986c2-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="986c2-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="986c2-112">In This Section</span></span>  
 [<span data-ttu-id="986c2-113">Erstellen einer Schaltfläche mit Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="986c2-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="986c2-114">Veranschaulicht, wie Schaltflächen mit benutzerdefiniertem Verhalten mithilfe der Designer-Funktionen von Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="986c2-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="986c2-115">Erstellen einer Schaltfläche mit XAML</span><span class="sxs-lookup"><span data-stu-id="986c2-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="986c2-116">Veranschaulicht das Erstellen von Schaltflächen mit benutzerdefiniertem Verhalten mithilfe [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="986c2-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="986c2-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="986c2-117">Related Sections</span></span>  
 [<span data-ttu-id="986c2-118">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="986c2-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="986c2-119">Beschreibt, wie Stile und Vorlagen verwendet werden können, um das Aussehen und Verhalten von Steuerelementen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="986c2-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="986c2-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="986c2-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="986c2-121">Beschreibt, wie Objekte mit animiert werden können die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Animations- und Zeitsteuerungssystems.</span><span class="sxs-lookup"><span data-stu-id="986c2-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="986c2-122">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="986c2-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="986c2-123">Beschreibt das Pinselobjekte verwenden, um mit Volltonfarben, linearer Farbverläufe und radialen Farbverläufen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="986c2-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="986c2-124">Übersicht über Bitmapeffekte</span><span class="sxs-lookup"><span data-stu-id="986c2-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="986c2-125">Beschreibt die Bitmapeffekte von unterstützten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und erläutert, wie sie angewendet.</span><span class="sxs-lookup"><span data-stu-id="986c2-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
