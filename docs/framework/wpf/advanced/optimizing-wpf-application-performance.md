---
title: Optimieren der WPF-Anwendungsleistung
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 45618e6180cbe0206eb120fc71726d0b8de5f06d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511587"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="6d10f-102">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="6d10f-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="6d10f-103">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die Möglichkeiten zur Verbesserung der Leistung ihrer Anwendungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="6d10f-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="6d10f-104">Wenn Sie Entwickler sind, die in Microsoft .NET Framework neu ist und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie sollten zuerst sich vertraut machen mit beiden Plattformen.</span><span class="sxs-lookup"><span data-stu-id="6d10f-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="6d10f-105">In diesem Abschnitt wird davon ausgegangen sowohl Kenntnisse und ist für Programmierer, die schon genug, um ihre Anwendungen einsatzbereit geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d10f-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d10f-106">In diesem Abschnitt bereitgestellten Leistungsdaten basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen auf einem PC mit 2,8 GHz mit 512 RAM und ein ATI Radeon 9700 Grafikkarte.</span><span class="sxs-lookup"><span data-stu-id="6d10f-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d10f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6d10f-107">In This Section</span></span>  
 [<span data-ttu-id="6d10f-108">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="6d10f-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="6d10f-109">Vorteile der Hardware nutzen</span><span class="sxs-lookup"><span data-stu-id="6d10f-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="6d10f-110">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="6d10f-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="6d10f-111">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="6d10f-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="6d10f-112">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="6d10f-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="6d10f-113">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="6d10f-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="6d10f-114">Text</span><span class="sxs-lookup"><span data-stu-id="6d10f-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="6d10f-115">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6d10f-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="6d10f-116">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="6d10f-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="6d10f-117">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="6d10f-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="6d10f-118">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d10f-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="6d10f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d10f-119">See also</span></span>
- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="6d10f-120">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="6d10f-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)
- [<span data-ttu-id="6d10f-121">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="6d10f-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="6d10f-122">Layout</span><span class="sxs-lookup"><span data-stu-id="6d10f-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)
- [<span data-ttu-id="6d10f-123">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="6d10f-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
- [<span data-ttu-id="6d10f-124">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="6d10f-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="6d10f-125">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="6d10f-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="6d10f-126">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="6d10f-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="6d10f-127">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="6d10f-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="6d10f-128">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6d10f-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="6d10f-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="6d10f-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="6d10f-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="6d10f-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
- [<span data-ttu-id="6d10f-131">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="6d10f-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
- [<span data-ttu-id="6d10f-132">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6d10f-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6d10f-133">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="6d10f-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)
- [<span data-ttu-id="6d10f-134">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="6d10f-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="6d10f-135">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6d10f-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
