---
title: 'Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334fc0fee7166f8f8c5c1db61d3b9e370da72f87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie
Ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt eine Sequenz von Linien und Bézier-Splines speichert. Sie können mehrere Typen von Kurven (Ellipsen, Bögen, kardinale Splines) hinzufügen, um einen Pfad, aber jede Kurve wird in eine Bézier-Spline konvertiert, vor dem Speichern im Pfad. Reduzieren einen Pfad besteht aus einzelnen Bézier-Splines in den Pfad in eine Sequenz von gerade Linien konvertieren. Die folgende Abbildung zeigt einen Pfad vor und nach vereinfachen.  
  
 ![Gerade Linien und Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>So vereinfachen Sie einen Pfad  
  
-   Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Methode von einer <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt. Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> -Methode erhält ein Flachheitsargument, der den maximalen Abstand zwischen dem vereinfachten und der ursprüngliche Pfad angibt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
