---
title: Beobachtbarkeitsmuster
description: Observability-Muster für Native Cloud-Anwendungen
ms.date: 09/23/2019
ms.openlocfilehash: 23320144c03278d631b8a1fcc1d1c0954e907296
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841066"
---
# <a name="observability-patterns"></a>Beobachtbarkeitsmuster

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Ebenso wie Muster entwickelt wurden, um das Layout von Code in Anwendungen zu unterstützen, gibt es auf zuverlässige Weise Muster für Betriebs Anwendungen. Bei der Verwaltung von Anwendungen sind drei nützliche Muster aufgetreten: Protokollierung, Überwachung und Warnungen.

## <a name="when-to-use-logging"></a>Verwendungszwecke der Protokollierung

Unabhängig davon, wie sorgfältig wir sind, Verhalten sich Anwendungen fast immer auf unerwartete Weise in der Produktionsumgebung. Wenn Benutzer Probleme mit einer Anwendung melden, ist es äußerst nützlich, wenn Sie sehen können, was mit der APP passiert ist, als das Problem aufgetreten ist. Eine der bewährten Methoden zum Erfassen von Informationen darüber, was eine Anwendung während der Ausführung tut, besteht darin, die Anwendung zu schreiben, was Sie tut. Dieser Prozess wird als Protokollierung bezeichnet. Immer wenn Ausfälle oder Probleme in der Produktion auftreten, sollte das Ziel darin bestehen, die Bedingungen, unter denen die Ausfälle aufgetreten sind, in einer nicht-Produktionsumgebung zu reproduzieren. Eine gute Protokollierung ist eine Roadmap für Entwickler, die Sie befolgen können, um Probleme in einer Umgebung zu duplizieren, die Sie testen und experimentieren können.

### <a name="logging-in-cloud-native-applications"></a>Protokollierung in Cloud-native Anwendungen

Jede Programmiersprache verfügt über Tools, die das Schreiben von Protokollen erlauben, und in der Regel ist der Aufwand für das Schreiben dieser Protokolle gering. Viele der Protokollierungs Bibliotheken ermöglichen das Protokollieren verschiedener Arten von criticalities, die zur Laufzeit optimiert werden können. Die Bibliothek "serilog" ist beispielsweise eine beliebte strukturierte Protokollierungs Bibliothek für .net, die die folgenden Protokolliergrade bereitstellt.

* Ausführlich
* Debug
* Information
* Warnung
* Fehler
* FAT

Diese verschiedenen Protokoll Ebenen bieten Granularität bei der Protokollierung. Wenn die Anwendung in der Produktionsumgebung ordnungsgemäß funktioniert, kann Sie so konfiguriert werden, dass nur wichtige Nachrichten protokolliert werden. Wenn sich die Anwendung nicht verhält, kann die Protokollebene erweitert werden, sodass ausführlichere Protokolle gesammelt werden. Dadurch wird die Leistung gegenüber dem einfachen Debuggen ausgeglichen.

Dank der hohen Leistung der Protokollierungs Tools und der Anpassbarkeit der Ausführlichkeit sollten Entwickler sich häufig anmelden. Viele bevorzugen ein Muster für das Protokollieren des Eintrags und Beendigungs der einzelnen Methoden. Diese Vorgehensweise mag wie bei Overkill klingen, aber es ist selten, dass Entwickler weniger protokollieren möchten. Tatsächlich ist es nicht ungewöhnlich, bereit Stellungen ausschließlich für das Hinzufügen von Protokollierung um eine problematische Methode auszuführen. Irren Sie sich auf der Seite der zu großen Protokollierung, nicht auf zu wenig. Beachten Sie, dass einige Tools verwendet werden können, um diese Art der Protokollierung automatisch bereitzustellen.

In herkömmlichen Anwendungen wurden Protokolldateien in der Regel auf dem lokalen Computer gespeichert. Tatsächlich gibt es auf Unix-ähnlichen Betriebssystemen eine Ordnerstruktur, die für alle Protokolle definiert ist, in der Regel unter `/var/log`. Die Nützlichkeit der Protokollierung in einer Flatfile auf einem einzelnen Computer wird in einer cloudumgebung erheblich reduziert. Anwendungen, die Protokolle erstellen, haben möglicherweise keinen Zugriff auf den lokalen Datenträger, oder der lokale Datenträger ist möglicherweise sehr vorübergehend, da Container durch physische Computer gemischt werden.

