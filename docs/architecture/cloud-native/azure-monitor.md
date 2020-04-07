---
title: Azure Monitor
description: Die Verwendung von Azure Monitor, um Einblick in Ihr System zu erhalten, wird ausgeführt.
ms.date: 02/05/2020
ms.openlocfilehash: 4e5ddba6c1c13dc65662a7748d4ae3a58a6a6f68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805632"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Kein anderer Cloudanbieter verfügt über eine so ausgereifte Cloudanwendungsüberwachungslösung wie in Azure. Azure Monitor ist ein Dachname für eine Sammlung von Tools, die einen Einblick in den Status Ihres Systems, Einblicke in Probleme und die Optimierung Ihrer Anwendung bieten.

![Azure Monitor, eine Sammlung von Tools, die Einblicke in die Funktionsweise einer cloudnativen Anwendung bietet. ](./media/azure-monitor.png)
 **Abbildung 7-12**. Azure Monitor, eine Sammlung von Tools, die Einblicke in die Funktionsweise einer cloudnativen Anwendung bietet.

## <a name="gathering-logs-and-metrics"></a>Sammeln von Protokollen und Metriken

Der erste Schritt in jeder Überwachungslösung besteht darin, so viele Daten wie möglich zu sammeln. Je mehr Daten gesammelt werden können, desto tiefer sind die Erkenntnisse, die gewonnen werden können. Instrumentierungssysteme waren traditionell schwierig. Simple Network Management Protocol (SNMP) war das Gold-Standardprotokoll zum Sammeln von Informationen auf Maschinenebene, aber es erforderte viel Wissen und Konfiguration. Glücklicherweise wurde ein Großteil dieser harten Arbeit eliminiert, da die häufigsten Metriken automatisch von Azure Monitor erfasst werden.

Metriken und Ereignisse auf Anwendungsebene können nicht automatisch instrumentiert werden, da sie spezifisch für die bereitgestellte Anwendung sind. Um diese Metriken zu erfassen, stehen [SDKs und APIs zur Verfügung,](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) um solche Informationen direkt zu melden, z. B. wenn sich ein Kunde anmeldet oder eine Bestellung abschließt. Ausnahmen können auch erfasst und über Application Insights wieder an Azure Monitor gemeldet werden. Die SDKs unterstützen die meisten Sprachen in Cloud Native-Anwendungen, einschließlich Go, Python, JavaScript und den .NET-Sprachen.

Das ultimative Ziel, Informationen über den Status Ihrer Anwendung zu sammeln, besteht darin, sicherzustellen, dass Ihre Endbenutzer eine gute Erfahrung haben. Gibt es eine bessere Möglichkeit, um zu erkennen, ob Benutzer Probleme haben, als [externe Webtests](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)durchzuführen? Diese Tests können so einfach sein, wie das Pingen Ihrer Website von Standorten auf der ganzen Welt oder so beteiligt, wie Agenten sich an der Website anmelden und Benutzeraktionen simulieren.

## <a name="reporting-data"></a>Berichtsdaten

Sobald die Daten gesammelt wurden, können sie bearbeitet, zusammengefasst und in Diagramme geplottet werden, sodass Benutzer sofort sehen können, wenn Probleme auftreten. Diese Diagramme können in Dashboards oder in Workbooks gesammelt werden, einem mehrseitigen Bericht, der eine Geschichte über einen Aspekt des Systems erzählen soll.

