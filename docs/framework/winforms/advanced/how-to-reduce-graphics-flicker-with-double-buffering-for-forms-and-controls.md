---
title: 'Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente'
description: Erfahren Sie, wie Sie die Grafik Flimmern mit doppelter Pufferung für Windows Forms reduzieren und mithilfe von Steuerelementen die Flimmer Probleme im Zusammenhang mit Paint-Vorgängen beheben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618128"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente
Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben. Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert. Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert. Da nur ein Grafik Vorgang auf dem Bildschirm ausgeführt wird, wird das Bild flimmern, das komplexen Zeichnungs Vorgängen zugeordnet ist, nicht mehr unterbunden. Bei den meisten Anwendungen bietet die standardmäßige doppelte Pufferung, die von der .NET Framework bereitgestellt wird, die besten Ergebnisse. Standard Windows Forms-Steuerelemente werden standardmäßig doppelt gepuffert. Sie können die standardmäßige doppelte Pufferung in Ihren Formularen und den erstellten Steuerelementen auf zwei Arten aktivieren. Sie können die- <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft entweder auf festlegen `true` , oder Sie können die-Methode aufzurufen, um <xref:System.Windows.Forms.Control.SetStyle%2A> das- <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> Flag auf festzulegen `true` . Beide Methoden ermöglichen die standardmäßige doppelte Pufferung für das Formular oder Steuerelement und bieten flimmerfreies Grafik Rendering. Das Aufrufen der- <xref:System.Windows.Forms.Control.SetStyle%2A> Methode wird nur für benutzerdefinierte Steuerelemente empfohlen, für die Sie den gesamten Renderingcode geschrieben haben.  
  
 Für erweiterte Szenarien mit doppelter Pufferung, wie z. b. Animation oder erweiterte Speicherverwaltung, können Sie eine eigene doppelte pufferlogik implementieren. Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>So reduzieren Sie Flimmern  
  
- Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> -Eigenschaft auf `true`fest.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- oder -  
  
- Ruft die- <xref:System.Windows.Forms.Control.SetStyle%2A> Methode auf, um das- <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> Flag auf festzulegen `true` .  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Doppelt gepufferte Grafiken](double-buffered-graphics.md)
- [Grafik und Zeichnen in Windows Forms](graphics-and-drawing-in-windows-forms.md)
