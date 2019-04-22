---
title: 'Vorgehensweise: Verwenden von Treffertests mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150500"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Vorgehensweise: Verwenden von Treffertests mit einem Bereich
Für den Treffertest dient zu bestimmen, ob der Cursor über ein bestimmtes Objekt, z. B. ein Symbol oder eine Schaltfläche befindet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Region Plus gestalteten durch, die die Union der zwei rechteckige Bereiche bilden. Vorausgesetzt, dass die Variable `point` enthält den Speicherort aus, klicken Sie im letzten. Der Code prüft, ob `point` ist in der Region Pluszeichen bildet. Wenn der Punkt in der Region (ein Treffer) ist, wird der Bereich mit einem roten transparenten Pinsel gefüllt. Andernfalls wird der Bereich mit einem roten halb transparenten Pinsel gefüllt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Region>
- [Bereiche in GDI+](regions-in-gdi.md)
- [Vorgehensweise: Verwenden von Clipping mit einer Region](how-to-use-clipping-with-a-region.md)
