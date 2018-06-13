---
title: Optimieren der WPF-Anwendungsleistung
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: faa06e4558401c1d0e9335fbc630c5371d1bc516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546327"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="60add-102">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="60add-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="60add-103">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die nach Möglichkeiten zum Verbessern der Leistung ihrer Anwendungen suchen.</span><span class="sxs-lookup"><span data-stu-id="60add-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="60add-104">Wenn Sie Entwickler sind, die noch nicht mit Microsoft .NET Framework ist und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie sollten zuerst Kennenlernen der beiden Plattformen.</span><span class="sxs-lookup"><span data-stu-id="60add-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="60add-105">In diesem Abschnitt setzt beide praktische Kenntnisse und für Programmierer, die sich bereits ausreichend, um ihre Anwendungen einsatzbereit wissen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="60add-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60add-106">In diesem Abschnitt bereitgestellten Leistungsdaten sind basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen auf einer mit 2,8 GHz PC mit 512 RAM und einem ATI Radeon 9700 Grafikkarte.</span><span class="sxs-lookup"><span data-stu-id="60add-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60add-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="60add-107">In This Section</span></span>  
 [<span data-ttu-id="60add-108">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="60add-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="60add-109">Vorteile der Hardware nutzen</span><span class="sxs-lookup"><span data-stu-id="60add-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="60add-110">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="60add-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="60add-111">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="60add-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="60add-112">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="60add-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="60add-113">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="60add-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="60add-114">Text</span><span class="sxs-lookup"><span data-stu-id="60add-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="60add-115">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="60add-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="60add-116">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="60add-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="60add-117">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="60add-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="60add-118">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="60add-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="60add-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60add-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="60add-120">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="60add-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="60add-121">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="60add-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="60add-122">Layout</span><span class="sxs-lookup"><span data-stu-id="60add-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="60add-123">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="60add-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="60add-124">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="60add-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="60add-125">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="60add-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="60add-126">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="60add-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="60add-127">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="60add-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="60add-128">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="60add-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="60add-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="60add-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="60add-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="60add-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="60add-131">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="60add-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="60add-132">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="60add-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="60add-133">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="60add-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="60add-134">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="60add-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="60add-135">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="60add-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
