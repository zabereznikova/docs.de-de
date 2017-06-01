---
title: "Multithreading in Windows Forms-Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BackgroundWorker-Komponente"
  - "BeginInvoke-Methode"
  - "Threading [Windows Forms], Steuerelemente"
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Multithreading in Windows Forms-Steuerelementen
In zahlreichen Anwendungen kann die Reaktionsgeschwindigkeit der Benutzeroberfläche verbessert werden, indem zeitaufwendige Vorgänge in einem anderen Thread ausgeführt werden.  Zum Implementieren des Multithreadings in Windows Forms\-Steuerelemente stehen zahlreiche Tools zur Verfügung, darunter der <xref:System.Threading>\-Namespace, die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName>\-Methode und die `BackgroundWorker`\-Komponente.  
  
> [!NOTE]
>  Obwohl die `BackgroundWorker`\-Komponente den <xref:System.Threading>\-Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName>\-Methode ersetzt und funktionell erweitert, werden diese sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## In diesem Abschnitt  
 [Gewusst wie: Threadsicheres Aufrufen von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Veranschaulicht, wie threadsichere Aufrufe an Windows Forms\-Steuerelemente ausgeführt werden.  
  
 [Gewusst wie: Verwenden eines Hintergrundthreads zur Dateisuche](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Veranschaulicht, wie der <xref:System.Threading>\-Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A>\-Methode für die asynchrone Suche nach Dateien verwendet werden.  
  
## Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Enthält die Dokumentation der Komponente, die einen Arbeitsthread für asynchrone Vorgänge kapselt.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Enthält eine Dokumentation zum asynchronen Laden eines Sounds.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Enthält eine Dokumentation zum asynchronen Laden eines Bildes.  
  
## Verwandte Abschnitte  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Veranschaulicht, wie ein zeitaufwendiger Vorgang mit der <xref:System.ComponentModel.BackgroundWorker>\-Komponente ausgeführt wird.  
  
 [Übersicht über die BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Enthält Themen, in denen die Verwendung der <xref:System.ComponentModel.BackgroundWorker>\-Komponente für asynchrone Vorgänge beschrieben wird.