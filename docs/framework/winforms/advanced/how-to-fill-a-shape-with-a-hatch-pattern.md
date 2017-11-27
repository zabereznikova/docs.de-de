---
title: "Gewusst wie: Ausfüllen einer Form mit einer Schraffur"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36ee5b7152dabc7dcd1e0c844e8549eb03aa0045
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Gewusst wie: Ausfüllen einer Form mit einer Schraffur
Eine Schraffur besteht aus zwei Farben: eine für den Hintergrund und eine für die Zeilen, die das Muster über dem Hintergrund bilden. Um eine geschlossene Form mit einer Schraffur zu füllen, verwenden Sie eine <xref:System.Drawing.Drawing2D.HatchBrush> Objekt. Im folgenden Beispiel wird veranschaulicht, wie eine Ellipse, die mit einer Schraffur füllen:  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Konstruktor hat drei Argumente: die Schraffurart, die Farbe der Schraffurlinie und die Farbe des Hintergrunds. Das Schraffurstilargument kann einen beliebigen Wert zwischen der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration. Es gibt mehr als 50 Elemente in der <xref:System.Drawing.Drawing2D.HatchStyle> -Enumeration; nur einige dieser Elemente sind in der folgenden Liste dargestellt:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 Die folgende Abbildung zeigt das ausgefüllte Ellipse.  
  
 ![Muster Schraffieren](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
