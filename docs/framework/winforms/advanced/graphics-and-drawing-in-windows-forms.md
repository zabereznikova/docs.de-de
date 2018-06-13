---
title: Grafik und Zeichnen in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 3dbb5d36ce2e550c0420a23b40247771e10d60ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521601"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="89c1d-102">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89c1d-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="89c1d-103">Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows-Grafikdesignoberfläche ([!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]), die so genannte [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89c1d-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="89c1d-104">Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="89c1d-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="89c1d-105"> vereint Leistung und Komfort.</span><span class="sxs-lookup"><span data-stu-id="89c1d-105"> is designed to offer performance and ease of use.</span></span> <span data-ttu-id="89c1d-106">Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] lassen sich grafische Bilder in Windows Forms und Steuerelementen rendern.</span><span class="sxs-lookup"><span data-stu-id="89c1d-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="89c1d-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann zwar in Web Forms nicht direkt verwendet werden, jedoch können Sie grafische Bilder mit dem Image-Webserversteuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="89c1d-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="89c1d-108">Dieser Abschnitt enthält Themen, die Sie in die Grundlagen der Programmierung mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] einführen.</span><span class="sxs-lookup"><span data-stu-id="89c1d-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="89c1d-109">Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="89c1d-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="89c1d-110">Weitere Informationen finden Sie unter [GDI + Verweis](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).</span><span class="sxs-lookup"><span data-stu-id="89c1d-110">For more information, see [GDI+ Reference](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).</span></span>  
  
 <span data-ttu-id="89c1d-111">Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md).</span><span class="sxs-lookup"><span data-stu-id="89c1d-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="89c1d-112">Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="89c1d-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89c1d-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="89c1d-113">In This Section</span></span>  
 [<span data-ttu-id="89c1d-114">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="89c1d-114">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 <span data-ttu-id="89c1d-115">Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="89c1d-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="89c1d-116">Verwalteter Code in GDI+</span><span class="sxs-lookup"><span data-stu-id="89c1d-116">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 <span data-ttu-id="89c1d-117">Enthält Informationen zu den verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89c1d-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="89c1d-118">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="89c1d-118">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 <span data-ttu-id="89c1d-119">Veranschaulicht die Ausführung verschiedener Aufgaben mithilfe der verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89c1d-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="89c1d-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="89c1d-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="89c1d-121">Ermöglicht den Zugriff auf die grundlegenden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="89c1d-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="89c1d-122">Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.</span><span class="sxs-lookup"><span data-stu-id="89c1d-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="89c1d-123">Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Bildfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="89c1d-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="89c1d-124">Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Typografiefunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="89c1d-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="89c1d-125">Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89c1d-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="89c1d-126">Stellt Druckfunktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="89c1d-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="89c1d-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="89c1d-127">Related Sections</span></span>  
 [<span data-ttu-id="89c1d-128">Zeichnen und Rendern von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="89c1d-128">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="89c1d-129">Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="89c1d-129">Details how to provide code for painting controls.</span></span>
