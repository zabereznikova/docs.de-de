---
title: Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
ms.openlocfilehash: 34f4f11176b3827ec3e4622944ffe02be5207df9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300280"
---
# <a name="error-handling"></a>Fehlerbehandlung
## <a name="error-handling-in-windows-communication-foundation"></a>Fehlerbehandlung in Windows Communication Foundation  
 Wenn in einem Dienst eine unerwartete Ausnahme oder ein unerwarteter Fehler auftritt, gibt es mehrere Möglichkeiten zum Entwerfen einer Lösung für die Ausnahmebehandlung. Es gibt zwar keine einzelnen "richtig" oder "best Practices" für die Fehlerbehandlung Lösung, es gibt mehrere Möglichkeiten zu berücksichtigen. Wird normalerweise empfohlen, eine eine Hybrid-Lösung implementieren, die mehrere Ansätze aus der Liste unten, abhängig von der Komplexität der WCF-Implementierung, Typ und Häufigkeit der Ausnahmen, die behandelten im Vergleich zu nicht behandelten Natur von kombiniert die Ausnahmen, und die Ihnen zugeordneten Ablaufverfolgung, Protokollierung und richtlinienanforderungen.  
  
 Diese Lösungen werden im restlichen Teil dieses Abschnitts genauer erläutert.  
  