Cloud native-Anwendungen, die mit einer microservicearchitektur entwickelt wurden, stellen auch einige Herausforderungen bei dateibasierten Protokollierungen dar. Benutzer Anforderungen können sich nun über mehrere Dienste erstrecken, die auf unterschiedlichen Computern ausgeführt werden und Server lose Funktionen enthalten, die keinen Zugriff auf ein lokales Dateisystem haben. Es wäre sehr schwierig, die Protokolle von einem Benutzer oder einer Sitzung über diese vielen Dienste und Computer hinweg zu korrelieren.

Zum Schluss ist die Anzahl der Benutzer in einigen cloudbasierten Anwendungen hoch. Stellen Sie sich vor, dass jeder Benutzer bei der Anmeldung bei einer Anwendung hundert Zeilen mit Protokollnachrichten generiert. In der Isolation ist das zwar verwaltbar, aber es werden mehr als 100.000 Benutzer multipliziert, und die Menge der Protokolle wird zu groß.

Glücklicherweise gibt es einige fantastische Alternativen zur Verwendung der Dateisystem basierten Protokollierung. Ein zentralisierter Protokollserver, an den alle Protokolle gesendet werden, behebt alle diese Probleme. Protokolle werden von den Anwendungen gesammelt und an eine zentrale Protokollierungs Anwendung geliefert, die die Protokolle indiziert und speichert. Diese System Klasse kann täglich zehn Gigabyte an Protokollen erfassen.

