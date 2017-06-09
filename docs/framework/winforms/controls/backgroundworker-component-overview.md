---
title: "&#220;bersicht &#252;ber die BackgroundWorker-Komponente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BackgroundWorker"
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
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber die BackgroundWorker-Komponente
Es gibt viele häufig verwendete Operationen, deren Ausführung lange dauern kann.  Beispiel:  
  
-   Bilddownloads  
  
-   Webdienstaufrufe  
  
-   Dateidownloads und \-uploads \(einschließlich für Peer\-to\-Peer\-Anwendungen\)  
  
-   Komplexe lokale Berechnungen  
  
-   Datenbanktransaktionen  
  
-   Lokaler Festplattenzugriff, angesichts der langsamen Geschwindigkeit relativ zum Arbeitsspeicherzugriff  
  
 Operationen wie diese können bewirken, dass die Benutzeroberfläche während der Ausführung der Operation nicht mehr reagiert.  Wenn Sie dies vermeiden möchten und bei solchen Operationen lange Verzögerungen auftreten, stellt die <xref:System.ComponentModel.BackgroundWorker>\-Komponente eine geeignete Alternative dar.  
  
 Die <xref:System.ComponentModel.BackgroundWorker>\-Komponente ermöglicht es Ihnen, zeitaufwändige Operationen asynchron \("im Hintergrund"\) auf einem anderen Thread als dem primären UI\-Thread der Anwendung auszuführen.  Um einen <xref:System.ComponentModel.BackgroundWorker> zu verwenden, müssen Sie lediglich festlegen, welche zeitaufwändige Workermethode im Hintergrund ausgeführt werden soll, und anschließend die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode aufrufen.  Der aufrufende Thread wird weiterhin wie gewohnt ausgeführt, während die Workermethode asynchron ausgeführt wird.  Nach Abschluss der Methode gibt der <xref:System.ComponentModel.BackgroundWorker> eine Warnung an den aufrufenden Thread aus, indem er das <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>\-Ereignis auslöst, das optional die Ergebnisse der Operation enthält.  
  
 Die <xref:System.ComponentModel.BackgroundWorker>\-Komponente ist in der **Toolbox**, auf der Registerkarte **Komponenten** verfügbar.  Um dem Formular einen <xref:System.ComponentModel.BackgroundWorker> hinzuzufügen, ziehen Sie die <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf das Formular.  Es wird im Komponentenfach angezeigt, und seine Eigenschaften werden im **Eigenschaftenfenster** angezeigt.  
  
 Um die asynchrone Operation zu starten, verwenden Sie die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode.  <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> verwendet einen optionalen `object`\-Parameter, mit dem Argumente an die Workermethode übergeben werden können.  Die <xref:System.ComponentModel.BackgroundWorker>\-Klasse macht das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis verfügbar, mit dem der Workerthread über einen <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler verbunden ist.  
  
 Der <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler verwendet einen <xref:System.ComponentModel.DoWorkEventArgs>\-Parameter, der über eine <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>\-Eigenschaft verfügt.  Diese Eigenschaft empfängt den Parameter von <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und kann an die Workermethode übergeben werden, die im <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler aufgerufen wird.  Im folgenden Beispiel wird gezeigt, wie ein Ergebnis von einer Workermethode mit dem Namen `ComputeFibonacci` zugewiesen wird.  Es ist Teil eines größeren Beispiels, das Sie unter [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md) finden.  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Ereignisse](../../../../docs/standard/events/index.md).  
  
> [!CAUTION]
>  Wenn Sie Multithreading verwenden, setzen Sie sich möglicherweise sehr ernsten und komplexen Problemen aus.  Schlagen Sie unter [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) nach, bevor Sie eine Projektmappe implementieren, die Multithreading verwendet.  
  
 Weitere Informationen zur Verwendung der <xref:System.ComponentModel.BackgroundWorker>\-Klasse finden Sie unter [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
## Siehe auch  
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/de-de/c731a50c-09c1-4468-9646-54c86b75d269)   
 [Gewusst wie: Implementieren eines Formulars, das eine Hintergrundoperation verwendet](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)