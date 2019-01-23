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
ms.openlocfilehash: b27a013d2cf66fb12365bffc35a07ed32bc25a2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554490"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken
Für erweiterte Szenarien mit doppelter Pufferung, können Sie die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Klassen Ihre eigene doppelte Pufferungslogik implementieren. Die Klasse, die für das zuordnen und Verwalten einzelner Grafikpuffer verantwortlich ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse. Jede Anwendung verfügt über einen standardmäßigen <xref:System.Drawing.BufferedGraphicsContext> , die die gesamte standardmäßige doppelte Pufferung für die Anwendung verwaltet. Sie können einen Verweis auf diese Instanz abrufen, durch den Aufruf der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Um einen Verweis auf den Standardwert BufferedGraphicsContext erhalten  
  
-   Legen Sie die <xref:System.Drawing.BufferedGraphicsManager.Current%2A> -Eigenschaft, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Sie müssen nicht aufrufen, die `Dispose` Methode für die <xref:System.Drawing.BufferedGraphicsContext> -Verweis, der erhalten Sie von der <xref:System.Drawing.BufferedGraphicsManager> Klasse. Die <xref:System.Drawing.BufferedGraphicsManager> behandelt die gesamte die speicherbelegung und die Verteilung für standardmäßige <xref:System.Drawing.BufferedGraphicsContext> Instanzen.  
  
     Von grafisch anspruchsvollen Anwendungen wie z. B. Animationen, Sie können manchmal Leistung verbessern, indem eine dedizierte <xref:System.Drawing.BufferedGraphicsContext> statt der <xref:System.Drawing.BufferedGraphicsContext> gebotenen die <xref:System.Drawing.BufferedGraphicsManager>. Dadurch können Sie zum Erstellen und verwalten Grafikpuffer einzeln, ohne dass der Mehraufwand an Leistung verwalten Sie alle anderen gepufferte Grafiken Ihrer Anwendung zugeordnet, jedoch von der Anwendung belegt größer werden.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Erstellen Sie einen dedizierte BufferedGraphicsContext  
  
-   Deklarieren und erstellen Sie eine neue Instanz der dem <xref:System.Drawing.BufferedGraphicsContext> Klasse, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.BufferedGraphicsContext>
- [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [Vorgehensweise: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
