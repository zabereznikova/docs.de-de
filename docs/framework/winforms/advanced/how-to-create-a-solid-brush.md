---
title: 'Vorgehensweise: Erstellen Sie einen Pinsel mit Volltonfarbe'
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
ms.openlocfilehash: 0943bd1d5e05a1d726f0f6c55e372b9ff70cc4ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632269"
---
# <a name="how-to-create-a-solid-brush"></a>Vorgehensweise: Erstellen Sie einen Pinsel mit Volltonfarbe
In diesem Beispiel wird eine <xref:System.Drawing.SolidBrush> -Objekt, das verwendet werden kann eine <xref:System.Drawing.Graphics> Objekt zum Ausfüllen von Formen.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Sie die Verwendung abgeschlossen haben, rufen Sie <xref:System.IDisposable.Dispose%2A> für Objekte, die Systemressourcen, z. B. Pinselobjekte verwenden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [Erste Schritte mit Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Pinsel und gefüllte Formen in GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
- [Verwenden eines Pinsels zum Ausfüllen von Formen](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
