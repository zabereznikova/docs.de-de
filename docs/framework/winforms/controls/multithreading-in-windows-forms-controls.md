---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 68822c62a1a195ce3128d51c765cfeba2056955d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536356"
---
# <a name="multithreading-in-windows-forms-controls"></a>Multithreading in Windows Forms-Steuerelementen
In vielen Anwendungen können Sie Ihre Benutzeroberfläche (UI) anpassbar, indem zeitaufwändige Operationen in einem anderen Thread ausführen. Eine Reihe von Tools stehen für multithreading Windows Forms-Steuerelemente, einschließlich der <xref:System.Threading> Namespace, der <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode, und die `BackgroundWorker` Komponente.  
  
> [!NOTE]
>  Die `BackgroundWorker` Komponente ersetzt und funktionell erweitert, um die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Methode; diese werden jedoch beibehalten für Abwärtskompatibilität und für zukünftige Verwendung, falls gewünscht. Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Zeigt, wie Sie threadsichere Aufrufe an Windows Forms-Steuerelemente.  
  
 [Gewusst wie: Verwenden eines Hintergrundthreads zur Dateisuche](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Zeigt, wie die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A> Methode zur Suche nach Dateien asynchron.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Die Dokumentation der Komponente, die einen Arbeitsthread für asynchrone Vorgänge kapselt.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Dokumentiert, wie Sie einen Sound asynchron zu laden.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Dokumentiert, wie Sie ein Bild asynchron geladen werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Zeigt die Vorgehensweise führen Sie einen zeitaufwändigen Vorgang mit der <xref:System.ComponentModel.BackgroundWorker> Komponente.  
  
 [Übersicht über die BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Enthält Themen, die beschreiben, wie Sie die <xref:System.ComponentModel.BackgroundWorker> -Komponente für asynchrone Vorgänge.
