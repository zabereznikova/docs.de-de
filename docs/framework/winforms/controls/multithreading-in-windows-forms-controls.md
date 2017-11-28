---
title: Multithreading in Windows Forms-Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
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
  
## <a name="reference"></a>Verweis  
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
