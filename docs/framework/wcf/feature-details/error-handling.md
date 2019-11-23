---
title: Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
ms.openlocfilehash: f6c0d676a37648678b2b726a46a6238ccc1b3331
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004889"
---
# <a name="error-handling-in-windows-communication-foundation-wcf"></a>Fehlerbehandlung in Windows Communication Foundation (WCF)

Wenn in einem Dienst eine unerwartete Ausnahme oder ein unerwarteter Fehler auftritt, gibt es mehrere Möglichkeiten zum Entwerfen einer Lösung für die Ausnahmebehandlung. Obwohl es keine einzige "korrekte" oder "bewährte Methode"-Fehler Behandlungslösung gibt, gibt es mehrere gültige Pfade, die Sie beachten müssen. Normalerweise wird empfohlen, eine Hybridlösung zu implementieren, die mehrere Ansätze in der folgenden Liste kombiniert. Dies hängt von der Komplexität der WCF-Implementierung, dem Typ und der Häufigkeit der Ausnahmen, der behandelten und nicht behandelten Natur des Ausnahmen sowie alle zugehörigen Ablauf Verfolgungs-, Protokollierungs-oder Richtlinien Anforderungen.

Diese Lösungen werden im restlichen Teil dieses Abschnitts genauer erläutert.

## <a name="the-microsoft-enterprise-library"></a>Die Microsoft Enterprise Library

Der Ausnahmebehandlungs-Anwendungsblock der Microsoft Enterprise Library erleichtert das Implementieren häufiger Entwurfsmuster und das Erstellen einer einheitlichen Strategie für die Verarbeitung von Ausnahmen, die auf allen Architekturebenen einer Unternehmensanwendung auftreten. Er unterstützt den typischen Code in den Catch-Anweisungen von Anwendungskomponenten. Statt diesen Code (z. B. Code zum Protokollieren von Ausnahmeinformationen) in der gesamten Anwendung in identischen Catch-Blöcken zu wiederholen, ermöglicht der Ausnahmebehandlungs-Anwendungsblock Entwicklern das Kapseln dieser Logik als wiederverwendbare Ausnahmehandler.

Diese Bibliothek enthält standardmäßig einen Fehlervertragsausnahmehandler. Dieser Ausnahmehandler ist für die Verwendung an WCF-Dienst Grenzen konzipiert und generiert einen neuen Fehler Vertrag aus der Ausnahme.

Anwendungsblöcke enthalten in der Regel häufig verwendete bewährte Methoden und bieten eine allgemeine Vorgehensweise für die Ausnahmebehandlung in der gesamten Anwendung. Jedoch können benutzerdefinierte Fehlerhandler und Fehlerverträge, die selbst entwickelt wurden, ebenfalls sehr hilfreich sein. Benutzerdefinierte Fehlerhandler bieten beispielsweise die Möglichkeit, alle Ausnahmen automatisch auf faultexceptions zu Stufen und ihrer Anwendung Protokollierungsfunktionen hinzuzufügen.

