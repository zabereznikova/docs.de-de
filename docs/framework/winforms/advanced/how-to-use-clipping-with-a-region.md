---
title: 'Vorgehensweise: Verwenden von Ausschneiden mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163734"
---
# <a name="how-to-use-clipping-with-a-region"></a>Vorgehensweise: Verwenden von Ausschneiden mit einem Bereich
Eine der Eigenschaften von den <xref:System.Drawing.Graphics> -Klasse ist der Clip-Bereich. Alle Zeichnungen erreicht, indem ein bestimmten <xref:System.Drawing.Graphics> Objekt ist auf den Ausschneidebereich dieses beschränkt <xref:System.Drawing.Graphics> Objekt. Sie können die Clip-Bereich festlegen, durch den Aufruf der <xref:System.Drawing.Graphics.SetClip%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Pfad, der ein einzelnes Polygon besteht. Anschließend erstellt der Code eine Region, die basierend auf diesen Pfad. Die Region wird zum Übergeben der <xref:System.Drawing.Graphics.SetClip%2A> -Methode der ein <xref:System.Drawing.Graphics> -Objekt, und klicken Sie dann zwei Zeichenfolgen stammen.  
  
 Die folgende Abbildung zeigt die abgeschnittenen Zeichenfolgen.  
  
 ![Clip](./media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- [Bereiche in GDI+](regions-in-gdi.md)
- [Verwenden von Bereichen](using-regions.md)
