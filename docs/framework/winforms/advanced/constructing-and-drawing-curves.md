---
title: Erstellen und Zeichnen von Kurven
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 92e7b1e8b4ce37db633b5dafe212a252b854d1af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935446"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="17574-102">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="17574-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="17574-103">unterstützt verschiedene Typen von Kurven: Ellipsen, Bögen, kardinale Splinekurven und Béziersplinekurven.</span><span class="sxs-lookup"><span data-stu-id="17574-103">supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="17574-104">Eine Ellipse wird durch deren umschließendes Rechteck definiert; ein Bogen ist ein Teil einer Ellipse, die von einem Startwinkel und bei einem mittelpunktswinkel definiert.</span><span class="sxs-lookup"><span data-stu-id="17574-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="17574-105">Eine cardinal-Splinekurve durch ein Array von Punkten und Spannungsparameter definiert ist — die Kurve durchläuft reibungslos jeder Punkt im Array, und die Spannungsparameter wirkt sich auf die Möglichkeit, die Steuerpunkte.</span><span class="sxs-lookup"><span data-stu-id="17574-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="17574-106">Eine Béziersplinekurve wird durch zwei Endpunkte und die beiden Steuerpunkte, die die Kurve nicht über die Control-Punkte erfüllt definiert, aber die Kontrollpunkte, beeinflussen die Richtung, und biegen Sie im Laufe der Kurve von einem Endpunkt mit dem anderen.</span><span class="sxs-lookup"><span data-stu-id="17574-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17574-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="17574-107">In This Section</span></span>  
 [<span data-ttu-id="17574-108">Vorgehensweise: Zeichnen von kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="17574-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="17574-109">Beschreibt kardinale Splinekurven und wie sie gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="17574-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="17574-110">Vorgehensweise: Zeichnen Sie eine einzelne Béziersplinekurve</span><span class="sxs-lookup"><span data-stu-id="17574-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="17574-111">Beschreibt eine Béziersplinekurve und wie Sie gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="17574-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="17574-112">Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven</span><span class="sxs-lookup"><span data-stu-id="17574-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="17574-113">Erläutert, wie mehrere Béziersplinekurven nacheinander zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="17574-113">Explains how to draw several Bézier splines in sequence.</span></span>
