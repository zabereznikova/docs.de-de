---
title: "Gewusst wie: Trefferüberprüfung mit einem Bereich"
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
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: adc55d137a5578dbe8649afa02ab8525d4913cd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
