---
title: 'Vorgehensweise: Trefferüberprüfung mit einem Bereich'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: a9435724e7674fd196ad70bdfd0ab43808a53058
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709744"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Vorgehensweise: Trefferüberprüfung mit einem Bereich
Für den Treffertest dient zu bestimmen, ob der Cursor über ein bestimmtes Objekt, z. B. ein Symbol oder eine Schaltfläche befindet.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Region Plus gestalteten durch, die die Union der zwei rechteckige Bereiche bilden. Vorausgesetzt, dass die Variable `point` enthält den Speicherort aus, klicken Sie im letzten. Der Code prüft, ob `point` ist in der Region Pluszeichen bildet. Wenn der Punkt in der Region (ein Treffer) ist, wird der Bereich mit einem roten transparenten Pinsel gefüllt. Andernfalls wird der Bereich mit einem roten halb transparenten Pinsel gefüllt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Region>
- [Bereiche in GDI+](regions-in-gdi.md)
- [Vorgehensweise: Verwenden von Clipping mit einer Region](how-to-use-clipping-with-a-region.md)
