---
title: 'Gewusst wie: Manuelles Verwalten von gepufferten Grafiken'
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Gewusst wie: Manuelles Verwalten von gepufferten Grafiken
Für erweiterte Szenarien mit doppelter Pufferung können Sie die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Klassen, Ihre eigene Logik Doppelpufferung implementieren. Die Klasse, die verantwortlich für das zuordnen und Verwalten einzelner Grafikpuffer ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse. Jede Anwendung verfügt über einen eigenen Standard <xref:System.Drawing.BufferedGraphicsContext> , verwaltet alle Standardeinstellungen, die doppelte Pufferung für die Anwendung. Sie können einen Verweis auf diese Instanz abrufen, durch Aufrufen der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Abrufen eines Verweises auf den standardmäßigen BufferedGraphicsContext  
  
-   Legen Sie die <xref:System.Drawing.BufferedGraphicsManager.Current%2A> Eigenschaft, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Sie müssen nicht Aufrufen der `Dispose` Methode auf die <xref:System.Drawing.BufferedGraphicsContext> -Referenz, die Sie von erhalten die <xref:System.Drawing.BufferedGraphicsManager> Klasse. Die <xref:System.Drawing.BufferedGraphicsManager> behandelt die speicherbelegung und die Verteilung für standardmäßige <xref:System.Drawing.BufferedGraphicsContext> Instanzen.  
  
     Für grafisch anspruchsvolle Anwendungen z. B. Animation, Sie können in einigen Fällen verbessern, indem mithilfe einer dedizierten <xref:System.Drawing.BufferedGraphicsContext> statt der <xref:System.Drawing.BufferedGraphicsContext> gebotenen der <xref:System.Drawing.BufferedGraphicsManager>. Dadurch können Sie zum Erstellen und verwalten Grafikpuffer einzeln ohne Beeinträchtigung der Systemleistung, verwalten Sie alle anderen gepufferten Grafiken Ihrer Anwendung zugeordnet, obwohl die von der Anwendung belegten Arbeitsspeichers größer werden.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>So erstellen einen dedizierten BufferedGraphicsContext  
  
-   Deklarieren und erstellen Sie eine neue Instanz der dem <xref:System.Drawing.BufferedGraphicsContext> Klasse, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Gewusst wie: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
