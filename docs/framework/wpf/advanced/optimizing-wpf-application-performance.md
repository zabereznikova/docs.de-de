---
title: Optimieren der APP-Leistung
description: Nutzen Sie diese Ressourcen, um die Leistung von Windows Presentation Foundation Anwendungen zu verbessern, z. b. die Leistungsplanung und die Nutzung von Hardware.
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 165caaf102a66988db0254839a947b8e262a386d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166332"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="70d8b-103">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="70d8b-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="70d8b-104">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die nach Möglichkeiten suchen, die Leistung Ihrer Anwendungen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="70d8b-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="70d8b-105">Wenn Sie ein Entwickler sind, der noch nicht mit dem Microsoft .NET Framework und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vertraut ist, sollten Sie sich zunächst mit beiden Plattformen vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="70d8b-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="70d8b-106">In diesem Abschnitt wird davon ausgegangen, dass Sie über Kenntnisse beider Personen verfügen, und Sie wird für Programmierer geschrieben, die bereits genug wissen, um Ihre Anwendungen zu starten.</span><span class="sxs-lookup"><span data-stu-id="70d8b-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70d8b-107">Die in diesem Abschnitt bereitgestellten Leistungsdaten basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die auf einem 2,8 GHz-PC mit 512 RAM und einer ATI Radeon 9700-Grafikkarte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="70d8b-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70d8b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="70d8b-108">In This Section</span></span>  
 [<span data-ttu-id="70d8b-109">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="70d8b-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="70d8b-110">Nutzen der Vorteile der Hardware</span><span class="sxs-lookup"><span data-stu-id="70d8b-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="70d8b-111">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="70d8b-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="70d8b-112">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="70d8b-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="70d8b-113">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="70d8b-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="70d8b-114">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="70d8b-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="70d8b-115">Text</span><span class="sxs-lookup"><span data-stu-id="70d8b-115">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="70d8b-116">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="70d8b-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="70d8b-117">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="70d8b-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="70d8b-118">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="70d8b-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="70d8b-119">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="70d8b-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="70d8b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70d8b-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="70d8b-121">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="70d8b-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="70d8b-122">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="70d8b-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="70d8b-123">Layout</span><span class="sxs-lookup"><span data-stu-id="70d8b-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="70d8b-124">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="70d8b-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="70d8b-125">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="70d8b-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="70d8b-126">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="70d8b-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="70d8b-127">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="70d8b-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="70d8b-128">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="70d8b-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="70d8b-129">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="70d8b-129">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="70d8b-130">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="70d8b-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="70d8b-131">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="70d8b-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="70d8b-132">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="70d8b-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="70d8b-133">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="70d8b-133">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="70d8b-134">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="70d8b-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="70d8b-135">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="70d8b-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="70d8b-136">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="70d8b-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
