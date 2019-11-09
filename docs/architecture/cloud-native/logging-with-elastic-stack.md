---
title: Protokollierung mit Elastic Stack
description: Protokollierung mithilfe von Elastic Stack, logstash und kibana
ms.date: 09/23/2019
ms.openlocfilehash: 989834925bc08541bf484e1a4567a56ac324872f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841738"
---
# <a name="logging-with-elastic-stack"></a>Protokollierung mit Elastic Stack

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Es gibt viele gute zentralisierte Protokollierungs Tools, die sich von kostenlosen Open Source-Tools bis hin zu kostspieligen Optionen unterscheiden. In vielen Fällen sind die kostenlosen Tools so gut wie die kostenpflichtigen Angebote. Ein solches Tool ist eine Kombination aus drei Open Source-Komponenten: Elastic Search, logstash und kibana.
Gemeinsam werden diese Tools als elastischer Stapel oder Elk-Stapel bezeichnet.

## <a name="what-are-the-advantages-of-elastic-stack"></a>Was sind die Vorteile von Elastic Stack?

Elastischer Stapel ermöglicht die zentralisierte Protokollierung in kostengünstiger, skalierbarer und cloudfreundlicher Weise. Mit der Benutzeroberfläche wird die Datenanalyse optimiert, sodass Sie sich mit der Verwendung von Erkenntnissen aus Ihren Daten beschäftigen können, anstatt mit einer umständlich-Schnittstelle zu kämpfen. Es unterstützt eine Vielzahl von Eingaben, sodass Sie in der Lage sind, Protokoll-und Metrikdaten weiterhin in das System zu übertragen, wenn die verteilte Anwendung mehr und unterschiedliche Dienste umfasst. Der elastische Stapel unterstützt auch schnelle Suchvorgänge, auch über große Datasets hinweg, sodass es auch für große Anwendungen möglich ist, ausführliche Daten zu protokollieren und dennoch in der Lage zu sein, ihn in einer leistungsfähigen Weise sichtbar zu machen.

## <a name="logstash"></a>Logstash

Die erste Komponente ist " [logstash](https://www.elastic.co/products/logstash)". Dieses Tool wird zum Erfassen von Protokollinformationen aus einer Vielzahl von verschiedenen Quellen verwendet. Logstash kann z. b. Protokolle von einem Datenträger lesen und auch Nachrichten aus Protokollierungs Bibliotheken wie [serilog](https://serilog.net/)empfangen. Logstash kann einige grundlegende Filter und Erweiterungen für die Protokolle ausführen, sobald sie eintreffen. Wenn Ihre Protokolle beispielsweise IP-Adressen enthalten, kann logstash so konfiguriert werden, dass eine geografische Suche durchführen und ein Land oder sogar eine Ursprungs Stadt für diese Nachricht abgerufen wird.

Serilog ist eine Protokollierungs Bibliothek für .NET-Sprachen, die eine parametrisierte Protokollierung ermöglicht. Anstatt eine Text Protokollmeldung zu erzeugen, die Felder einbettet, werden die Parameter getrennt aufbewahrt. Dies ermöglicht eine intelligentere Filterung und Suche. In Abbildung 7-2 wird eine Beispielkonfiguration für das serilog zum Schreiben in logstash angezeigt.

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

**Abbildung 7-2** Serilog-Konfiguration zum direkten Schreiben von Protokollinformationen in logstash über http

Logstash würde eine Konfiguration verwenden, die wie in Abbildung 7-3 dargestellt ist.

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

**Abbildung 7-3** : eine logstash-Konfiguration zum Verarbeiten von Protokollen aus serilog

Für Szenarien, in denen eine umfangreiche Protokoll Bearbeitung nicht erforderlich ist, gibt es eine Alternative zu logstash, die als [Beats](https://www.elastic.co/products/beats)bezeichnet wird Beats ist eine Reihe von Tools, die eine Vielzahl von Daten aus Protokollen zu Netzwerkdaten und Betriebszeit Informationen sammeln können. Viele Anwendungen verwenden logstash und Beats.

Nachdem die Protokolle von logstash erfasst wurden, müssen Sie an einem Ort abgelegt werden. Obwohl logstash viele verschiedene Ausgaben unterstützt, ist eine der aufregendsten bei der elastischen Suche.

## <a name="elastic-search"></a>Elastische Suche

Bei der elastischen Suche handelt es sich um ein leistungsfähiges Suchmodul, das Protokolle nach dem Eintreffen indizieren kann Dadurch wird das Ausführen von Abfragen für die Protokolle schnell. Bei der elastischen Suche können große Mengen von Protokollen verarbeitet und in Extremfällen auf viele Knoten horizontal hochskaliert werden.

Protokollmeldungen, die so erstellt wurden, dass Sie Parameter enthalten oder über Parameter verfügen, die durch die logstash-Verarbeitung voneinander getrennt wurden, können direkt abgefragt werden, da elasticsearch diese Informationen beibehält.

Eine Abfrage, die nach den ersten 10 Seiten sucht, die von `jill@example.com`besucht werden, wird in Abbildung 7-4 angezeigt.

```
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

**Abbildung 7-4** : eine elasticsearch-Abfrage zum Suchen der zehn wichtigsten Seiten, die von einem Benutzer besucht werden

## <a name="visualizing-information-with-kibana-web-dashboards"></a>Visualisieren von Informationen mit kibana-webdashboards

Die letzte Komponente des Stapels ist kibana. Mit diesem Tool werden interaktive Visualisierungen in einem Webdashboard bereitgestellt. Dashboards können auch von Benutzern erstellt werden, die nicht technisch sind. Die meisten Daten, die im elasticsearch-Index ansässig sind, können in die kibana-Dashboards eingefügt werden. Einzelne Benutzer haben möglicherweise unterschiedliche Dashboardansichten, und kibana ermöglicht diese Anpassung durch das zulassen Benutzer spezifischer Dashboards.

## <a name="installing-elastic-stack-on-azure"></a>Installieren des elastischen Stapels in Azure

Der elastische Stapel kann auf verschiedene Weise auf Azure installiert werden. Wie immer ist es möglich, [virtuelle Computer bereitzustellen und elastischen Stapel direkt auf Ihnen zu installieren](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch). Diese Option wird von einigen erfahrenen Benutzern bevorzugt, da Sie den höchsten Grad an Anpassungsmöglichkeiten bietet. Durch die Bereitstellung von Infrastructure-as-a-Service wird ein erheblicher Verwaltungsaufwand eingeführt, bei dem die Mitarbeiter, die diesen Weg nehmen, den Besitz aller Aufgaben übernehmen, die mit der Infrastruktur als Dienst verbunden sind, z. b. das Sichern der Computer und das aktuelle aufbewahren

Eine Option mit weniger Aufwand besteht darin, einen der vielen docker-Container zu verwenden, auf denen der elastische Stapel bereits konfiguriert wurde. Diese Container können in einem vorhandenen Kubernetes-Cluster abgelegt und neben Anwendungscode ausgeführt werden. Der Container [sebp/Elk](https://elk-docker.readthedocs.io/) ist ein gut dokumentierter und getesteter Container für elastische Datenbanken.

Eine andere Möglichkeit ist ein [kürzlich kündigter Elk-as-a-Service-Angebot](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).

## <a name="references"></a>Verweise

- [Installieren des elastischen Stapels in Azure](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
>[Zurück](observability-patterns.md)
>[Weiter](monitoring-azure-kubernetes.md)
