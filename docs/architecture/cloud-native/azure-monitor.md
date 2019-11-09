---
title: Azure Monitor
description: Die Verwendung von Azure Monitor, um Einblick in Ihr System zu erhalten, wird ausgeführt.
ms.date: 09/23/2019
ms.openlocfilehash: fa7b4e103f4d1245710f88319271a9e8b7a24b04
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841864"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Kein anderer cloudanbieter hat eine Überwachungslösung für cloudanwendungen wie in Azure gefunden. Azure Monitor ist ein namens Name für eine Sammlung von Tools, die entwickelt wurden, um Einblick in den Zustand Ihres Systems zu erhalten, Einblicke in alle Probleme und die Optimierung Ihrer Anwendung.

![Azure Monitor, eine Sammlung von Tools, um Einblick in die Funktionsweise einer cloudbasierten Anwendung zu bieten.](./media/azure-monitor.png)
**Abbildung 7-9**. Azure Monitor eine Sammlung von Tools, um Einblick in die Funktionsweise einer Cloud-native Anwendung zu erhalten.

## <a name="gathering-logs-and-metrics"></a>Sammeln von Protokollen und Metriken

Der erste Schritt einer Überwachungslösung besteht darin, so viele Daten wie möglich zu erfassen. Die mehr Daten, die gesammelt werden können, desto genauer sind die Erkenntnisse, die abgerufen werden können. Instrumentierungssysteme waren traditionell schwierig. Das Simple Network Management-Protokoll (SNMP) war das Gold-Standardprotokoll für die Erfassung von Informationen auf Computer Ebene, erforderte aber sehr viel Wissen und Konfigurierung. Glücklicherweise wurde ein Großteil dieser harte Arbeit beseitigt, da die häufigsten Metriken automatisch von Azure Monitor gesammelt werden.

Metriken und Ereignisse auf Anwendungsebene können nicht automatisch instrumentiert werden, da Sie für die bereitgestellte Anwendung lokal sind. Um diese Metriken zu erfassen, sind [sdken und APIs verfügbar](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) , die diese Informationen direkt melden, z. b. wenn sich ein Kunde anmeldet oder eine Bestellung abschließt. Ausnahmen können auch aufgezeichnet und in Azure Monitor über Application Insights zurückgemeldet werden. Die sdche unterstützen die meisten Sprachen, die in nativen cloudanwendungen enthalten sind, einschließlich go, Python, JavaScript und .NET-Sprachen.

Das Hauptziel der Erfassung von Informationen über den Zustand Ihrer Anwendung besteht darin, sicherzustellen, dass Ihre Endbenutzer eine gute Benutzer Leistung haben. Was ist besser zu erkennen, wenn Benutzer Probleme haben, als [externe Webtests durchzuführen](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)? Diese Tests können so einfach sein wie das Pingen Ihrer Website an den Standorten auf der ganzen Welt oder daran, dass sich Agents bei der Website anmelden und Aktionen ausführen.

## <a name="reporting-data"></a>Berichtsdaten

Sobald die Daten erfasst wurden, können Sie in Diagrammen manipuliert, zusammengefasst und gezeichnet werden, sodass Benutzer sofort erkennen können, wann Probleme aufgetreten sind. Diese Diagramme können in Dashboards oder in Arbeitsmappen gesammelt werden, einem mehrseitigen Bericht, der eine Story über einen Aspekt des Systems informieren soll.

