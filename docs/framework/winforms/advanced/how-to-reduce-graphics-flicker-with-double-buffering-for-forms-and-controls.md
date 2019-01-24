---
title: 'Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: 96bdaa8882b5f33c68d2a87dd28163c1acd606bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663582"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente
Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben. Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert. Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert. Da auf dem Bildschirm nur eine Grafikoperation ausgeführt wird, wird die durch komplexe Zeichenoperationen ausgelöste Bildflimmern beseitigt. Für die meisten Anwendungen, die von bereitgestellten standardmäßige doppelte Pufferung der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bieten die besten Ergebnisse. Standardmäßigen Windows Forms-Steuerelemente sind doppelte standardmäßig gepuffert. Sie können standardmäßige doppelte Pufferung in Ihren Formularen und Steuerelementen auf zwei Arten erstellt. Können Sie entweder die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft `true`, oder Sie rufen die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag auf `true`. Beide Methoden werden standardmäßige doppelte Pufferung für das Formular oder Steuerelement zu aktivieren und Bereitstellen flimmerfreier Grafik-Rendering. Aufrufen der <xref:System.Windows.Forms.Control.SetStyle%2A> Methode wird empfohlen, nur für benutzerdefinierte Steuerelemente, die für die Sie alle wiedergebenden Code geschrieben haben.  
  
 Für erweiterte Szenarien mit doppelter Pufferung, wie Animationen oder erweiterter Speicherverwaltung können Sie Ihre eigene doppelte Pufferung Logik implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Um Flimmern zu verringern  
  
-   Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> -Eigenschaft auf `true`fest.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- oder –  
  
-   Rufen Sie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode zum Festlegen der <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [Grafik und Zeichnen in Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
