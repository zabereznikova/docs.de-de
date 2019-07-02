---
title: Erstellen und Zeichnen von Kurven
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506102"
---
# <a name="constructing-and-drawing-curves"></a>Erstellen und Zeichnen von Kurven
GDI + unterstützt mehrere Typen von Kurven: Ellipsen, Bögen, kardinale Splinekurven und Béziersplinekurven. Eine Ellipse wird durch deren umschließendes Rechteck definiert; ein Bogen ist ein Teil einer Ellipse, die von einem Startwinkel und bei einem mittelpunktswinkel definiert. Eine cardinal-Splinekurve durch ein Array von Punkten und Spannungsparameter definiert ist — die Kurve durchläuft reibungslos jeder Punkt im Array, und die Spannungsparameter wirkt sich auf die Möglichkeit, die Steuerpunkte. Eine Béziersplinekurve wird durch zwei Endpunkte und die beiden Steuerpunkte, die die Kurve nicht über die Control-Punkte erfüllt definiert, aber die Kontrollpunkte, beeinflussen die Richtung, und biegen Sie im Laufe der Kurve von einem Endpunkt mit dem anderen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Zeichnen von kardinalen Splines](how-to-draw-cardinal-splines.md)  
 Beschreibt kardinale Splinekurven und wie sie gezeichnet.  
  
 [Vorgehensweise: Zeichnen Sie eine einzelne Béziersplinekurve](how-to-draw-a-single-bezier-spline.md)  
 Beschreibt eine Béziersplinekurve und wie Sie gezeichnet.  
  
 [Vorgehensweise: Zeichnen Sie eine Sequenz von Béziersplinekurven](how-to-draw-a-sequence-of-bezier-splines.md)  
 Erläutert, wie mehrere Béziersplinekurven nacheinander zu zeichnen.
