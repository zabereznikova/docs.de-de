---
title: Beobachtbarkeitsmuster
description: Observability-Muster für Native Cloud-Anwendungen
ms.date: 08/10/2020
ms.openlocfilehash: 2a6ef0e58f1e20667167042614768b099f640858
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539852"
---
# <a name="observability-patterns"></a>Beobachtbarkeitsmuster

Ebenso wie Muster entwickelt wurden, um das Layout von Code in Anwendungen zu unterstützen, gibt es auf zuverlässige Weise Muster für Betriebs Anwendungen. Bei der Verwaltung von Anwendungen sind drei nützliche Muster aufgetreten: **Protokollierung**, **Überwachung**und **Warnungen**.

## <a name="when-to-use-logging"></a>Verwendungszwecke der Protokollierung

Unabhängig davon, wie sorgfältig wir sind, Verhalten sich Anwendungen fast immer auf unerwartete Weise in der Produktionsumgebung. Wenn Benutzer Probleme mit einer Anwendung melden, ist es hilfreich, wenn Sie sehen können, was mit der APP passiert ist, als das Problem aufgetreten ist. Eine der bewährten Methoden zum Erfassen von Informationen darüber, was eine Anwendung während der Ausführung tut, besteht darin, die Anwendung zu schreiben, was Sie tut. Dieser Prozess wird als Protokollierung bezeichnet. Immer wenn Ausfälle oder Probleme in der Produktion auftreten, sollte das Ziel darin bestehen, die Bedingungen, unter denen die Ausfälle aufgetreten sind, in einer nicht-Produktionsumgebung zu reproduzieren. Eine gute Protokollierung ist eine Roadmap für Entwickler, die Sie befolgen können, um Probleme in einer Umgebung zu duplizieren, die Sie testen und experimentieren können.

### <a name="challenges-when-logging-with-cloud-native-applications"></a>Herausforderungen bei der Protokollierung mit nativen cloudanwendungen

In herkömmlichen Anwendungen werden Protokolldateien in der Regel auf dem lokalen Computer gespeichert. Tatsächlich gibt es für UNIX-ähnliche Betriebssysteme eine Ordnerstruktur, die für alle Protokolle definiert ist, in der Regel unter `/var/log` .

![Protokollierung in einer Datei in einer monolithischen app. ](./media/single-monolith-logging.png)
 **Abbildung 7-1**. Protokollierung in einer Datei in einer monolithischen app.

Die Nützlichkeit der Protokollierung in einer Flatfile auf einem einzelnen Computer wird in einer cloudumgebung erheblich reduziert. Anwendungen, die Protokolle erstellen, haben möglicherweise keinen Zugriff auf den lokalen Datenträger, oder der lokale Datenträger ist möglicherweise sehr vorübergehend, da Container durch physische Computer gemischt werden. Selbst das einfache hochskalieren monolithischer Anwendungen über mehrere Knoten hinweg kann es schwierig machen, die geeignete dateibasierte Protokolldatei zu finden.

![Protokollieren von Dateien in einer skalierten monolithischen app. ](./media/multiple-node-monolith-logging.png)
 **Abbildung 7-2**. Protokollieren von Dateien in einer skalierten monolithischen app.

Cloud native-Anwendungen, die mit einer microservicearchitektur entwickelt wurden, stellen auch einige Herausforderungen bei dateibasierten Protokollierungen dar. Benutzer Anforderungen können sich nun über mehrere Dienste erstrecken, die auf unterschiedlichen Computern ausgeführt werden und Server lose Funktionen enthalten können, die keinen Zugriff auf ein lokales Dateisystem haben. Es wäre sehr schwierig, die Protokolle von einem Benutzer oder einer Sitzung über diese vielen Dienste und Computer hinweg zu korrelieren.

![Protokollieren von lokalen Dateien in einer-Webdienst-app. ](./media/local-log-file-per-service.png)
 **Abbildung 7-3**. Protokollieren von lokalen Dateien in einer-Webdienst-app.

Zum Schluss ist die Anzahl der Benutzer in einigen cloudbasierten Anwendungen hoch. Stellen Sie sich vor, dass jeder Benutzer bei der Anmeldung bei einer Anwendung hundert Zeilen mit Protokollnachrichten generiert. In der Isolation ist das zwar verwaltbar, aber es werden mehr als 100.000 Benutzer multipliziert, und die Menge der Protokolle wird so groß, dass spezialisierte Tools zur Unterstützung der effektiven Verwendung der Protokolle benötigt werden.

### <a name="logging-in-cloud-native-applications"></a>Protokollierung in Cloud-native Anwendungen