Weitere Informationen finden Sie [unter Microsoft Enterprise Library](https://docs.microsoft.com/previous-versions/msp-n-p/ff632023(v=pandp.10)).

## <a name="dealing-with-expected-exceptions"></a>Umgang mit erwarteten Ausnahmen

Die richtige Vorgehensweise ist das Abfangen erwarteter Ausnahmen in jedem Vorgang oder relevanten Erweiterbarkeits Punkt, die Entscheidung, ob Sie von wieder hergestellt werden können, und das Zurückgeben des richtigen benutzerdefinierten Fehlers in einer FaultException-\<t->.
  
## <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>Umgang mit unerwarteten Ausnahmen mit einem IErrorHandler

Um unerwartete Ausnahmen zu behandeln, wird empfohlen, einen IErrorHandler als "Hook" zu erhalten. Fehlerhandler fangen nur Ausnahmen auf der WCF-Lauf Zeit Ebene (der Dienstmodell Ebene) und nicht auf der Kanal Ebene ab. Die einzige Möglichkeit, einen {1}IErrorHandler{2} auf Kanalebene zu verknüpfen, ist das Erstellen eines benutzerdefinierten Kanals, und dies wird in den meisten Szenarien nicht empfohlen.

Eine "unerwartete Ausnahme" ist im allgemeinen weder eine nicht behebbare Ausnahme noch eine Verarbeitungs Ausnahme. Es handelt sich vielmehr um eine unerwartete Benutzer Ausnahme. Eine nicht BEHEB Bare Ausnahme (z. b. eine Ausnahme aufgrund ungenügenden Arbeitsspeichers) – eine, die im Allgemeinen vom [Dienstmodell-Ausnahme Handler](xref:System.ServiceModel.Dispatcher.ExceptionHandler) automatisch verarbeitet wird – kann im Allgemeinen nicht ordnungsgemäß behandelt werden, und der einzige Grund für die Behandlung einer solchen Ausnahme ist möglicherweise eine zusätzliche Protokollierung oder die Rückgabe einer Standard Ausnahme an den Client. Eine Verarbeitungsausnahme tritt meist beim Verarbeiten der Nachricht auf, beispielsweise auf Serialisierungs-, Encoder- oder Formatiererebene, und kann im Allgemeinen nicht von einem "IErrorHandler" behandelt werden, weil die Fehlerbehandlung noch nicht oder nicht mehr eingreifen kann, wenn diese Ausnahmen auftreten. Ebenso können Transportausnahmen nicht von einem {1}IErrorHandler{2} behandelt werden.

Mit einem {1}IErrorHandler{2} können Sie das Verhalten der Anwendung explizit steuern, wenn eine Ausnahme ausgelöst wird. Sie haben folgende Möglichkeiten:  

1. Entscheiden Sie, ob ein Fehler an den Client gesendet werden soll oder nicht.

2. Ersetzen Sie eine Ausnahme durch einen Fehler.

3. Ersetzen Sie einen Fehler durch einen anderen Fehler.

4. Ausführen von Protokollierung oder Ablauf Verfolgung.

5. Führen Sie andere benutzerdefinierte Aktivitäten aus.

Sie können einen benutzerdefinierten Fehlerhandler installieren, indem Sie ihn der ErrorHandlers-Eigenschaft der Kanalverteiler für den Dienst hinzufügen.  Es ist zulässig, mehrere Fehlerhandler zu verwenden. Sie werden in der Reihenfolge aufgerufen, in der sie der Auflistung hinzugefügt wurden.

{1}IErrorHandler.ProvideFault{2} steuert die Fehlermeldung, die an den Client gesendet wird. Diese Methode wird unabhängig vom Typ der Ausnahme aufgerufen, die durch einen Vorgang im Dienst ausgelöst wird. Wenn hier kein Vorgang ausgeführt wird, nimmt WCF das Standardverhalten an und wird so fortgesetzt, als wären keine benutzerdefinierten Fehlerhandler vorhanden.

Sie können diese Herangehensweise beispielsweise verwenden, wenn Ausnahmen an einer zentralen Stelle in Fehler umgewandelt werden sollen, bevor sie an den Client gesendet werden (um sicherzustellen, dass die Instanz nicht verworfen wird und der Kanal nicht in den Faulted-Zustand wechselt).

Die IErrorHandler. Handler Error-Methode wird normalerweise verwendet, um Fehler bedingte Verhalten zu implementieren, z. b. Fehler Protokollierung, System Benachrichtigungen, Herunterfahren der Anwendung usw. IErrorHandler. Handler Error kann an mehreren Stellen im Dienst aufgerufen werden. je nachdem, wo der Fehler ausgelöst wird, kann die Methode "Lenker Error" vom gleichen Thread wie der Vorgang aufgerufen werden. in dieser Hinsicht werden keine Garantien gestellt.

## <a name="dealing-with-exceptions-outside-wcf"></a>Behandeln von Ausnahmen außerhalb von WCF

Häufig treten Konfigurationsausnahmen, Ausnahmen im Hinblick auf Datenbankverbindungszeichenfolgen und ähnliche Ausnahmen im Kontext einer WCF-Anwendung auf, ohne vom Dienstmodell oder vom Webdienst selbst verursacht worden zu sein. Diese Ausnahmen sind reguläre Ausnahmen, die außerhalb des Webdiensts liegen, und sollten so behandelt werden, wie andere externe Ausnahmen in der Umgebung behandelt werden müssen.

## <a name="tracing-exceptions"></a>Ablaufverfolgung von Ausnahmen

Die Ablauf Verfolgung ist die einzige "Catch-All"-Stelle, bei der potenziell alle Ausnahmen angezeigt werden können. Weitere Informationen zur Ablaufverfolgung und Protokollierung von Ausnahmen finden Sie unter "Ablaufverfolgung und Protokollierung".

## <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>URI-Vorlagenfehler bei Verwendung von {1}WebGetAttribute{2} und {3}WebInvokeAttribute{4}

Mit dem WebGet-Attribut und dem WebInvoke-Attribut können Sie eine URI-Vorlage angeben, die Vorgangsparametern Komponenten der Anforderungsadresse zuordnet. Beispielsweise ordnet die URI-Vorlage "weather/{state}/{city}" die Anforderungsadresse als Literaltoken, als Parameter mit dem Namen {1}state{2} und als Parameter mit dem Namen {3}city{4} zu. Diese Parameter können dann nach Name an einige der formalen Parameter des Vorgangs gebunden werden.

Die Vorlagenparameter werden im URI als Zeichenfolgen angezeigt, während die formalen Parameter eines typisierten Vertrags möglicherweise nicht vom Typ String sind. Daher muss eine Konvertierung erfolgen, bevor der Vorgang aufgerufen werden kann. Eine [Tabelle mit Konvertierungs Formaten](wcf-web-http-programming-model-overview.md) ist verfügbar.

Wenn jedoch die Konvertierung fehlschlägt, gibt es keine Möglichkeit, dies dem Vorgang zu signalisieren. Stattdessen wird für die Typkonvertierung ein Verteilungsfehler ausgegeben.

Ein Typkonvertierungs-Verteilungsfehler kann wie viele andere Typen von Verteilungsfehlern durch das Installieren eines Fehlerhandlers überprüft werden. Der IErrorHandler-Erweiterungspunkt wird aufgerufen, um auf Dienstebene aufgetretene Ausnahmen zu behandeln. Dort kann die an den Aufrufer zurückzusendende Antwort ausgewählt werden, und es lassen sich benutzerdefinierte Aufgaben ausführen und Berichte erstellen.

## <a name="see-also"></a>Siehe auch

- [Einfache WCF-Programmierung](../basic-wcf-programming.md)
