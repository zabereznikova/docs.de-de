---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952681"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading in Windows Forms-Steuerelementen
In vielen Anwendungen können Sie die Benutzeroberfläche (UI) reaktionsfähiger machen, indem Sie zeitaufwändige Vorgänge in einem anderen Thread ausführen. Zum Multithreading Ihrer Windows Forms-Steuerelemente stehen eine Reihe von Tools zur Verfügung <xref:System.Threading> , einschließlich des- <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Namespace, der `BackgroundWorker` -Methode und der-Komponente.  
  
> [!NOTE]
> Die `BackgroundWorker` Komponente ersetzt und fügt Funktionen <xref:System.Threading> zum-Namespace und zur <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode hinzu. Diese werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen. Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Thread sichere Aufrufe an Windows Forms Steuerelemente erstellen](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Zeigt, wie Thread sichere Aufrufe an Windows Forms-Steuerelemente durchführen werden.  
  
 [Vorgehensweise: Verwenden Sie einen Hintergrund Thread, um nach Dateien zu suchen.](how-to-use-a-background-thread-to-search-for-files.md)  
 Zeigt, wie Sie mit <xref:System.Threading> dem-Namespace <xref:System.Windows.Forms.Control.BeginInvoke%2A> und der-Methode asynchron nach Dateien suchen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Dokumentiert eine Komponente, die einen Arbeits Thread für asynchrone Vorgänge kapselt.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Dokumente zum asynchronen Laden eines Sounds.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Dokumente zum asynchronen Laden eines Bilds.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)  
 Zeigt, wie ein zeitaufwendiger Vorgang mit der <xref:System.ComponentModel.BackgroundWorker> -Komponente durchgeführt wird.  
  
 [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md)  
 Enthält Themen, in denen beschrieben wird, <xref:System.ComponentModel.BackgroundWorker> wie die-Komponente für asynchrone Vorgänge verwendet wird.
