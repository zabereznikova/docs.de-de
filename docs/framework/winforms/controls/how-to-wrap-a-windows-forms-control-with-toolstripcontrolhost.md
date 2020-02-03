---
title: Wrap-Steuerelement mit ToolStripControlHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStrip control [Windows Forms], wrapping controls
- toolbars [Windows Forms], wrapping controls
- ToolStrip control [Windows Forms], hosting controls
ms.assetid: e2ce4990-661d-4882-a116-8a9eb575dc84
ms.openlocfilehash: c7dbe042623006ed9501016669d6451ba0667cbc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728178"
---
# <a name="how-to-wrap-a-windows-forms-control-with-toolstripcontrolhost"></a>Gewusst wie: Verwenden eines ToolStripControlHost als Wrapper für ein Windows Forms-Steuerelement
<xref:System.Windows.Forms.ToolStripControlHost> dient zum Aktivieren des Hostings von beliebigen Windows Forms-Steuerelementen mithilfe des <xref:System.Windows.Forms.ToolStripControlHost>-Konstruktors oder durch die Erweiterung von <xref:System.Windows.Forms.ToolStripControlHost> selbst. Es ist einfacher, das Steuerelement durch Erweitern von <xref:System.Windows.Forms.ToolStripControlHost> und Implementieren der Eigenschaften und Methoden zu umschließen, die häufig verwendete Eigenschaften und Methoden des Steuerelements verfügbar machen. Sie können Ereignisse für das Steuerelement auch auf der <xref:System.Windows.Forms.ToolStripControlHost>-Ebene verfügbar machen.  
  
### <a name="to-host-a-control-in-a-toolstripcontrolhost-by-derivation"></a>So hosten Sie ein Steuerelement in einem "ToolStripControlHost" durch Ableitung  
  
1. Erweitern Sie <xref:System.Windows.Forms.ToolStripControlHost>. Implementieren Sie einen Parameter losen Konstruktor, der den Basisklassenkonstruktor aufruft, der das gewünschte Steuerelement übergibt.  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#10)]  
  
2. Deklarieren Sie eine Eigenschaft mit demselben Typ wie für das umschlossene Steuerelement, und geben Sie `Control` als richtigen Typ des Steuerelements im Accessor der Eigenschaft zurück.  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#11)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#11)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#11)]  
  
3. Machen Sie andere häufig verwendete Eigenschaften und Methoden des umschlossenen Steuerelements mithilfe von Eigenschaften und Methoden in der erweiterten Klasse verfügbar.  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#12)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#12)]  
  
4. Überschreiben Sie optional die Methoden <xref:System.Windows.Forms.ToolStripControlHost.OnSubscribeControlEvents%2A> und <xref:System.Windows.Forms.ToolStripControlHost.OnUnsubscribeControlEvents%2A>, und fügen Sie die bereitzustellenden Steuerelementereignisse hinzu.  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#16)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#16)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#16)]  
  
5. Geben Sie die erforderlichen Wrapper für die Ereignisse an, die Sie verfügbar machen möchten.  
  
     [!code-cpp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#17)]
     [!code-csharp[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#17)]
     [!code-vb[System.Windows.Forms.ToolStripControlHost#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#17)]  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CPP/form1.cpp#13)]
 [!code-csharp[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/CS/form1.cs#13)]
 [!code-vb[System.Windows.Forms.ToolStripControlHost#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripControlHost/VB/form1.vb#13)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
Dieses Beispiel erfordert Folgendes:
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStripControlHost>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
