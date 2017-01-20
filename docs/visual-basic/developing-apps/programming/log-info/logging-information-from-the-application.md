---
title: "Logging Information from the Application (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Log object"
  - "My.Log object"
  - "applications [Visual Basic], logging information from"
  - "logging"
  - "My.Application.Log object"
  - "examples [Visual Basic], logging application information"
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Logging Information from the Application (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Dieser Abschnitt enthält Themen zum Protokollieren von Anwendungsinformationen unter Verwendung des `My.Application.Log`\-Objekts oder des `My.Log`\-Objekts sowie zum Erweitern der Protokollierungsfunktionen der Anwendung.  
  
 Das `Log`\-Objekt bietet Methoden für das Schreiben von Informationen in die Protokollüberwachungen der Anwendung, und die erweiterte `TraceSource`\-Eigenschaft des `Log`\-Objekts bietet detaillierte Konfigurationsinformationen.  Das `Log`\-Objekt wird in der Konfigurationsdatei der Anwendung konfiguriert.  
  
 Das `My.Log`\-Objekt ist nur für ASP.NET\-Anwendungen verfügbar.  Verwenden Sie für Clientanwendungen `My.Application.Log`.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## Aufgaben  
  
|To|Siehe|  
|--------|-----------|  
|Schreiben von Ereignisinformationen in die Anwendungsprotokolle|[Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Schreiben von Ausnahmeinformationen in die Anwendungsprotokolle|[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Schreiben von Ablaufverfolgungsinformationen in die Anwendungsprotokolle beim Starten und Beenden der Anwendung|[Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Konfigurieren von `My.Application.Log` zum Schreiben von Informationen in eine Textdatei.|[How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Konfigurieren von `My.Application.Log` zum Schreiben von Informationen in ein Ereignisprotokoll|[Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Ändern des Ziels, in das `My.Application.Log` Informationen schreibt|[Exemplarische Vorgehensweise: Ändern des Ortes, in den "My.Application.Log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Bestimmen des Zieles, in das `My.Application.Log` Informationen schreibt|[Exemplarische Vorgehensweise: Bestimmen, wohin "My.Application.Log" Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Erstellen einer benutzerdefinierten Protokollüberwachung für `My.Application.Log`|[Walkthrough: Creating Custom Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Filtern der Ausgabe der `My.Application.Log`\-Protokolle|[Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Troubleshooting: Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)