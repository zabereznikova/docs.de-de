---
title: "Troubleshooting: Log Listeners (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "event logs, troubleshooting"
  - "troubleshooting Visual Basic, event logs"
  - "troubleshooting event logs"
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Troubleshooting: Log Listeners (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können das `My.Application.Log`\-Objekt und das `My.Log`\-Objekt verwenden, um Informationen über in der Anwendung auftretende Ereignisse zu protokollieren.  
  
 Informationen zur Ermittlung der Protokollüberwachungen, die diese Meldungen empfangen, finden Sie unter [Exemplarische Vorgehensweise: Bestimmen, wohin "My.Application.Log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 Das `Log`\-Objekt kann Protokollfilterung verwenden, um die Anzahl und Art der protokollierten Informationen einzuschränken.  Wenn die Filter nicht korrekt konfiguriert sind, können die Protokolle falsche Informationen enthalten.  Weitere Informationen zum Filtern finden Sie unter [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Wenn jedoch ein Protokoll falsch konfiguriert ist, benötigen Sie möglicherweise weitere Informationen über dessen aktuelle Konfiguration.  Sie können diese Informationen über die erweiterte `TraceSource`\-Eigenschaft des Protokolls ermitteln.  
  
### So bestimmen Sie die Protokollüberwachungen für das Log\-Objekt mithilfe von Code  
  
1.  Importieren Sie am Beginn der Codedatei den <xref:System.Diagnostics>\-Namespace.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  Erstellen Sie eine Funktion, die eine Zeichenfolge mit Informationen für jeden Listener des Protokolls zurückgibt.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  Übergeben Sie die Auflistung der Ablaufverfolgungslistener des Protokolls an die `GetListeners`\-Funktion, und zeigen Sie den Rückgabewert an.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Exemplarische Vorgehensweise: Bestimmen, wohin "My.Application.Log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)