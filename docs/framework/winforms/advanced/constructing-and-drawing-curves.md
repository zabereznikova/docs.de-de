---
title: Erstellen und Zeichnen von Kurven
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 801af10f7b9e5e7998fc061537977c5bced6bdb3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="50ee4-102">Erstellen und Zeichnen von Kurven</span><span class="sxs-lookup"><span data-stu-id="50ee4-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="50ee4-103">unterstützt mehrere Typen von Kurven: Ellipsen, Bögen, kardinale Splines und Bézier-Splines.</span><span class="sxs-lookup"><span data-stu-id="50ee4-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="50ee4-104">Durch das umschließende Rechteck wird eine Ellipse definiert. ein Bogen ist ein Teil einer Ellipse, die durch einen Anfangswinkel und bei einem mittelpunktswinkel definiert.</span><span class="sxs-lookup"><span data-stu-id="50ee4-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="50ee4-105">Eine cardinal-Splinekurve durch ein Array aus Punkten und Spannungsparameter definiert ist – die Kurve durchläuft reibungslos jedem Punkt im Array, und die Spannungsparameter beeinflusst die Möglichkeit, Steuerpunkte.</span><span class="sxs-lookup"><span data-stu-id="50ee4-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="50ee4-106">Eine Béziersplinekurve wird durch zwei Endpunkte und die beiden Steuerpunkte, die die Kurve nicht über die Steuerpunkte übergibt definiert, aber die Steuerpunkte beeinflussen die Richtung und biegen wie die Kurve wird von einem Endpunkt zum anderen wechselt.</span><span class="sxs-lookup"><span data-stu-id="50ee4-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50ee4-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="50ee4-107">In This Section</span></span>  
 [<span data-ttu-id="50ee4-108">Gewusst wie: Zeichnen von kardinalen Splines</span><span class="sxs-lookup"><span data-stu-id="50ee4-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="50ee4-109">Beschreibt kardinale Splines und wie sie gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50ee4-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="50ee4-110">Gewusst wie: Zeichnen eines einzelnen Bézier-Splines</span><span class="sxs-lookup"><span data-stu-id="50ee4-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="50ee4-111">Beschreibt eine Béziersplinekurve und eine gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50ee4-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="50ee4-112">Gewusst wie: Zeichnen einer Folge von Bézier-Splines</span><span class="sxs-lookup"><span data-stu-id="50ee4-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="50ee4-113">Erläutert, wie mehrere Bézier-Splines nacheinander gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50ee4-113">Explains how to draw several Bézier splines in sequence.</span></span>
