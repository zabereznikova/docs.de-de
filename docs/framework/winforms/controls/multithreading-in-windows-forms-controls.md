---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012723"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading in Windows Forms-Steuerelementen
In vielen Anwendungen können Sie Ihre Benutzeroberfläche (UI) Steigern der Reaktionsfähigkeit, indem zeitaufwändige Vorgänge in einem anderen Thread. Eine Reihe von Tools stehen für multithreading Ihrer Windows Forms-Steuerelemente, einschließlich der <xref:System.Threading> -Namespace, der <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode, und die `BackgroundWorker` Komponente.  
  
> [!NOTE]
>  Die `BackgroundWorker` Komponente ersetzt und funktionell erweitert die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Methode; diese werden jedoch beibehalten für die Abwärtskompatibilität und zur zukünftigen Verwendung, wenn Sie auswählen. Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Threadsichere Aufrufe von Windows Forms-Steuerelementen](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Zeigt, wie für threadsichere Aufrufe von Windows Forms-Steuerelementen.  
  
 [Vorgehensweise: Verwenden eines Hintergrundthreads zur Dateisuche](how-to-use-a-background-thread-to-search-for-files.md)  
 Zeigt, wie die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A> Methode, um nach Dateien suchen, asynchron.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Dokumentation der Komponente, die einen Arbeitsthread für asynchrone Vorgänge kapselt.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Dokumentiert, wie Sie einen Sound asynchron zu laden.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Dokumentation zum asynchronen Laden eines Bilds.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](how-to-run-an-operation-in-the-background.md)  
 Zeigt, wie einen zeitaufwändigen Vorgang mit führen die <xref:System.ComponentModel.BackgroundWorker> Komponente.  
  
 [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md)  
 Enthält Themen, die beschreiben, wie Sie mit der <xref:System.ComponentModel.BackgroundWorker> -Komponente für asynchrone Vorgänge.
