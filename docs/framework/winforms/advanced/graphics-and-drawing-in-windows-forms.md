---
title: Grafiken und zeichnen
description: Erfahren Sie mehr über Grafik-, Stift-, Pinsel-und Farb Objekte sowie über das Ausführen von Aufgaben wie das Zeichnen von Formen, das Zeichnen von Text oder das Anzeigen von Bildern in Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 58d8cde6aa102225cf9e3c342efe37218c818307
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618401"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="cf893-103">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cf893-103">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="cf893-104">Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows Graphics Device Interface (GDI) mit dem Namen GDI+.</span><span class="sxs-lookup"><span data-stu-id="cf893-104">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="cf893-105">Mit GDI+ können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cf893-105">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="cf893-106">GDI+ wurde entwickelt, um Leistung und Benutzerfreundlichkeit zu bieten.</span><span class="sxs-lookup"><span data-stu-id="cf893-106">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="cf893-107">Mit GDI+ können Sie grafische Bilder auf Windows Forms-und-Steuerelementen darstellen.</span><span class="sxs-lookup"><span data-stu-id="cf893-107">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="cf893-108">Obwohl Sie GDI+ nicht direkt auf Web Forms verwenden können, können Sie grafische Bilder mit dem Image-Webserver Steuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cf893-108">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="cf893-109">In diesem Abschnitt finden Sie Themen, in denen die Grundlagen der GDI+-Programmierung vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cf893-109">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="cf893-110">Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="cf893-110">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="cf893-111">Weitere Informationen finden Sie unter [GDI+-Referenz](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="cf893-111">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="cf893-112">Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="cf893-112">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="cf893-113">Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cf893-113">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf893-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cf893-114">In This Section</span></span>  
 [<span data-ttu-id="cf893-115">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="cf893-115">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="cf893-116">Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="cf893-116">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="cf893-117">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="cf893-117">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="cf893-118">Stellt Informationen zu den verwalteten GDI+-Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf893-118">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="cf893-119">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="cf893-119">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="cf893-120">Veranschaulicht, wie eine Vielzahl von Tasks mithilfe der verwalteten GDI+-Klassen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cf893-120">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf893-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="cf893-121">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="cf893-122">Bietet Zugriff auf die grundlegenden GDI+-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cf893-122">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="cf893-123">Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="cf893-123">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="cf893-124">Stellt erweiterte GDI+-Bildverarbeitungsfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf893-124">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="cf893-125">Stellt erweiterte GDI+-Typografiefunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf893-125">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="cf893-126">Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf893-126">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="cf893-127">Stellt Druckfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf893-127">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf893-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cf893-128">Related Sections</span></span>  
 [<span data-ttu-id="cf893-129">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="cf893-129">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="cf893-130">Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="cf893-130">Details how to provide code for painting controls.</span></span>