### <a name="the-microsoft-enterprise-library"></a>Die Microsoft Enterprise Library  
 Der Ausnahmebehandlungs-Anwendungsblock der Microsoft Enterprise Library erleichtert das Implementieren häufiger Entwurfsmuster und das Erstellen einer einheitlichen Strategie für die Verarbeitung von Ausnahmen, die auf allen Architekturebenen einer Unternehmensanwendung auftreten. Er unterstützt den typischen Code in den Catch-Anweisungen von Anwendungskomponenten. Statt diesen Code (z. B. Code zum Protokollieren von Ausnahmeinformationen) in der gesamten Anwendung in identischen Catch-Blöcken zu wiederholen, ermöglicht der Ausnahmebehandlungs-Anwendungsblock Entwicklern das Kapseln dieser Logik als wiederverwendbare Ausnahmehandler.  
  
 Diese Bibliothek enthält standardmäßig einen Fehlervertragsausnahmehandler. Dieser Ausnahmehandler ist für die Verwendung an den Grenzen des WCF (Windows® Communication Foundation)-Diensts vorgesehen, und er generiert aus der Ausnahme einen neuen Fehlervertrag.  
  
 Anwendungsblöcke enthalten in der Regel häufig verwendete bewährte Methoden und bieten eine allgemeine Vorgehensweise für die Ausnahmebehandlung in der gesamten Anwendung. Jedoch können benutzerdefinierte Fehlerhandler und Fehlerverträge, die selbst entwickelt wurden, ebenfalls sehr hilfreich sein. Beispielsweise bieten Benutzerdefinierte Fehlerhandler eine ausgezeichnete Gelegenheit, automatisch alle Ausnahmen FaultExceptions höher stufen und Hinzufügen von Protokollierfunktionen zu Ihrer Anwendung.  
  
 Weitere Informationen finden Sie unter [Microsoft Enterprise Library](https://docs.microsoft.com/previous-versions/msp-n-p/ff632023(v=pandp.10)).  
  
### <a name="dealing-with-expected-exceptions"></a>Behandeln von erwarteten Ausnahmen  
 Die korrekte Vorgehensweise ist Abfangen erwarteter Ausnahmen in jedem Vorgang oder die relevanten Erweiterungspunkt, entscheiden Sie, ob sie aus wiederhergestellt werden können, und geben Sie den ordnungsgemäßen benutzerdefinierten Fehler in einer FaultException zurück\<T >  
  
### <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>Behandeln von unerwarteten Ausnahmen mit einem IErrorHandler  
 Um unerwartete Ausnahmen zu beheben, ist die empfohlene Vorgehensweise "Einen" ierrorhandler "verknüpfen" aus. Fehlerhandler fangen nur Ausnahmen, die WCF-Laufzeitebene (der "" dienstmodellebene), nicht auf Kanalebene. Die einzige Möglichkeit, einen IErrorHandler auf Kanalebene zu verknüpfen, ist das Erstellen eines benutzerdefinierten Kanals, und dies wird in den meisten Szenarien nicht empfohlen.  
  
 Eine "unerwartete"Ausnahme ist im Allgemeinen weder eine nicht behebbare Ausnahme noch eine Verarbeitungsausnahme; Es ist, stattdessen eine unerwartete Benutzerausnahme. Eine nicht behebbare Ausnahme (z. B. eine Out-of-Memory-Ausnahme) – eine in der Regel anhand der [Dienstmodell-Ausnahmehandler](xref:System.ServiceModel.Dispatcher.ExceptionHandler) automatisch kann nicht in der Regel nicht erfolgreich behandelt werden, und der einzige Grund, eine Ausnahme zu behandeln Alle möglicherweise zusätzliche Protokollierung oder eine Standardausnahme an den Client zurückgegeben. Eine Verarbeitungsausnahme tritt meist beim Verarbeiten der Nachricht auf, beispielsweise auf Serialisierungs-, Encoder- oder Formatiererebene, und kann im Allgemeinen nicht von einem "IErrorHandler" behandelt werden, weil die Fehlerbehandlung noch nicht oder nicht mehr eingreifen kann, wenn diese Ausnahmen auftreten. Ebenso können Transportausnahmen nicht von einem IErrorHandler behandelt werden.  
  
 Mit einem IErrorHandler können Sie das Verhalten der Anwendung explizit steuern, wenn eine Ausnahme ausgelöst wird. Sie haben folgende Möglichkeiten:  
  
1. Entscheiden, ob ein Fehler an den Client gesendet wird  
  
2. Ersetzen einer Ausnahme durch einen Fehler  
  
3. Ersetzen eines Fehlers durch einen anderen Fehler  
  
4. Ausführen von Protokollierung oder Ablaufverfolgung  
  
5. Ausführen von anderen benutzerdefinierten Aktivitäten  
  
 Sie können einen benutzerdefinierten Fehlerhandler installieren, indem Sie ihn der ErrorHandlers-Eigenschaft der Kanalverteiler für den Dienst hinzufügen.  Es ist zulässig, mehrere Fehlerhandler zu verwenden. Sie werden in der Reihenfolge aufgerufen, in der sie der Auflistung hinzugefügt wurden.  
  
 IErrorHandler.ProvideFault steuert die Fehlermeldung, die an den Client gesendet wird. Diese Methode wird unabhängig vom Typ der Ausnahme aufgerufen, die durch einen Vorgang im Dienst ausgelöst wird. Wenn hier kein Vorgang ausgeführt wird, wird WCF mit dem Standardverhalten fortgesetzt und auf die gleiche Weise wie ohne benutzerdefinierte Fehlerhandler ausgeführt.  
  
 Sie können diese Herangehensweise beispielsweise verwenden, wenn Ausnahmen an einer zentralen Stelle in Fehler umgewandelt werden sollen, bevor sie an den Client gesendet werden (um sicherzustellen, dass die Instanz nicht verworfen wird und der Kanal nicht in den Faulted-Zustand wechselt).  
  
 Die "IErrorHandler.HandleError"-Methode wird in der Regel verwendet, um Verhalten für Fehler zu implementieren, z. B. Fehlerprotokollierung, Systembenachrichtigungen, Beenden der Anwendung usw. "IErrorHandler.HandleError" kann an mehreren Stellen im Dienst aufgerufen werden. Je nachdem, wo der Fehler ausgelöst wird, erfolgt der Aufruf der "HandleError"-Methode vom selben Thread wie der Vorgang oder auch nicht. Dies lässt sich nicht eindeutig festlegen.  
  
### <a name="dealing-with-exceptions-outside-wcf"></a>Behandeln von Ausnahmen außerhalb von WCF  
 Häufig treten Konfigurationsausnahmen, Ausnahmen im Hinblick auf Datenbankverbindungszeichenfolgen und ähnliche Ausnahmen im Kontext einer WCF-Anwendung auf, ohne vom Dienstmodell oder vom Webdienst selbst verursacht worden zu sein. Diese Ausnahmen sind "regular" Ausnahmen außerhalb des Webdiensts und behandelt werden sollen, ebenso wie andere externen Ausnahmen in der Umgebung behandelt werden.  
  
### <a name="tracing-exceptions"></a>Ablaufverfolgung von Ausnahmen  
 Die Ablaufverfolgung ist, die nur "Catch-All" Stelle, wo eine potenziell alle Ausnahmen angezeigt werden. Weitere Informationen zur Ablaufverfolgung und Protokollierung von Ausnahmen finden Sie unter "Ablaufverfolgung und Protokollierung".  
  
### <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>URI-Vorlagenfehler bei Verwendung von WebGetAttribute und WebInvokeAttribute  
 Mit dem WebGet-Attribut und dem WebInvoke-Attribut können Sie eine URI-Vorlage angeben, die Vorgangsparametern Komponenten der Anforderungsadresse zuordnet. Beispielsweise ordnet die URI-Vorlage "weather/{state}/{city}" die Anforderungsadresse als Literaltoken, als Parameter mit dem Namen state und als Parameter mit dem Namen city zu. Diese Parameter können dann nach Name an einige der formalen Parameter des Vorgangs gebunden werden.  
  
 Die Vorlagenparameter werden im URI als Zeichenfolgen angezeigt, während die formalen Parameter eines typisierten Vertrags möglicherweise nicht vom Typ String sind. Daher muss eine Konvertierung erfolgen, bevor der Vorgang aufgerufen werden kann. Ein [Tabelle der konvertierungsformate](wcf-web-http-programming-model-overview.md) verfügbar ist.  
  
 Wenn jedoch die Konvertierung fehlschlägt, gibt es keine Möglichkeit, dies dem Vorgang zu signalisieren. Stattdessen wird für die Typkonvertierung ein Verteilungsfehler ausgegeben.  
  
 Ein Typkonvertierungs-Verteilungsfehler kann wie viele andere Typen von Verteilungsfehlern durch das Installieren eines Fehlerhandlers überprüft werden. Der IErrorHandler-Erweiterungspunkt wird aufgerufen, um auf Dienstebene aufgetretene Ausnahmen zu behandeln. Dort kann die an den Aufrufer zurückzusendende Antwort ausgewählt werden, und es lassen sich benutzerdefinierte Aufgaben ausführen und Berichte erstellen.  
  
## <a name="see-also"></a>Siehe auch

- [Einfache WCF-Programmierung](../basic-wcf-programming.md)
