---
title: Optimieren der WPF-Anwendungsleistung
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 4724e6264c0108924629055525e46d84e86a6e6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953424"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="9e370-102">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="9e370-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="9e370-103">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die nach Möglichkeiten suchen, die Leistung Ihrer Anwendungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9e370-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="9e370-104">Wenn Sie ein Entwickler sind, der noch nicht mit dem Microsoft .NET Framework [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]und vertraut ist, sollten Sie sich zunächst mit beiden Plattformen vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="9e370-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="9e370-105">In diesem Abschnitt wird davon ausgegangen, dass Sie über Kenntnisse beider Personen verfügen, und Sie wird für Programmierer geschrieben, die bereits genug wissen, um Ihre Anwendungen zu starten.</span><span class="sxs-lookup"><span data-stu-id="9e370-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e370-106">Die in diesem Abschnitt bereitgestellten Leistungsdaten basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die auf einem 2,8 GHz-PC mit 512 RAM und einer ATI Radeon 9700-Grafikkarte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9e370-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e370-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e370-107">In This Section</span></span>  
 [<span data-ttu-id="9e370-108">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="9e370-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="9e370-109">Vorteile der Hardware nutzen</span><span class="sxs-lookup"><span data-stu-id="9e370-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="9e370-110">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="9e370-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="9e370-111">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="9e370-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="9e370-112">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="9e370-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="9e370-113">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="9e370-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="9e370-114">Text</span><span class="sxs-lookup"><span data-stu-id="9e370-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="9e370-115">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9e370-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="9e370-116">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e370-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="9e370-117">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="9e370-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="9e370-118">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e370-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e370-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e370-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="9e370-120">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="9e370-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="9e370-121">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="9e370-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="9e370-122">Layout</span><span class="sxs-lookup"><span data-stu-id="9e370-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="9e370-123">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="9e370-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="9e370-124">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="9e370-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="9e370-125">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="9e370-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="9e370-126">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e370-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="9e370-127">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="9e370-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="9e370-128">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9e370-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="9e370-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="9e370-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="9e370-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="9e370-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="9e370-131">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="9e370-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="9e370-132">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9e370-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="9e370-133">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="9e370-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="9e370-134">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="9e370-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="9e370-135">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e370-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
