---
title: 'Vorgehensweise: Erstellen eines Stifts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 69fe6157c710ae63df9dbf391a5d355d1c3f9765
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148108"
---
# <a name="how-to-create-a-pen"></a>Vorgehensweise: Erstellen eines Stifts
In diesem Beispiel wird eine <xref:System.Drawing.Pen> Objekt.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Nach dem Verwenden von Objekten, die Systemressourcen, z. B. nutzen <xref:System.Drawing.Pen> Objekte, rufen Sie <xref:System.Drawing.Pen.Dispose%2A> darauf.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Pen>
- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Stifte, Linien und Rechtecke in GDI+](pens-lines-and-rectangles-in-gdi.md)
