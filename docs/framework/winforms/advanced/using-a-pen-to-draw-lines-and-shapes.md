---
title: Verwenden eines Stiftes zum Zeichnen von Linien und Formen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f43316e2535aae6622ccf7952f649cdb92fc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="ba71b-102">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="ba71b-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="ba71b-103">Verwendung [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` Objekte Liniensegmente, Kurven und Umrisse von Formen gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba71b-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="ba71b-104">In diesem Abschnitt *Zeile* bezieht sich auf alle von diesen, sofern angegeben, um nur ein Liniensegment bedeuten.</span><span class="sxs-lookup"><span data-stu-id="ba71b-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="ba71b-105">Legen Sie die Eigenschaften eines Stiftes zum Steuern der Farbe, Breite, Ausrichtung und die Art des mit diesem Stift gezeichneten Linien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba71b-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba71b-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ba71b-106">In This Section</span></span>  
 [<span data-ttu-id="ba71b-107">Gewusst wie: Verwenden eines Stifts zum Zeichnen von Linien</span><span class="sxs-lookup"><span data-stu-id="ba71b-107">How to: Use a Pen to Draw Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="ba71b-108">Erläutert das Zeichnen von Linien.</span><span class="sxs-lookup"><span data-stu-id="ba71b-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="ba71b-109">Gewusst wie: Verwenden eines Stifts zum Zeichnen von Rechtecken</span><span class="sxs-lookup"><span data-stu-id="ba71b-109">How to: Use a Pen to Draw Rectangles</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="ba71b-110">Beschreibt, wie zum Zeichnen von Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="ba71b-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="ba71b-111">Gewusst wie: Festlegen von Stiftbreite und -ausrichtung</span><span class="sxs-lookup"><span data-stu-id="ba71b-111">How to: Set Pen Width and Alignment</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="ba71b-112">Erläutert, wie die Breite und die Ausrichtung des Ändern einer `Pen` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ba71b-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="ba71b-113">Gewusst wie: Zeichnen einer Linie mit Linienenden</span><span class="sxs-lookup"><span data-stu-id="ba71b-113">How to: Draw a Line with Line Caps</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="ba71b-114">Beschreibt, wie Hinzufügen von Linienenden beim Zeichnen einer Linie.</span><span class="sxs-lookup"><span data-stu-id="ba71b-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="ba71b-115">Gewusst wie: Verknüpfen von Linien</span><span class="sxs-lookup"><span data-stu-id="ba71b-115">How to: Join Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-join-lines.md)  
 <span data-ttu-id="ba71b-116">Zeigt, wie Sie zwei Zeilen verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ba71b-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="ba71b-117">Gewusst wie: Zeichnen einer benutzerdefinierten gestrichelten Linie</span><span class="sxs-lookup"><span data-stu-id="ba71b-117">How to: Draw a Custom Dashed Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="ba71b-118">Beschreibt, wie eine gestrichelte Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ba71b-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="ba71b-119">Gewusst wie: Zeichnen einer mit einer Textur ausgefüllten Linie</span><span class="sxs-lookup"><span data-stu-id="ba71b-119">How to: Draw a Line Filled with a Texture</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="ba71b-120">Es wird erläutert, wie eine Textur ausgefüllten Linie zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ba71b-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ba71b-121">Verweis</span><span class="sxs-lookup"><span data-stu-id="ba71b-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="ba71b-122">Beschreibt diese Klasse und enthält Links zu allen zugehörigen Membern.</span><span class="sxs-lookup"><span data-stu-id="ba71b-122">Describes this class and has links to all its members.</span></span>
