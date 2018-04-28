---
title: Optimieren der WPF-Anwendungsleistung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
caps.latest.revision: 45
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2de2d4009cb29c5e9cbdace0d69c220f95a54e1
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="9e7a9-102">Optimieren der WPF-Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="9e7a9-103">Dieser Abschnitt dient als Referenz für [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungsentwickler, die nach Möglichkeiten zum Verbessern der Leistung ihrer Anwendungen suchen.</span><span class="sxs-lookup"><span data-stu-id="9e7a9-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="9e7a9-104">Wenn Sie Entwickler sind, die noch nicht mit Microsoft .NET Framework ist und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Sie sollten zuerst Kennenlernen der beiden Plattformen.</span><span class="sxs-lookup"><span data-stu-id="9e7a9-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="9e7a9-105">In diesem Abschnitt setzt beide praktische Kenntnisse und für Programmierer, die sich bereits ausreichend, um ihre Anwendungen einsatzbereit wissen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9e7a9-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e7a9-106">In diesem Abschnitt bereitgestellten Leistungsdaten sind basieren auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen auf einer mit 2,8 GHz PC mit 512 RAM und einem ATI Radeon 9700 Grafikkarte.</span><span class="sxs-lookup"><span data-stu-id="9e7a9-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e7a9-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e7a9-107">In This Section</span></span>  
 [<span data-ttu-id="9e7a9-108">Planen der Anwendungsleistung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="9e7a9-109">Vorteile der Hardware nutzen</span><span class="sxs-lookup"><span data-stu-id="9e7a9-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="9e7a9-110">Layout und Entwurf</span><span class="sxs-lookup"><span data-stu-id="9e7a9-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="9e7a9-111">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="9e7a9-112">Objektverhalten</span><span class="sxs-lookup"><span data-stu-id="9e7a9-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="9e7a9-113">Anwendungsressourcen</span><span class="sxs-lookup"><span data-stu-id="9e7a9-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="9e7a9-114">Text</span><span class="sxs-lookup"><span data-stu-id="9e7a9-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="9e7a9-115">Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="9e7a9-116">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="9e7a9-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="9e7a9-117">Weitere Leistungsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="9e7a9-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="9e7a9-118">Startzeit der Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e7a9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e7a9-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="9e7a9-120">Renderingebenen für Grafiken</span><span class="sxs-lookup"><span data-stu-id="9e7a9-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="9e7a9-121">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="9e7a9-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="9e7a9-122">Layout</span><span class="sxs-lookup"><span data-stu-id="9e7a9-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="9e7a9-123">Strukturen in WPF</span><span class="sxs-lookup"><span data-stu-id="9e7a9-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="9e7a9-124">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="9e7a9-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="9e7a9-125">Verwenden von DrawingVisual-Objekten</span><span class="sxs-lookup"><span data-stu-id="9e7a9-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="9e7a9-126">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e7a9-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="9e7a9-127">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="9e7a9-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="9e7a9-128">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9e7a9-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="9e7a9-129">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="9e7a9-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="9e7a9-130">Zeichnen von formatiertem Text</span><span class="sxs-lookup"><span data-stu-id="9e7a9-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="9e7a9-131">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="9e7a9-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="9e7a9-132">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="9e7a9-133">Übersicht über die Navigation</span><span class="sxs-lookup"><span data-stu-id="9e7a9-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="9e7a9-134">Tipps und Tricks zu Animationen</span><span class="sxs-lookup"><span data-stu-id="9e7a9-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="9e7a9-135">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e7a9-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
