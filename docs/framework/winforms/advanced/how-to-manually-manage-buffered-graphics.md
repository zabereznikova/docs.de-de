---
title: "Gewusst wie: Manuelles Verwalten von gepufferten Grafiken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BufferedGraphicsContext-Klasse"
  - "Flimmern, Reduzieren durch manuelles Verwalten von Grafiken"
  - "Grafiken, Verwalten, gepuffert"
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Manuelles Verwalten von gepufferten Grafiken
Für anspruchsvollere Szenarien mit doppelter Pufferung können Sie die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Klassen verwenden, um Ihre eigene doppelte Pufferungslogik zu implementieren.  Die Klasse, die für das Zuordnen und Verwalten einzelner Grafikpuffer verantwortlich ist, ist die <xref:System.Drawing.BufferedGraphicsContext>\-Klasse.  Jede Anwendung verfügt über einen standardmäßigen <xref:System.Drawing.BufferedGraphicsContext>, der die gesamte standardmäßige doppelte Pufferung für die Anwendung verwaltet.  Sie können einen Verweis auf diese Instanz abrufen, indem Sie <xref:System.Drawing.BufferedGraphicsManager.Current%2A> aufrufen.  
  
### So erhalten Sie einen Verweis auf den standardmäßigen BufferedGraphicsContext  
  
-   Legen Sie die <xref:System.Drawing.BufferedGraphicsManager.Current%2A>\-Eigenschaft fest, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Sie müssen nicht die `Dispose`\-Methode für den <xref:System.Drawing.BufferedGraphicsContext>\-Verweis aufrufen, den Sie von der <xref:System.Drawing.BufferedGraphicsManager>\-Klasse abrufen.  Der <xref:System.Drawing.BufferedGraphicsManager> übernimmt die gesamte Speicherbelegung und \-verteilung für standardmäßige <xref:System.Drawing.BufferedGraphicsContext>\-Instanzen.  
  
     Bei grafisch anspruchsvollen Anwendungen wie Animationen können Sie manchmal die Leistung verbessern, indem Sie einen dedizierten <xref:System.Drawing.BufferedGraphicsContext> anstelle des <xref:System.Drawing.BufferedGraphicsContext> verwenden, der vom <xref:System.Drawing.BufferedGraphicsManager> bereitgestellt wird.  Dadurch können Sie Grafikpuffer einzeln erstellen und verwalten, ohne dass die Verwaltung aller anderen gepufferten Anwendungsgrafiken die Leistung beeinträchtigt. Der von der Anwendung beanspruchte Arbeitsspeicher nimmt jedoch zu.  
  
### So erstellen Sie einen dedizierten BufferedGraphicsContext  
  
-   Deklarieren und erstellen Sie eine neue Instanz der <xref:System.Drawing.BufferedGraphicsContext>\-Klasse, wie im folgenden Codebeispiel gezeigt.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## Siehe auch  
 <xref:System.Drawing.BufferedGraphicsContext>   
 [Doppelt gepufferte Grafiken](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Gewusst wie: Manuelles Rendern von gepufferten Grafiken](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)