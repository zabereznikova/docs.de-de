---
title: Elasticsearch in Cloud-native Anwendungen
description: Erfahren Sie mehr über das Hinzufügen elastischer Suchfunktionen zu cloudbasierten Anwendungen.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 6ea237eddc89a8c6843d6b34b05b1b71515a99b6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795038"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch in einer cloudbasierten App

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch ist ein verteiltes Such-und Analysesystem, das komplexe Suchfunktionen über verschiedene Datentypen hinweg ermöglicht. Es ist Open Source und häufig beliebt. Berücksichtigen Sie, wie die folgenden Unternehmen elasticsearch in Ihre Anwendung integrieren:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) für Volltext und inkrementell (suchen Sie nach dem Typ) suchen.
- [GitHub](https://www.elastic.co/customers/github) für die Indizierung und Bereitstellung über 8 Millionen Coderepositorys.  
- [Docker](https://www.elastic.co/customers/docker) , um die Container Bibliothek sichtbar zu machen.

Elasticsearch basiert auf der [Apache Lucene](https://lucene.apache.org/core/) -Volltext-Suchmaschine. Lucene bietet eine hochleistungsfähige Dokument Indizierung und-Abfrage. Die Daten werden mit einem umgekehrten Indizierungs Schema indiziert – anstatt Seiten zu Schlüsselwörtern zu zuordnen, werden Schlüsselwörter auf Seiten wie ein Glossar am Ende eines Buchs zugeordnet. Lucene bietet leistungsstarke Funktionen für die Abfrage Syntax und kann Daten nach folgenden Abfragen Abfragen:

- Begriff (ein vollständiges Wort) 
- Prefix (beginnt mit Word)
- Platzhalter (mithilfe von "\*"-oder "?"-Filtern)
- Ausdruck (eine Sequenz von Text in einem Dokument)
- Boolescher Wert (komplexe Suchvorgänge, die Abfragen kombinieren)

Während Lucene auf niedriger Ebene für die Suche sorgt, bietet elasticsearch den Server, der auf Lucene basiert. Elasticsearch bietet Funktionen höherer Ebene, um das Arbeiten mit Lucene zu vereinfachen, einschließlich einer Rest-API für den Zugriff auf die Indizierungs-und Suchfunktionen von lucene. Außerdem wird eine verteilte Infrastruktur bereitgestellt, die eine enorme Skalierbarkeit, Fehlertoleranz und hohe Verfügbarkeit bietet.

Für größere Native cloudanwendungen mit komplexen Suchanforderungen ist elasticsearch als verwalteter Dienst in Azure verfügbar. Der Microsoft Azure Marketplace bietet vorkonfigurierte Vorlagen, die Entwickler verwenden können, um einen elasticsearch-Cluster in Azure bereitzustellen.

Aus dem Microsoft Azure Marketplace können Entwickler vorkonfigurierte Vorlagen verwenden, die für die schnelle Bereitstellung eines elasticsearch-Clusters in Azure entwickelt wurden. Mit dem von Azure verwalteten Angebot können Sie bis zu 50 Datenknoten, 20 koordinierende Knoten und drei dedizierte Master Knoten bereitstellen.

## <a name="summary"></a>Summary

In diesem Kapitel wurde eine ausführliche Betrachtung der Daten in Cloud-Native-Systemen vorgestellt. Wir haben damit begonnen, Datenspeicherung in monolithischen Anwendungen mit Daten Speicherungs Mustern in cloudbasierten Systemen zu vergleichen. Wir haben uns mit Datenmustern beschäftigt, die in cloudbasierten Systemen implementiert sind, einschließlich Dienst übergreifender Abfragen, verteilter Transaktionen und Mustern zum Umgang mit Systemen mit hohem Volumen. Wir haben gegen SQL mit nosql-Daten verglichen. Wir haben uns mit den in Azure verfügbaren Datenspeicher Optionen beschäftigt, die sowohl Microsoft-zentrierte als auch Open-Source-Optionen enthalten. Schließlich haben wir das Caching und elasticsearch in einer Cloud-native Anwendung erläutert.

### <a name="references"></a>Verweise

- [Cqrs-Muster (Command and Query Responsibility Segregation)](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Muster für Ereignis Beschaffung](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [RDBMSs-und nosql-Datenbanken: Übersicht](https://maxivak.com/rdbms-vs-nosql-databases/)

- [Warum ist RDBMS im Cap-Theorem nicht tolerant und warum ist es verfügbar?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Materialisierte Sicht](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Alles, was Sie wirklich über Open Source-Datenbanken wissen müssen](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Muster für kompensierende Transaktionen](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Saga-Muster](https://microservices.io/patterns/data/saga.html)

- [Saga-Muster | Implementieren von Geschäftstransaktionen mithilfe von microservices](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Muster für kompensierende Transaktionen](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Die folgenden 9-Ball-Cosmos DB Konsistenz Ebenen werden näher erläutert.](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Untersuchen der verschiedenen Typen von nosql-Datenbanken Teil II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [Auf RDBMS-, nosql-und newsql-Datenbanken. Interview mit John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs nosql im Vergleich zu newsql: vollständiger Vergleich](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [Bindestrich: vier Eigenschaften von Kubernetes-systemeigenen Datenbanken](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [Cockroachdb](https://www.cockroachlabs.com/)

- [Tidb](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Nicht mehr](https://vitess.io/)

- [Elasticsearch: das definitive Handbuch](http://shop.oreilly.com/product/0636920028505.do)
  
- [Einführung in Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Zurück](azure-caching.md)
>[Weiter](resiliency.md) <!-- Next Chapter -->
