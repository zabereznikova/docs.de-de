---
title: "Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente"
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
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc782ba262527a319cbb05cc6d36ca568afc55c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Gewusst wie: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente
Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben. Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert. Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert. Da nur ein Graphics-Vorgang auf dem Bildschirm ausgeführt wird, wird das Bildflimmern komplexe Zeichenoperationen zugeordneten entfernt. Für die meisten Anwendungen, die standardmäßig doppelte Pufferung gebotenen der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet die besten Ergebnisse. Standard-Windows Forms-Steuerelemente sind doppelte standardmäßig gepuffert. Sie können die standardmäßige doppelte Pufferung in Ihrem Formularen aktivieren und Steuerelemente auf zwei Arten erstellt. Können Sie entweder die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true`, oder Sie rufen die <xref:System.Windows.Forms.Control.SetStyle%2A> -Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag auf `true`. Beide Methoden aktiviert standardmäßig doppelte Pufferung für das Formular oder Steuerelement und flimmerfreier Grafikrendering bereitzustellen. Aufrufen der <xref:System.Windows.Forms.Control.SetStyle%2A> Methode wird empfohlen, nur für benutzerdefinierte Steuerelemente, die für das gesamte Renderingcode geschrieben haben.  
  
 Für erweiterte Szenarien mit doppelter Pufferung, z. B. Animation oder erweiterte Speicherverwaltungsfunktionen können Sie Ihre eigene doppelte Pufferung Logik implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Um Flackern zu verringern.  
  
-   Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A>-Eigenschaft auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- oder –  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.SetStyle%2A> -Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
