---
title: 'Vorgehensweise: Legen Sie die Farbe eines Stiftes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: d0402a7d6bb641ef6d97eb41bc25f3c59b3b4250
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569439"
---
# <a name="how-to-set-the-color-of-a-pen"></a>Vorgehensweise: Legen Sie die Farbe eines Stiftes
In diesem Beispiel ändert sich die Farbe einer bereits vorhandenen <xref:System.Drawing.Pen> Objekt  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Drawing.Pen> Objekt mit dem Namen `myPen`.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Rufen Sie <xref:System.Drawing.Pen.Dispose%2A> für Objekte, die Systemressourcen (z. B. <xref:System.Drawing.Pen> Objekte) nach deren Verwendung.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Pen>
- [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Vorgehensweise: Erstellen eines Stifts](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
- [Verwenden eines Stifts zum Zeichnen von Linien und Formen](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Stifte, Linien und Rechtecke in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
