---
title: Protokollieren von Informationen aus der Anwendung
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 43738b2d654435532a98654cbc40af134d43f02c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410022"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Protokollieren von Informationen aus der Anwendung (Visual Basic)

Dieser Abschnitt enthält Themen zur Protokollierung von Anwendungsinformationen mithilfe der Objekte `My.Application.Log` oder `My.Log` und zur Erweiterung der Protokollierungsfunktionen der Anwendung.  
  
 Das `Log`-Objekt stellt Methoden zum Schreiben von Informationen für die Protokolllistener der Anwendung zur Verfügung, und die erweiterte Eigenschaft `TraceSource` des `Log`-Objekts bietet ausführliche Konfigurationsinformationen. Das `Log`-Objekt wird von der Konfigurationsdatei der Anwendung konfiguriert.  
  
 Das `My.Log`-Objekt ist nur für ASP.NET-Anwendungen verfügbar. Verwenden Sie `My.Application.Log` für Clientanwendungen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Aufgaben  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Schreiben Sie Ereignisinformationen in die Anwendungsprotokolle.|[How to: Schreiben von Protokollmeldungen](how-to-write-log-messages.md)|  
|Schreiben Sie Ausnahmeinformationen in die Anwendungsprotokolle.|[How to: Protokollieren von Ausnahmen](how-to-log-exceptions.md)|  
|Schreiben Sie beim Starten und Herunterfahren der Anwendung Ablaufverfolgungsinformationen in die Anwendungsprotokolle.|[How to: Protokollieren von Meldungen beim Starten oder Beenden der Anwendung](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Konfigurieren Sie `My.Application.Log`, um Informationen in eine Textdatei zu schreiben.|[How to: Schreiben von Ereignisinformationen in eine Textdatei](how-to-write-event-information-to-a-text-file.md)|  
|Konfigurieren Sie `My.Application.Log`, um Informationen in ein Ereignisprotokoll zu schreiben.|[How to: Schreiben in ein Anwendungsereignisprotokoll](how-to-write-to-an-application-event-log.md)|  
|Ändern Sie den Ort, in den `My.Application.Log` Informationen schreibt.|[Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](walkthrough-changing-where-my-application-log-writes-information.md)|  
|Bestimmen Sie, wohin `My.Application.Log` Informationen schreibt.|[Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt](walkthrough-determining-where-my-application-log-writes-information.md)|  
|Erstellen Sie einen benutzerdefinierten Protokolllistener für `My.Application.Log`.|[Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern](walkthrough-creating-custom-log-listeners.md)|  
|Filtern Sie die Ausgabe der Protokolle `My.Application.Log`.|[Exemplarische Vorgehensweise: Filtern der Ausgabe von „My.Application.Log“](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Arbeiten mit Anwendungsprotokollen](working-with-application-logs.md)
- [Problembehandlung: Protokolllistener](troubleshooting-log-listeners.md)
