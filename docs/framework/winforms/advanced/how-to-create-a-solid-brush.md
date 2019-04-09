---
title: 'Vorgehensweise: Erstellen eines Volltonpinsels'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213440"
---
# <a name="how-to-create-a-solid-brush"></a>Vorgehensweise: Erstellen eines Volltonpinsels
In diesem Beispiel wird eine <xref:System.Drawing.SolidBrush> -Objekt, das verwendet werden kann eine <xref:System.Drawing.Graphics> Objekt zum Ausfüllen von Formen.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Sie die Verwendung abgeschlossen haben, rufen Sie <xref:System.IDisposable.Dispose%2A> für Objekte, die Systemressourcen, z. B. Pinselobjekte verwenden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md)
- [Pinsel und gefüllte Formen in GDI+](brushes-and-filled-shapes-in-gdi.md)
- [Verwenden eines Pinsels zum Ausfüllen von Formen](using-a-brush-to-fill-shapes.md)
