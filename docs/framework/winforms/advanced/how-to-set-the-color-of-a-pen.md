---
title: 'Gewusst wie: Festlegen der Farbe eines Stiftes'
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
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66527be5a70f9c7c60f4ca3836ee68b96872442f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a>Gewusst wie: Festlegen der Farbe eines Stiftes
In diesem Beispiel ändert sich die Farbe einer bereits vorhandenen <xref:System.Drawing.Pen> Objekt  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Drawing.Pen> Objekt mit dem Namen `myPen`.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Rufen Sie <xref:System.Drawing.Pen.Dispose%2A> für Objekte, die an Systemressourcen beanspruchen (z. B. <xref:System.Drawing.Pen> Objekte), nachdem Sie diese nicht mehr verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Pen>  
 [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Gewusst wie: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Stifte, Linien und Rechtecke in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