Ohne künstliche Intelligenz oder Maschinelles Lernen wäre keine moderne Anwendung fertiggestellt. Zu diesem Zweck können Daten an die verschiedenen Machine Learning-Tools in Azure über [mittelt werden](https://www.youtube.com/watch?v=Cuza-I1g9tw) , damit Sie Trends und Informationen extrahieren können, die andernfalls ausgeblendet werden.

Application Insights bietet eine leistungsstarke Abfragesprache namens Kusto, mit der Sie Datensätze suchen, zusammenfassen und sogar Diagramme zeichnen können. Diese Abfrage findet beispielsweise alle Datensätze für den Monat November 2007, gruppiert Sie nach Bundesland und zeichnet die ersten 10 als Kreis Diagramm.

```
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![das Ergebnis der Application Insights Abfrage](./media/azure-monitor.png)
**Abbildung 7-10**. Das Ergebnis der Application Insights Abfrage.

Es gibt einen [Spielplatz für das Experimentieren mit Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples) -Abfragen. Dies ist ein idealer Ort, um eine Stunde oder zwei Stunden zu verbringen. Das Lesen von [Beispielabfragen](https://docs.microsoft.com/azure/kusto/query/samples) kann auch aufschlussreich sein.

## <a name="dashboards"></a>Dashboards

Es gibt mehrere verschiedene dashboardtechnologien, die verwendet werden können, um die Informationen aus Azure Monitor zu verwenden. Möglicherweise ist es am einfachsten, einfach Abfragen in Application Insights auszuführen und [die Daten in einem Diagramm zu zeichnen](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards).

![ein Beispiel für Application Insights Diagramme, die in das Azure-Haupt Dashboard eingebettet sind](./media/azure-monitor.png)
**Abbildung 7-11**. Ein Beispiel für Application Insights Diagramme, die im Azure-Haupt Dashboard eingebettet sind.

Diese Diagramme können dann mithilfe der dashboardfunktion in den Azure-Portal eingebettet werden. Für Benutzer mit anspruchsvolleren Anforderungen, z. b. der Möglichkeit, einen Drilldown in mehrere Daten Ebenen durchführen zu können Azure Monitor Daten für [Power BI](https://powerbi.microsoft.com/)verfügbar. Power BI ist eine branchenführende Enterprise-Klasse Business Intelligence Tool, mit dem Daten aus vielen verschiedenen Datenquellen aggregiert werden können.

![ein Beispiel Power BI Dashboard](./media/azure-monitor.png)
**Abbildung 7-12**. Ein Beispiel Power BI-Dashboard.

## <a name="alerts"></a>Benachrichtigungen

Manchmal reicht es nicht aus, Daten Dashboards zu haben. Wenn niemand aktiv ist, um die Dashboards zu beobachten, kann es nach wie vor viele Stunden dauern, bis ein Problem behoben oder sogar erkannt wird. Zu diesem Zweck stellt Azure Monitor auch eine Lösung mit der höchsten [Lösung](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)bereit. Warnungen können durch eine Vielzahl von Bedingungen ausgelöst werden, darunter:

- Metrikwerte
- Protokoll such Abfragen
- Aktivitätsprotokoll Ereignisse
- Integrität der zugrunde liegenden Azure-Plattform
- Tests zur Verfügbarkeit von Websites

Wenn die Warnungen ausgelöst werden, können Sie eine Vielzahl von Tasks ausführen. Auf der einfachen Seite können die Warnungen nur eine e-Mail-Benachrichtigung an eine Mailingliste oder eine Textnachricht an eine Person senden. Weitere Beteiligte Warnungen könnten einen Workflow in einem Tool wie z. b. PagerDuty auslöst, das weiß, wer für eine bestimmte Anwendung aufgerufen wird. Warnungen können Aktionen in [Microsoft Flow](https://flow.microsoft.com/) Auslösung von nahezu unbegrenzten Möglichkeiten für Workflows auslöst.

Da häufig Warnungen identifiziert werden, können die Warnungen mit Details zu den häufigen Ursache der Warnungen und den Schritten zum Beheben der Warnungen erweitert werden. Hoch ausgereifte, Native Cloud-Anwendungs Bereitstellungen können Selbstreparatur Aufgaben ausführen, die Aktionen ausführen, z. b. das Entfernen fehlerhafter Knoten aus einer Skalierungs Gruppe oder das Auslösen einer Aktivität für die automatische Skalierung. Es ist ggf. nicht mehr erforderlich, die Mitarbeiter auf der zweiten Seite zu reaktivieren, um ein Problem mit der Live Site zu beheben, da sich das System in der Lage ist, sich an den nächsten Morgen zu kompensieren oder zumindest an die Arbeit zu richten.

Azure Monitor nutzt Machine Learning automatisch, um die normalen Betriebsparameter von bereitgestellten Anwendungen zu verstehen. Dadurch können Dienste erkannt werden, die außerhalb ihrer normalen Parameter ausgeführt werden. Beispielsweise kann der typische wochentagsdatenverkehr auf der Website 10.000 Anforderungen pro Minute betragen. In einer bestimmten Woche trifft die Anzahl der Anforderungen plötzlich auf sehr ungewöhnliche 20.000-Anforderungen pro Minute. Die [intelligente Erkennung](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) bemerkt diese Abweichung von der Norm und löst eine Warnung aus. Gleichzeitig ist die Trendanalyse intelligent genug, um zu vermeiden, dass falsch positive Ergebnisse ausgelöst werden, wenn die Auslastung des Datenverkehrs erwartet wird.

>[!div class="step-by-step"]
>[Zurück](monitoring-azure-kubernetes.md)
>[Weiter](identity.md)
