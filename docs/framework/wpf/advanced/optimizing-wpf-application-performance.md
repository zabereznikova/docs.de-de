---
title: Optimieren der WPF-Anwendungsleistung
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 53291a0e428b723cd7a6e7b1184639a7b3c3b972
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141556"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="85eca-102">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="85eca-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="85eca-103">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die Möglichkeiten zur Verbesserung der Leistung ihrer Anwendungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="85eca-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="85eca-104">Wenn Sie Entwickler sind, die in Microsoft .NET Framework neu ist und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie sollten zuerst sich vertraut machen mit beiden Plattformen.</span><span class="sxs-lookup"><span data-stu-id="85eca-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="85eca-105">In diesem Abschnitt wird davon ausgegangen sowohl Kenntnisse und ist für Programmierer, die schon genug, um ihre Anwendungen einsatzbereit geschrieben.</span><span class="sxs-lookup"><span data-stu-id="85eca-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85eca-106">In diesem Abschnitt bereitgestellten Leistungsdaten basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen auf einem PC mit 2,8 GHz mit 512 RAM und ein ATI Radeon 9700 Grafikkarte.</span><span class="sxs-lookup"><span data-stu-id="85eca-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85eca-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="85eca-107">In This Section</span></span>  
 [<span data-ttu-id="85eca-108">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="85eca-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="85eca-109">Vorteile der Hardware nutzen</span><span class="sxs-lookup"><span data-stu-id="85eca-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="85eca-110">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="85eca-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="85eca-111">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="85eca-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="85eca-112">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="85eca-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="85eca-113">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="85eca-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="85eca-114">Text</span><span class="sxs-lookup"><span data-stu-id="85eca-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="85eca-115">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85eca-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="85eca-116">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="85eca-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="85eca-117">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="85eca-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="85eca-118">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="85eca-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="85eca-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85eca-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="85eca-120">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="85eca-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="85eca-121">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="85eca-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="85eca-122">Layout</span><span class="sxs-lookup"><span data-stu-id="85eca-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="85eca-123">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="85eca-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="85eca-124">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="85eca-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="85eca-125">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="85eca-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="85eca-126">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="85eca-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="85eca-127">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="85eca-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="85eca-128">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="85eca-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="85eca-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="85eca-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="85eca-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="85eca-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="85eca-131">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="85eca-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="85eca-132">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="85eca-132">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="85eca-133">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="85eca-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="85eca-134">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="85eca-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="85eca-135">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="85eca-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
