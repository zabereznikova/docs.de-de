---
title: "Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kurven, Abflachen"
  - "Zeichnen, Abflachen von Kurven"
  - "Flatten-Methode"
  - "Grafiken, Abflachen von Kurven zu Linien"
  - "GraphicsPath-Objekt"
  - "Pfade, Abflachen"
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie
Ein <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekt speichert eine Sequenz von Linien und Bézier\-Splines.  Sie können einem Pfad verschiedene Arten von Kurven \(Ellipsen, Bögen, kardinale Splines\) hinzufügen, aber jede Kurve wird in einen Bézier\-Spline konvertiert, bevor sie in dem Pfad gespeichert wird.  Beim Abflachen eines Pfades wird jeder Bézier\-Spline in dem Pfad in eine Sequenz von geraden Linien konvertiert.  Die folgende Abbildung zeigt einen Pfad vor und nach dem Abflachen.  
  
 ![Gerade Linien und Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.png "AboutGdip02\_Art32A")  
  
### So flachen Sie einen Pfad ab  
  
-   Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>\-Methode eines <xref:System.Drawing.Drawing2D.GraphicsPath>\-Objekts auf.  Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>\-Methode erhält ein Flachheitsargument, das den maximalen Abstand zwischen dem abgeflachten Pfad und dem ursprünglichen Pfad angibt.  
  
## Siehe auch  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Erstellen und Zeichnen von Pfaden](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)