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
# <a name="constructing-and-drawing-curves"></a>Erstellen und Zeichnen von Kurven
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]unterstützt mehrere Typen von Kurven: Ellipsen, Bögen, kardinale Splines und Bézier-Splines. Durch das umschließende Rechteck wird eine Ellipse definiert. ein Bogen ist ein Teil einer Ellipse, die durch einen Anfangswinkel und bei einem mittelpunktswinkel definiert. Eine cardinal-Splinekurve durch ein Array aus Punkten und Spannungsparameter definiert ist – die Kurve durchläuft reibungslos jedem Punkt im Array, und die Spannungsparameter beeinflusst die Möglichkeit, Steuerpunkte. Eine Béziersplinekurve wird durch zwei Endpunkte und die beiden Steuerpunkte, die die Kurve nicht über die Steuerpunkte übergibt definiert, aber die Steuerpunkte beeinflussen die Richtung und biegen wie die Kurve wird von einem Endpunkt zum anderen wechselt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Zeichnen von kardinalen Splines](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Beschreibt kardinale Splines und wie sie gezeichnet werden soll.  
  
 [Gewusst wie: Zeichnen eines einzelnen Bézier-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Beschreibt eine Béziersplinekurve und eine gezeichnet werden soll.  
  
 [Gewusst wie: Zeichnen einer Folge von Bézier-Splines](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Erläutert, wie mehrere Bézier-Splines nacheinander gezeichnet werden soll.
