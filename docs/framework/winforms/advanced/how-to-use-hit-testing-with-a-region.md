---
title: 'Gewusst wie: Trefferüberprüfung mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 40297fada3d042aee8c317eb787de03662f86cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523083"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Gewusst wie: Trefferüberprüfung mit einem Bereich
Treffertests dient zum bestimmen, ob der Cursor über einem angegebenen Objekt, z. B. ein Symbol oder eine Schaltfläche befindet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Region Plus geformten durch, die die Vereinigung der zwei rechteckige Bereiche bilden. Vorausgesetzt, dass die Variable `point` enthält den Speicherort des letzten klicken. Der Code überprüft, ob `point` in der Region Plus strukturiert ist. Wenn der Punkt in der Region (Treffer) ist, wird der Bereich mit einem nicht transparenten Pinselfarbe gefüllt. Andernfalls wird der Bereich mit einer halb transparenten Pinselfarbe gefüllt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Region>  
 [Bereiche in GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Gewusst wie: Ausschneiden mit einem Bereich](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
