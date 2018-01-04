---
title: Drei Kategorien von Grafikdiensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 305ffae04b6f1ddb94081f8a6ee334f8195caba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="95488-102">Drei Kategorien von Grafikdiensten</span><span class="sxs-lookup"><span data-stu-id="95488-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="95488-103">Die Angebote Grafiken in Windows Forms werden in den folgenden drei allgemeine Kategorien fallen:</span><span class="sxs-lookup"><span data-stu-id="95488-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
-   <span data-ttu-id="95488-104">Zweidimensionale (2D) Vektorgrafik</span><span class="sxs-lookup"><span data-stu-id="95488-104">Two-dimensional (2-D) vector graphics</span></span>  
  
-   <span data-ttu-id="95488-105">Aufspielen eines Abbilds</span><span class="sxs-lookup"><span data-stu-id="95488-105">Imaging</span></span>  
  
-   <span data-ttu-id="95488-106">Typografie</span><span class="sxs-lookup"><span data-stu-id="95488-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="95488-107">2D-Vektorgrafiken</span><span class="sxs-lookup"><span data-stu-id="95488-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="95488-108">Zweidimensionale Vektorgrafik handelt es sich um primitive Typen; z. B. Linien, Kurven und Formen; werden durch Gruppen von Punkten auf einem Koordinatensystem angegeben.</span><span class="sxs-lookup"><span data-stu-id="95488-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="95488-109">Z. B. eine gerade Linie durch zwei Endpunkte angegeben wird, und ein Rechteck wird durch einen Punkt, erteilen den Speicherort der oberen linken Ecke und ein Paar von Zahlen, wobei die Breite und Höhe angegeben.</span><span class="sxs-lookup"><span data-stu-id="95488-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="95488-110">Durch ein Array von Punkten, die durch gerade Linien verbunden sind, wird ein einfacher Pfad angegeben.</span><span class="sxs-lookup"><span data-stu-id="95488-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="95488-111">Ein Bézier-Spline ist eine anspruchsvolle Kurve, die durch vier Steuerpunkte angegeben.</span><span class="sxs-lookup"><span data-stu-id="95488-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="95488-112">enthält Klassen und Strukturen, die Informationen über die Grundelemente speichern, Klassen, in denen Informationen wie die primitiven gezeichnet werden gespeichert und Klassen, die den Zeichenvorgang ausführen.</span><span class="sxs-lookup"><span data-stu-id="95488-112"> provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="95488-113">Z. B. die <xref:System.Drawing.Rectangle> -Struktur speichert die Position und Größe eines Rechtecks; die <xref:System.Drawing.Pen> Klasse speichert Informationen über die Linienfarbe und Linienstärke Linienart aus, und die <xref:System.Drawing.Graphics> -Klasse verfügt über Methoden zum Zeichnen von Linien, Rechtecke, Pfaden, und andere Zahlen.</span><span class="sxs-lookup"><span data-stu-id="95488-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="95488-114">Es gibt auch mehrere <xref:System.Drawing.Brush> Klassen, die Informationen speichern geschlossene Formen und Pfade mit Farben oder Mustern ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="95488-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="95488-115">Ein Vektor-Image eine Sequenz von Graphics-Befehlen ist, können Sie in einer Metadatei aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="95488-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="95488-116">Stellt die <xref:System.Drawing.Imaging.Metafile> Klasse zum Aufzeichnen, anzeigen und Speichern von Metadateien.</span><span class="sxs-lookup"><span data-stu-id="95488-116"> provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="95488-117">Mit der <xref:System.Drawing.Imaging.MetafileHeader> und <xref:System.Drawing.Imaging.MetaHeader> Klassen, überprüfen Sie die Daten in einem Metadateiheader gespeichert.</span><span class="sxs-lookup"><span data-stu-id="95488-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="95488-118">Aufspielen eines Abbilds</span><span class="sxs-lookup"><span data-stu-id="95488-118">Imaging</span></span>  
 <span data-ttu-id="95488-119">Bestimmte Arten von Bildern sind schwer oder gar nicht mit den Techniken von Vektorgrafiken anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="95488-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="95488-120">Beispielsweise sind die Bilder auf Symbolleisten-Schaltflächen und Bilder, die als Symbole angezeigt werden nur schwer als Auflistungen von Linien und Kurven.</span><span class="sxs-lookup"><span data-stu-id="95488-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="95488-121">Ein hochauflösende digitale Foto des voll besetzten Fußballstadions ist auch schwieriger zu mit Vektor Techniken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="95488-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="95488-122">Bilder dieses Typs werden als Bitmaps, gespeichert, die Arrays von Zahlen sind, die die Farben der einzelnen Punkte auf dem Bildschirm darstellen.</span><span class="sxs-lookup"><span data-stu-id="95488-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="95488-123">Stellt die <xref:System.Drawing.Bitmap> Klasse zum Anzeigen, bearbeiten und Speichern von Bitmaps.</span><span class="sxs-lookup"><span data-stu-id="95488-123"> provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="95488-124">Typografie</span><span class="sxs-lookup"><span data-stu-id="95488-124">Typography</span></span>  
 <span data-ttu-id="95488-125">Typografie ist die Anzeige von Text in einer Vielzahl von Schriftarten, Größen und Formate.</span><span class="sxs-lookup"><span data-stu-id="95488-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="95488-126">bietet umfassende Unterstützung für diese komplexe Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="95488-126"> provides extensive support for this complex task.</span></span> <span data-ttu-id="95488-127">Eine der neuen Funktionen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] wird Subpixel Antialiasing (Antialiasing), die Text enthält gerendert auf einem Bildschirm LCD eine glattere Darstellung.</span><span class="sxs-lookup"><span data-stu-id="95488-127">One of the new features in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="95488-128">Windows Forms bietet außerdem die Option zum Zeichnen von Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Funktionen in seiner <xref:System.Windows.Forms.TextRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="95488-128">In addition, Windows Forms offers the option to draw text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95488-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95488-129">See Also</span></span>  
 [<span data-ttu-id="95488-130">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="95488-130">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [<span data-ttu-id="95488-131">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="95488-131">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [<span data-ttu-id="95488-132">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="95488-132">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