Es ist auch hilfreich, einige Standardverfahren zu befolgen, wenn Sie die Protokollierung entwickeln, die viele Dienste umfasst. Wenn Sie beispielsweise eine [Korrelations-ID](https://blog.rapid7.com/2016/12/23/the-value-of-correlation-ids/) zu Beginn einer langen Interaktion erstellen und diese dann in jeder Nachricht protokollieren, die mit dieser Interaktion verknüpft ist, ist es einfacher, nach allen zugehörigen Nachrichten zu suchen. Sie müssen nur eine einzelne Nachricht suchen und die Korrelations-ID extrahieren, um alle zugehörigen Nachrichten zu finden. Ein weiteres Beispiel ist die Sicherstellung, dass das Protokoll Format für jeden Dienst identisch ist, und zwar ungeachtet der verwendeten Sprache oder Protokollierungs Bibliothek. Diese Standardisierung erleichtert das Lesen von Protokollen. In Abbildung 7-1 wird veranschaulicht, wie eine microservicesarchitektur die zentralisierte Protokollierung als Teil des Workflows nutzen kann.

![Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen.](./media/centralized-logging.png)
**Abbildung 7-1**. Protokolle aus verschiedenen Quellen werden in einen zentralisierten Protokoll Speicher aufgenommen.

## <a name="when-to-use-monitoring"></a>Verwendungszwecke der Überwachung

Einige Anwendungen sind nicht Unternehmens kritisch. Vielleicht werden Sie nur intern verwendet, und wenn ein Problem auftritt, kann der Benutzer das verantwortliche Team kontaktieren, und die Anwendung kann neu gestartet werden. Kunden haben jedoch häufig höhere Erwartungen an die Anwendungen, die Sie nutzen. Wenn Sie wissen müssen, wann Probleme mit Ihrer Anwendung auftreten, *bevor* Benutzer dies tun, oder bevor Sie von Benutzern benachrichtigt werden, müssen Sie den aktuellen Status überwachen. Wenn Sie ordnungsgemäß implementiert haben, können Sie über die Überwachung über Bedingungen informiert werden, die zu Problemen führen, sodass Sie die zugrunde liegenden Bedingungen lösen können, bevor Sie zu Benutzer Auswirkungen führen.

## <a name="monitoring-considerations"></a>Überlegungen zur Überwachung

Einige zentralisierte Protokollierungs Systeme erfordern eine zusätzliche Rolle beim Sammeln von Telemetriedaten außerhalb von reinen Protokollen. Sie können Metriken erfassen, wie z. b. Zeit zum Ausführen einer Datenbankabfrage, durchschnittliche Reaktionszeit eines Webservers und sogar CPU-Auslastung durch Mittelwerte und Arbeitsspeicher Auslastung, wie vom Betriebssystem gemeldet. In Verbindung mit den Protokollen können diese Systeme eine ganzheitliche Ansicht der Integrität der Knoten im System und der Anwendung als Ganzes bereitstellen.

Die metriksammungsfunktionen der Überwachungstools können auch manuell in der Anwendung erfasst werden. Geschäftliche Abläufe, die von besonderem Interesse sind, wie z. b. neue Benutzer, die sich registrieren oder Aufträge platzieren, können so instrumentiert werden, dass Sie einen Gegenstand im zentralen Überwachungssystem erhöhen. Dadurch werden die Überwachungstools entsperrt, um nicht nur die Integrität der Anwendung, sondern die Integrität des Unternehmens zu überwachen.

Abfragen können in den Protokoll Aggregations Tools erstellt werden, um nach bestimmten Statistiken oder Mustern zu suchen, die dann in grafischer Form auf benutzerdefinierten Dashboards angezeigt werden können. Häufig investieren Teams in große, an der Wand eingebundene anzeigen, die sich durch die Statistiken für eine Anwendung drehen. Auf diese Weise ist es einfach, die Probleme zu erkennen, sobald sie auftreten.

## <a name="when-to-use-alerts"></a>Verwendungszwecke von Warnungen

Wenn Sie auf Probleme mit Ihrer Anwendung reagieren müssen, benötigen Sie eine Möglichkeit, die richtigen Mitarbeiter zu benachrichtigen. Dies ist das dritte in der Cloud Native Anwendungs Wahrnehmbarkeit-Muster, das von der Protokollierung und Überwachung abhängig ist. Die Anwendung muss über eine Protokollierung verfügen, damit Probleme diagnostiziert werden können, und in einigen Fällen müssen Sie in die Überwachungstools einfließen. Es muss überwacht werden, um anwendungsmetriken und Integritäts Daten an einem Ort zusammenzufassen. Nachdem dies festgelegt wurde, können Regeln erstellt werden, mit denen Warnungen ausgelöst werden, wenn bestimmte Metriken außerhalb der zulässigen Werte liegen.

## <a name="alerts"></a>Benachrichtigungen

Sie können Abfragen für die Überwachungstools erstellen, um nach bekannten Fehlerbedingungen zu suchen. Abfragen können beispielsweise die eingehenden Protokolle nach Hinweisen zum HTTP-Statuscode 500 durchsuchen, was auf ein Problem auf einem Webserver hinweist. Sobald eine dieser Informationen erkannt wird, könnte eine e-Mail oder eine SMS an den Besitzer des Ursprungs dienstanders gesendet werden, der mit der Untersuchung beginnen kann.

In der Regel reicht ein einzelner 500-Fehler nicht aus, um zu ermitteln, dass ein Problem aufgetreten ist. Dies könnte bedeuten, dass ein Benutzer sein Kennwort falsch eingegeben oder falsch formatierte Daten eingegeben hat. Die Warnungs Abfragen können so gestaltet werden, dass Sie nur ausgelöst werden, wenn eine höhere Anzahl von 500 Fehlern erkannt wird.

Eines der schädlichsten Muster bei der Warnung ist, dass zu viele Warnungen ausgelöst werden, damit die Menschen untersucht werden können. Dienst Besitzer werden schnell zu Fehlern, die Sie zuvor untersucht haben und als harmlos eingestuft werden. Wenn echte Fehler auftreten, gehen Sie beim Rauschen von Hunderten falsch positiven Ergebnissen verloren. Das Gleichnis der Person [, die Wolf ausgerufen](https://en.wikipedia.org/wiki/The_Boy_Who_Cried_Wolf) hat, wird häufig untergeordneten Elementen mitgeteilt, dass Sie von dieser großen Gefahr gewarnt werden. Es ist wichtig sicherzustellen, dass die Warnungen, die ausgelöst werden, auf ein echtes Problem hindeuten.

>[!div class="step-by-step"]
>[Zurück](monitoring-health.md)
>[Weiter](logging-with-elastic-stack.md)
