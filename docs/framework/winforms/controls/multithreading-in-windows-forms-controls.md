---
title: Multithreading in Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742141"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading in Windows Forms-Steuerelementen
In vielen Anwendungen können Sie die Benutzeroberfläche (UI) reaktionsfähiger machen, indem Sie zeitaufwändige Vorgänge in einem anderen Thread ausführen. Zum Multithreading Ihrer Windows Forms-Steuerelemente stehen eine Reihe von Tools zur Verfügung, einschließlich des <xref:System.Threading>-Namespace, der <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>-Methode und der `BackgroundWorker` Komponente.  
  
> [!NOTE]
> Die `BackgroundWorker` Komponente ersetzt und fügt Funktionen zum <xref:System.Threading>-Namespace und zur <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>-Methode hinzu. Diese werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie sich entscheiden. Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Zeigt, wie Thread sichere Aufrufe an Windows Forms-Steuerelemente durchführen werden.  
  
 [Gewusst wie: Verwenden eines Hintergrundthreads zur Dateisuche](how-to-use-a-background-thread-to-search-for-files.md)  
 Zeigt, wie Sie den <xref:System.Threading>-Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A>-Methode verwenden, um Dateien asynchron zu suchen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Dokumentiert eine Komponente, die einen Arbeits Thread für asynchrone Vorgänge kapselt.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Dokumente zum asynchronen Laden eines Sounds.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Dokumente zum asynchronen Laden eines Bilds.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)  
 Zeigt, wie Sie einen zeitaufwändigen Vorgang mit der <xref:System.ComponentModel.BackgroundWorker> Komponente ausführen.  
  
 [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md)  
 Enthält Themen, in denen beschrieben wird, wie die <xref:System.ComponentModel.BackgroundWorker> Komponente für asynchrone Vorgänge verwendet wird.