Jede Programmiersprache verfügt über Tools, die das Schreiben von Protokollen erlauben, und in der Regel ist der Aufwand für das Schreiben dieser Protokolle gering. Viele der Protokollierungs Bibliotheken ermöglichen das Protokollieren verschiedener Arten von criticalities, die zur Laufzeit optimiert werden können. Die [Bibliothek "serilog](https://serilog.net/) " ist beispielsweise eine beliebte strukturierte Protokollierungs Bibliothek für .net, die die folgenden Protokolliergrade bereitstellt:

* Ausführlich
* Debuggen
* Information
* Warnung
* Fehler
* FAT

Diese verschiedenen Protokoll Ebenen bieten Granularität bei der Protokollierung. Wenn die Anwendung in der Produktionsumgebung ordnungsgemäß funktioniert, kann Sie so konfiguriert werden, dass nur wichtige Nachrichten protokolliert werden. Wenn sich die Anwendung nicht verhält, kann die Protokollebene erweitert werden, sodass ausführlichere Protokolle gesammelt werden. Dadurch wird die Leistung gegenüber dem einfachen Debuggen ausgeglichen.

Dank der hohen Leistung der Protokollierungs Tools und der Anpassbarkeit der Ausführlichkeit sollten Entwickler sich häufig anmelden. Viele bevorzugen ein Muster für das Protokollieren des Eintrags und Beendigungs der einzelnen Methoden. Diese Vorgehensweise mag wie bei Overkill klingen, aber es ist selten, dass Entwickler weniger protokollieren möchten. Tatsächlich ist es nicht ungewöhnlich, bereit Stellungen ausschließlich für das Hinzufügen von Protokollierung um eine problematische Methode auszuführen. Irren Sie sich auf der Seite der zu großen Protokollierung, nicht auf zu wenig. Einige Tools können verwendet werden, um diese Art der Protokollierung automatisch bereitzustellen.

Aufgrund der Herausforderungen im Zusammenhang mit der Verwendung Datei basierter Protokolle in Cloud-Native apps werden zentralisierte Protokolle bevorzugt. Protokolle werden von den Anwendungen gesammelt und an eine zentrale Protokollierungs Anwendung geliefert, die die Protokolle indiziert und speichert. Diese System Klasse kann täglich zehn Gigabyte an Protokollen erfassen.

Es ist auch hilfreich, einige Standardverfahren zu befolgen, wenn Sie die Protokollierung entwickeln, die viele Dienste umfasst. Wenn Sie beispielsweise eine [Korrelations-ID](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) zu Beginn einer langen Interaktion erstellen und diese dann in jeder Nachricht protokollieren, die mit dieser Interaktion verknüpft ist, ist es einfacher, nach allen zugehörigen Nachrichten zu suchen. Sie müssen nur eine einzelne Nachricht suchen und die Korrelations-ID extrahieren, um alle zugehörigen Nachrichten zu finden. Ein weiteres Beispiel ist die Sicherstellung, dass das Protokoll Format für jeden Dienst identisch ist, und zwar ungeachtet der verwendeten Sprache oder Protokollierungs Bibliothek. Diese Standardisierung erleichtert das Lesen von Protokollen. In Abbildung 7-4 wird veranschaulicht, wie eine microservicesarchitektur die zentralisierte Protokollierung als Teil des Workflows nutzen kann.

![Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen. ](./media/centralized-logging.png)
 **Abbildung 7-4**. Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen.

## <a name="challenges-with-detecting-and-responding-to-potential-app-health-issues"></a>Herausforderungen beim erkennen und reagieren auf potenzielle Probleme mit der APP-Integrität

Einige Anwendungen sind nicht Unternehmens kritisch. Vielleicht werden Sie nur intern verwendet, und wenn ein Problem auftritt, kann der Benutzer das verantwortliche Team kontaktieren, und die Anwendung kann neu gestartet werden. Kunden haben jedoch häufig höhere Erwartungen an die Anwendungen, die Sie nutzen. Sie sollten wissen, wann Probleme mit Ihrer Anwendung auftreten, *bevor* Benutzer dies tun, oder bevor Sie von Benutzern benachrichtigt werden. Andernfalls können Sie über ein Problem informiert sein, wenn Sie eine wütende Überschwemmung von Social Media-Beiträgen erkennen, die Ihre Anwendung oder sogar Ihre Organisation verfällt.

Einige Szenarien, die Sie möglicherweise berücksichtigen müssen, sind:

- Ein Dienst in der Anwendung führt zu einem Fehler und Neustarten, was zu zeitweiligen langsamen Antworten führt.
- Zu manchen tageszeiten ist die Reaktionszeit Ihrer Anwendung langsam.
- Nach einer kürzlich Bereitstellung wurde die Last in der Datenbank verdreifacht.

Wenn die Überwachung ordnungsgemäß implementiert ist, können Sie über die Bedingungen informiert werden, die zu Problemen führen. Dadurch können Sie zugrunde liegende Bedingungen beheben, bevor Sie zu erheblichen Auswirkungen auf das Benutzer Ergebnis führen.

### <a name="monitoring-cloud-native-apps"></a>Überwachen von Cloud-Native apps

Einige zentralisierte Protokollierungs Systeme erfordern eine zusätzliche Rolle beim Sammeln von Telemetriedaten außerhalb von reinen Protokollen. Sie können Metriken erfassen, wie z. b. Zeit zum Ausführen einer Datenbankabfrage, durchschnittliche Reaktionszeit eines Webservers und sogar CPU-Auslastung durch Mittelwerte und Arbeitsspeicher Auslastung, wie vom Betriebssystem gemeldet. In Verbindung mit den Protokollen können diese Systeme eine ganzheitliche Ansicht der Integrität der Knoten im System und der Anwendung als Ganzes bereitstellen.

Die Funktionen für die metrikerfassung der Überwachungstools können auch manuell in der Anwendung zusammengeführt werden. Geschäftliche Abläufe, die von besonderem Interesse sind, wie z. b. neue Benutzer, die sich registrieren oder Aufträge platzieren, können so instrumentiert werden, dass Sie einen Gegenstand im zentralen Überwachungssystem erhöhen. Dadurch werden die Überwachungstools entsperrt, um nicht nur die Integrität der Anwendung, sondern die Integrität des Unternehmens zu überwachen.

Abfragen können in den Protokoll Aggregations Tools erstellt werden, um nach bestimmten Statistiken oder Mustern zu suchen, die dann in grafischer Form auf benutzerdefinierten Dashboards angezeigt werden können. Häufig investieren Teams in große, an der Wand eingebundene anzeigen, die sich durch die Statistiken für eine Anwendung drehen. Auf diese Weise ist es einfach, die Probleme zu erkennen, sobald sie auftreten.

Cloud-Native Überwachungstools bieten Echt Zeit Telemetrie und Einblicke in apps, unabhängig davon, ob es sich um prozessübergreifende monolithische Anwendungen oder verteilte microservicearchitekturen handelt. Zu diesen Tools gehören Tools, die das Sammeln von Daten aus der APP sowie Tools zum Abfragen und Anzeigen von Informationen über die Integrität der APP ermöglichen.

## <a name="challenges-with-reacting-to-critical-problems-in-cloud-native-apps"></a>Herausforderungen bei der Reaktion auf kritische Probleme in Cloud-Native apps

Wenn Sie auf Probleme mit Ihrer Anwendung reagieren müssen, benötigen Sie eine Möglichkeit, die richtigen Mitarbeiter zu benachrichtigen. Dies ist das dritte in der Cloud Native Anwendungs Wahrnehmbarkeit-Muster und hängt von der Protokollierung und Überwachung ab. Die Anwendung muss über eine Protokollierung verfügen, damit Probleme diagnostiziert werden können, und in einigen Fällen müssen Sie in die Überwachungstools einfließen. Es muss überwacht werden, um anwendungsmetriken und Integritäts Daten an einem Ort zusammenzufassen. Nachdem dies festgelegt wurde, können Regeln erstellt werden, mit denen Warnungen ausgelöst werden, wenn bestimmte Metriken außerhalb der zulässigen Werte liegen.

Im Allgemeinen werden Warnungen oberhalb der Überwachung angeordnet, sodass bestimmte Bedingungen geeignete Warnungen lösen, um Teammitglieder über dringende Probleme zu benachrichtigen. Einige Szenarien, die möglicherweise Warnungen erfordern, sind:

- Einer der Dienste Ihrer Anwendung reagiert nicht nach einer Ausfallzeit von einer Minute.
- Ihre Anwendung gibt nicht erfolgreiche HTTP-Antworten an mehr als 1% der Anforderungen zurück.
- Die durchschnittliche Antwortzeit Ihrer Anwendung für Schlüssel Endpunkte überschreitet 2000 ms.

### <a name="alerts-in-cloud-native-apps"></a>Warnungen in Cloud-Native apps

Sie können Abfragen für die Überwachungstools erstellen, um nach bekannten Fehlerbedingungen zu suchen. Abfragen können beispielsweise die eingehenden Protokolle nach Hinweisen zum HTTP-Statuscode 500 durchsuchen, was auf ein Problem auf einem Webserver hinweist. Sobald eine dieser Informationen erkannt wird, könnte eine e-Mail oder eine SMS an den Besitzer des Ursprungs dienstanders gesendet werden, der mit der Untersuchung beginnen kann.

In der Regel reicht ein einzelner 500-Fehler jedoch nicht aus, um zu ermitteln, ob ein Problem aufgetreten ist. Dies könnte bedeuten, dass ein Benutzer sein Kennwort falsch eingegeben oder falsch formatierte Daten eingegeben hat. Die Warnungs Abfragen können so gestaltet werden, dass Sie nur ausgelöst werden, wenn eine höhere Anzahl von 500 Fehlern erkannt wird.

Eines der schädlichsten Muster bei der Warnung ist, dass zu viele Warnungen ausgelöst werden, damit die Menschen untersucht werden können. Dienst Besitzer werden schnell zu Fehlern, die Sie zuvor untersucht haben und als harmlos eingestuft werden. Wenn dann echte Fehler auftreten, gehen Sie beim Rauschen von Hunderten falsch positiven Ergebnissen verloren. Das Gleichnis der Person [, die Wolf ausgerufen](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) hat, wird häufig untergeordneten Elementen mitgeteilt, dass Sie von dieser großen Gefahr gewarnt werden. Es ist wichtig sicherzustellen, dass die Warnungen, die ausgelöst werden, auf ein echtes Problem hindeuten.

>[!div class="step-by-step"]
>[Zurück](monitoring-health.md)
>[Weiter](logging-with-elastic-stack.md)