Keine moderne Anwendung wäre komplett ohne künstliche Intelligenz oder maschinelles Lernen. Zu diesem Zweck können Daten an die verschiedenen Tools zum erlernen den Benutzern in Azure [übergeben werden,](https://www.youtube.com/watch?v=Cuza-I1g9tw) damit Sie Trends und Informationen extrahieren können, die andernfalls ausgeblendet wären.

Application Insights bietet eine leistungsstarke Abfragesprache namens Kusto, die zum Suchen von Datensätzen, Zusammenfassen und sogar Plotdiagrammen verwendet werden kann. Diese Abfrage sucht z. B. alle Datensätze für den Monat November 2007, gruppiert sie nach Status und zeichnet die Top 10 als Kreisdiagramm.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![Das Ergebnis der Application](./media/azure-monitor.png)
Insights Query**Abbildung 7-13**. Das Ergebnis der Application Insights Query.

Es gibt einen [Spielplatz zum Experimentieren mit Kusto-Abfragen,](https://dataexplorer.azure.com/clusters/help/databases/Samples) der ein fantastischer Ort ist, um ein oder zwei Stunden zu verbringen. Das Lesen von [Beispielabfragen](https://docs.microsoft.com/azure/kusto/query/samples) kann auch lehrreich sein.

## <a name="dashboards"></a>Dashboards

Es gibt mehrere verschiedene Dashboardtechnologien, die verwendet werden können, um die Informationen aus Azure Monitor anzuzeigen. Vielleicht ist es am einfachsten, Abfragen in Application Insights auszuführen und [die Daten in einem Diagramm](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)darzustellen.

![Ein Beispiel für Application Insights-Diagramme, die in die Hauptabbildung](./media/azure-monitor.png)
**7-14**des Azure Dashboards eingebettet sind. Ein Beispiel für Application Insights-Diagramme, die in das Azure-Hauptdashboard eingebettet sind.

Diese Diagramme können dann mithilfe der Dashboardfunktion in das eigentliche Azure-Portal eingebettet werden. Für Benutzer mit anspruchsvolleren Anforderungen, z. B. in der Lage, einen Drilldown in mehrere Datenebenen zu führen, stehen Azure Monitor-Daten für [Power BI](https://powerbi.microsoft.com/)zur Verfügung. Power BI ist ein branchenführendes Business Intelligence-Tool der Enterprise-Klasse, das Daten aus vielen verschiedenen Datenquellen aggregieren kann.

![Beispiel Power BI-Dashboard](./media/azure-monitor.png)
Abbildung**7-15**. Ein Beispiel für das Power BI-Dashboard.

## <a name="alerts"></a>Alerts

Manchmal ist es nicht ausreichend, Datendashboards zu haben. Wenn niemand wach ist, um die Dashboards zu beobachten, dann kann es noch viele Stunden dauern, bis ein Problem behoben oder sogar erkannt wird. Zu diesem Zweck bietet Azure Monitor auch eine erstklassige [Warnlösung](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview). Warnungen können durch eine Vielzahl von Bedingungen ausgelöst werden, einschließlich:

- Metrikwerte
- Protokollsuchabfragen
- Aktivitätsprotokollereignisse
- Integrität der zugrunde liegenden Azure-Plattform
- Tests für die Verfügbarkeit von Websites

Wenn die Warnungen ausgelöst werden, können sie eine Vielzahl von Aufgaben ausführen. Auf der einfachen Seite können die Benachrichtigungen nur eine E-Mail-Benachrichtigung an eine Mailingliste oder eine SMS an eine Person senden. Mehr beteiligte Warnungen können einen Workflow in einem Tool wie PagerDuty auslösen, das weiß, wer für eine bestimmte Anwendung auf Abruf ist. Warnungen können Aktionen in [Microsoft Flow](https://flow.microsoft.com/) auslösen, die nahezu unbegrenzte Möglichkeiten für Workflows freischalten.

Wenn häufige Ursachen von Warnungen identifiziert werden, können die Warnungen um Details zu den häufigsten Ursachen der Warnungen und den zu ihrer Behebung zu ihrer Behebung erforderlichen Schritten erweitert werden. Hochausgereifte Cloud-native Anwendungsbereitstellungen können sich dafür entscheiden, Selbstheilungsaufgaben zu starten, die Aktionen ausführen, wie z. B. das Entfernen fehlerhafter Knoten aus einer Skalierungsgruppe oder das Auslösen einer Autoscaling-Aktivität. Schließlich kann es nicht mehr notwendig sein, das Bereitschaftspersonal um 2 Uhr morgens aufzuwecken, um ein Problem mit der Live-Site zu lösen, da das System in der Lage sein wird, sich anzupassen, um zu kompensieren oder zumindest mitzuschleppen, bis jemand am nächsten Morgen bei der Arbeit eintrifft.

Azure Monitor nutzt Machine Learning automatisch, um die normalen Betriebsparameter bereitgestellter Anwendungen zu verstehen. Auf diese Weise kann es Dienste erkennen, die außerhalb ihrer normalen Parameter arbeiten. Beispielsweise kann der typische Wochentagsverkehr auf der Website 10.000 Anforderungen pro Minute betragen. Und dann, in einer bestimmten Woche, plötzlich die Anzahl der Anfragen trifft eine sehr ungewöhnliche 20.000 Anfragen pro Minute. [Smart Detection](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) bemerkt diese Abweichung von der Norm und löst eine Warnung aus. Gleichzeitig ist die Trendanalyse intelligent genug, um zu vermeiden, dass falsche Positivmeldungen ausgelöst werden, wenn die Verkehrslast erwartet wird.

## <a name="references"></a>References

- [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[Zurück](monitoring-azure-kubernetes.md)
>[Weiter](identity.md)
