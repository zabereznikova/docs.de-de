---
title: Erstellen und Zeichnen von Pfaden
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: a698b93aac29a0a7f5c959b29a3feb41eb447e8c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716932"
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="8c177-102">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="8c177-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="8c177-103">Ein Pfad ist eine Sequenz von Grafikprimitiven (Linien, Rechtecke, Kurven, Text und ähnliches), die bearbeitet und als einzelne Einheit gezeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c177-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="8c177-104">Ein Pfad aufgeteilt werden kann *Abbildungen* offen oder geschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="8c177-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="8c177-105">Eine Abbildung kann mehrere primitive Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c177-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="8c177-106">Zeichnen eines Pfads können Sie durch Aufrufen der <xref:System.Drawing.Graphics.DrawPath%2A> Methode der <xref:System.Drawing.Graphics> -Klasse, und Sie können einen Pfad eingeben, durch den Aufruf der <xref:System.Drawing.Graphics.FillPath%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c177-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c177-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8c177-107">In This Section</span></span>  
 [<span data-ttu-id="8c177-108">Vorgehensweise: Erstellen von Figuren aus Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="8c177-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="8c177-109">Zeigt, wie eine <xref:System.Drawing.Drawing2D.GraphicsPath> Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8c177-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="8c177-110">Vorgehensweise: Füllen offener Körper aus</span><span class="sxs-lookup"><span data-stu-id="8c177-110">How to: Fill Open Figures</span></span>](how-to-fill-open-figures.md)  
 <span data-ttu-id="8c177-111">Erläutert das Ausfüllen einer <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="8c177-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="8c177-112">Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie</span><span class="sxs-lookup"><span data-stu-id="8c177-112">How to: Flatten a Curved Path into a Line</span></span>](how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="8c177-113">Zeigt, wie vereinfacht eine <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="8c177-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8c177-114">Referenz</span><span class="sxs-lookup"><span data-stu-id="8c177-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="8c177-115">Beschreibt diese Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="8c177-115">Describes this class and contains links to all of its members.</span></span>
