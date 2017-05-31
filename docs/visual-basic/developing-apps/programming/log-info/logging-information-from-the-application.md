---
title: Protokollieren von Informationen aus der Anwendung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 25bf4e1d8b9b87c1545272c0d2746dc808d3fa4b
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="logging-information-from-the-application-visual-basic"></a>Protokollieren von Informationen aus der Anwendung (Visual Basic)
Dieser Abschnitt enthält Themen zur Protokollierung von Anwendungsinformationen mithilfe der Objekte `My.Application.Log` oder `My.Log` und zur Erweiterung der Protokollierungsfunktionen der Anwendung.  
  
 Das `Log`-Objekt stellt Methoden zum Schreiben von Informationen für die Protokolllistener der Anwendung zur Verfügung, und die erweiterte Eigenschaft `TraceSource` des `Log`-Objekts bietet ausführliche Konfigurationsinformationen. Das `Log`-Objekt wird von der Konfigurationsdatei der Anwendung konfiguriert.  
  
 Das `My.Log`-Objekt ist nur für ASP.NET-Anwendungen verfügbar. Verwenden Sie `My.Application.Log` für Clientanwendungen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Aufgaben  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Schreiben Sie Ereignisinformationen in die Anwendungsprotokolle.|[Gewusst wie: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Schreiben Sie Ausnahmeinformationen in die Anwendungsprotokolle.|[Gewusst wie: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Schreiben Sie beim Starten und Herunterfahren der Anwendung Ablaufverfolgungsinformationen in die Anwendungsprotokolle.|[Gewusst wie: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Konfigurieren Sie `My.Application.Log`, um Informationen in eine Textdatei zu schreiben.|[Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Konfigurieren Sie `My.Application.Log`, um Informationen in ein Ereignisprotokoll zu schreiben.|[Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Ändern Sie den Ort, in den `My.Application.Log` Informationen schreibt.|[Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Bestimmen Sie, wohin `My.Application.Log` Informationen schreibt.|[Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Erstellen Sie einen benutzerdefinierten Protokolllistener für `My.Application.Log`.|[Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Filtern Sie die Ausgabe der Protokolle `My.Application.Log`.|[Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Problembehandlung: Protokolllistener](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
