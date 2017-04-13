---
title: "BackgroundWorker-Komponente | Microsoft Docs"
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
  - "Asynchrones Muster"
  - "Hintergrundvorgänge"
  - "Hintergrundaufgaben"
  - "BackgroundWorker-Komponente"
  - "Komponenten [Windows Forms], Asynchron"
  - "Formulare, Hintergrundvorgänge"
  - "Formulare, Multithreading"
  - "Threading [Windows Forms], Hintergrundvorgänge"
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# BackgroundWorker-Komponente
Mithilfe der `BackgroundWorker`\-Komponente kann ein Vorgang in einem Formular oder Steuerelement asynchron ausgeführt werden.  
  
## In diesem Abschnitt  
 [Übersicht über die BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Beschreibt die `BackgroundWorker`\-Komponente, die es Ihnen ermöglicht, zeitaufwendige Vorgänge \("im Hintergrund"\) in einem anderen Thread als dem primären UI\-Thread der Anwendung asynchron auszuführen.  
  
 [Exemplarische Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 Veranschaulicht die Verwendung der `BackgroundWorker`\-Komponente im Designer, um einen zeitaufwendigen Vorgang in einem separaten Thread auszuführen.  
  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Veranschaulicht die Verwendung der `BackgroundWorker`\-Komponente, um einen zeitaufwendigen Vorgang in einem separaten Thread auszuführen.  
  
 [Exemplarische Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Erstellt eine Anwendung mithilfe des Designers, der mathematische Berechnungen asynchron ausführt.  
  
 [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 Erstellt eine Anwendung, die mathematische Berechnungen asynchron ausführt.  
  
 [Gewusst wie: Downloaden einer Datei im Hintergrund](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 Veranschaulicht die Verwendung der `BackgroundWorker`\-Komponente, um eine Datei in einem separaten Thread herunterzuladen.  
  
## Referenz  
 <xref:System.ComponentModel.BackgroundWorker>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Beschreibt den Typ, der Daten für das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis enthält.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Beschreibt den Typ, der Daten für das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis enthält.  
  
## Verwandte Abschnitte  
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Beschreibt, wie das asynchrone Muster die Vorteile von Multithreadanwendungen verfügbar macht, während zahlreiche komplexere Aspekte des Multithreaddesigns im Hintergrund ablaufen.