---
title: Grafiken und zeichnen
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746406"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="1aa23-102">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1aa23-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="1aa23-103">Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows Graphics Device Interface (GDI) mit dem Namen GDI+.</span><span class="sxs-lookup"><span data-stu-id="1aa23-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="1aa23-104">Mit GDI+ können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1aa23-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="1aa23-105">GDI+ wurde entwickelt, um Leistung und Benutzerfreundlichkeit zu bieten.</span><span class="sxs-lookup"><span data-stu-id="1aa23-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="1aa23-106">Mit GDI+ können Sie grafische Bilder auf Windows Forms-und-Steuerelementen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1aa23-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="1aa23-107">Obwohl Sie GDI+ nicht direkt auf Web Forms verwenden können, können Sie grafische Bilder mit dem Image-Webserver Steuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1aa23-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="1aa23-108">In diesem Abschnitt finden Sie Themen, in denen die Grundlagen der GDI+-Programmierung vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1aa23-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="1aa23-109">Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="1aa23-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="1aa23-110">Weitere Informationen finden Sie unter [GDI+-Referenz](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="1aa23-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="1aa23-111">Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="1aa23-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="1aa23-112">Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1aa23-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1aa23-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1aa23-113">In This Section</span></span>  
 [<span data-ttu-id="1aa23-114">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="1aa23-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="1aa23-115">Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="1aa23-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="1aa23-116">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="1aa23-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="1aa23-117">Stellt Informationen zu den verwalteten GDI+-Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="1aa23-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="1aa23-118">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="1aa23-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="1aa23-119">Veranschaulicht, wie eine Vielzahl von Tasks mithilfe der verwalteten GDI+-Klassen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa23-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1aa23-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="1aa23-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="1aa23-121">Bietet Zugriff auf die grundlegenden GDI+-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1aa23-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="1aa23-122">Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="1aa23-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="1aa23-123">Stellt erweiterte GDI+-Bildverarbeitungsfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1aa23-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="1aa23-124">Stellt erweiterte GDI+-Typografiefunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1aa23-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="1aa23-125">Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1aa23-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="1aa23-126">Stellt Druckfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="1aa23-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1aa23-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1aa23-127">Related Sections</span></span>  
 [<span data-ttu-id="1aa23-128">Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1aa23-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="1aa23-129">Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="1aa23-129">Details how to provide code for painting controls.</span></span>
