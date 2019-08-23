---
title: 'Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968601"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken
Für erweiterte Szenarien mit doppelter Pufferung können Sie die .NET Framework-Klassen verwenden, um Ihre eigene, doppelte pufferinglogik zu implementieren. Die Klasse, die für das zuordnen und Verwalten einzelner Grafik Puffer <xref:System.Drawing.BufferedGraphicsContext> zuständig ist, ist die-Klasse. Jede Anwendung verfügt über einen eigenen <xref:System.Drawing.BufferedGraphicsContext> Standard, der die standardmäßige doppelte Pufferung für diese Anwendung verwaltet. Sie können einen Verweis auf diese Instanz abrufen, indem Sie <xref:System.Drawing.BufferedGraphicsManager.Current%2A>aufrufen.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>So rufen Sie einen Verweis auf den Standardwert von BufferedGraphicsContext ab  
  
- Legen Sie <xref:System.Drawing.BufferedGraphicsManager.Current%2A> die-Eigenschaft fest, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > Sie müssen die `Dispose` -Methode für den <xref:System.Drawing.BufferedGraphicsContext> Verweis, den Sie von der <xref:System.Drawing.BufferedGraphicsManager> -Klasse empfangen, nicht aufzurufen. Der <xref:System.Drawing.BufferedGraphicsManager> verarbeitet die gesamte Speicher Belegung und-Verteilung für Standard <xref:System.Drawing.BufferedGraphicsContext> Instanzen.  
  
     Für grafisch intensive Anwendungen, wie z. b. Animation, kann die <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager>Leistung manchmal verbessert werden, indem <xref:System.Drawing.BufferedGraphicsContext> ein dedizierter anstelle der von bereitgestellten verwendet wird. Dies ermöglicht es Ihnen, Grafik Puffer einzeln zu erstellen und zu verwalten, ohne dass der Aufwand für die Verwaltung aller anderen gepufferten Grafiken, die der Anwendung zugeordnet sind, entstehen soll, obwohl der von der Anwendung genutzte Arbeitsspeicher größer ist.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>So erstellen Sie einen dedizierten BufferedGraphicsContext  
  
- Deklarieren und erstellen Sie eine neue Instanz <xref:System.Drawing.BufferedGraphicsContext> der-Klasse, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.BufferedGraphicsContext>
- [Doppelt gepufferte Grafiken](double-buffered-graphics.md)
- [Vorgehensweise: Manuelles renderdebuggergrafiken](how-to-manually-render-buffered-graphics.md)
