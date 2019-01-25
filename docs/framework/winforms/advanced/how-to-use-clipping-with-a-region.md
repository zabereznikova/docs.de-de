---
title: 'Vorgehensweise: Verwenden von Clipping mit einer Region'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: 5482218a8d6310ce49a1f9f5f02b3b8e36c1fd90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590655"
---
# <a name="how-to-use-clipping-with-a-region"></a>Vorgehensweise: Verwenden von Clipping mit einer Region
Eine der Eigenschaften von den <xref:System.Drawing.Graphics> -Klasse ist der Clip-Bereich. Alle Zeichnungen erreicht, indem ein bestimmten <xref:System.Drawing.Graphics> Objekt ist auf den Ausschneidebereich dieses beschränkt <xref:System.Drawing.Graphics> Objekt. Sie können die Clip-Bereich festlegen, durch den Aufruf der <xref:System.Drawing.Graphics.SetClip%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen Pfad, der ein einzelnes Polygon besteht. Anschließend erstellt der Code eine Region, die basierend auf diesen Pfad. Die Region wird zum Übergeben der <xref:System.Drawing.Graphics.SetClip%2A> -Methode der ein <xref:System.Drawing.Graphics> -Objekt, und klicken Sie dann zwei Zeichenfolgen stammen.  
  
 Die folgende Abbildung zeigt die abgeschnittenen Zeichenfolgen.  
  
 ![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch
- [Bereiche in GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)
