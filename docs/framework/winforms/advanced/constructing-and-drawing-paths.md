---
title: Erstellen und Zeichnen von Pfaden
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d1952632b29450a441d3cf0c7d66bffc000ea5
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="d8dc2-102">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="d8dc2-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="d8dc2-103">Ein Pfad ist eine Sequenz von Graphics primitive (Linien, Rechtecke, Kurven, Text und Like), die bearbeitet und als einzelne Einheit gezeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="d8dc2-104">Ein Pfad aufgeteilt werden kann *Abbildungen* , die entweder offen oder geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="d8dc2-105">Eine Abbildung kann mehrere primitive Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="d8dc2-106">Zeichnen eines Pfads können Sie durch Aufrufen der <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> -Klasse, und Sie können einen Pfad ausfüllen, durch Aufrufen der <xref:System.Drawing.Graphics.FillPath%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8dc2-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d8dc2-107">In This Section</span></span>  
 [<span data-ttu-id="d8dc2-108">Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="d8dc2-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="d8dc2-109">Zeigt, wie eine <xref:System.Drawing.Drawing2D.GraphicsPath> Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="d8dc2-110">Gewusst wie: Ausfüllen offener Körper</span><span class="sxs-lookup"><span data-stu-id="d8dc2-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="d8dc2-111">Erläutert, wie zum Auffüllen einer <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="d8dc2-112">Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie</span><span class="sxs-lookup"><span data-stu-id="d8dc2-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="d8dc2-113">Zeigt, wie vereinfachen ein <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d8dc2-114">Verweis</span><span class="sxs-lookup"><span data-stu-id="d8dc2-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="d8dc2-115">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="d8dc2-115">Describes this class and contains links to all of its members.</span></span>
