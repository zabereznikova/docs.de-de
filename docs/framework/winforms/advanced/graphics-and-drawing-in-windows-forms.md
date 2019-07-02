---
title: Grafik und Zeichnen in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505539"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="6c001-102">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c001-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="6c001-103">Die common Language Runtime verwendet eine erweiterte Implementierung von der Windows Graphics Device Interface (GDI) wird aufgerufen, GDI +.</span><span class="sxs-lookup"><span data-stu-id="6c001-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="6c001-104">Mit GDI + können Sie Grafiken erstellen, Zeichnen von Text und Bearbeiten von Bildern als Objekte.</span><span class="sxs-lookup"><span data-stu-id="6c001-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="6c001-105">GDI + soll Leistung und benutzerfreundlichkeit bieten.</span><span class="sxs-lookup"><span data-stu-id="6c001-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="6c001-106">GDI + können zum Rendern von Grafiken in Windows Forms und Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="6c001-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="6c001-107">Obwohl Sie GDI + in Web Forms nicht direkt verwendet, können Sie grafische Bilder mit der Image-Webserversteuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c001-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="6c001-108">In diesem Abschnitt finden Sie Themen, in denen die Grundlagen der Programmierung von GDI + eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6c001-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="6c001-109">Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="6c001-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="6c001-110">Weitere Informationen finden Sie unter [GDI + Verweis](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="6c001-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="6c001-111">Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="6c001-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="6c001-112">Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6c001-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c001-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c001-113">In This Section</span></span>  
 [<span data-ttu-id="6c001-114">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="6c001-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="6c001-115">Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="6c001-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="6c001-116">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="6c001-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="6c001-117">Enthält Informationen zu den verwalteten GDI +-Klassen.</span><span class="sxs-lookup"><span data-stu-id="6c001-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="6c001-118">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="6c001-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="6c001-119">Veranschaulicht, wie zum Abschluss eine Vielzahl von Aufgaben, die mithilfe von GDI + Klassen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6c001-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6c001-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="6c001-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="6c001-121">Bietet Zugriff auf die grundlegende GDI +-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="6c001-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="6c001-122">Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="6c001-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="6c001-123">Stellt erweiterte GDI +-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="6c001-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="6c001-124">Stellt erweiterte GDI +-Typografiefunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="6c001-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="6c001-125">Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c001-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="6c001-126">Stellt Druckfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="6c001-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6c001-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6c001-127">Related Sections</span></span>  
 [<span data-ttu-id="6c001-128">Zeichnen und Rendern von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6c001-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="6c001-129">Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="6c001-129">Details how to provide code for painting controls.</span></span>
