---
title: Elasticsearch in Cloud-nativen Anwendungen
description: Erfahren Sie mehr über das Hinzufügen von Elastic Search-Funktionen zu cloudnativen Anwendungen.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141288"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch in einer Cloud-nativen App

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch ist ein verteiltes Such- und Analysesystem, das komplexe Suchfunktionen für verschiedene Datentypen ermöglicht. Es ist Open Source und sehr beliebt. Überlegen Sie, wie die folgenden Unternehmen Elasticsearch in ihre Anwendung integrieren:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) für Volltext und inkrementelle (Suche während der Eingabe) Suche.
- [GitHub](https://www.elastic.co/customers/github) soll über 8 Millionen Code-Repositorys indizieren und verfügbar machen.  
- [Docker,](https://www.elastic.co/customers/docker) um seine Containerbibliothek auffindbar zu machen.

Elasticsearch basiert auf der [Apache Lucene](https://lucene.apache.org/core/) Volltext-Suchmaschine. Lucene bietet eine leistungsstarke Dokumentindizierung und Abfrage. Es indiziert Daten mit einem invertierten Indizierungsschema – anstatt Seiten Zuschlüsselwörtern zuzuordnen, ordnet es Keywords Seiten wie ein Glossar am Ende eines Buches zu. Lucene verfügt über leistungsstarke Abfragesyntaxfunktionen und kann Daten abfragen durch:

- Begriff (ein vollständiges Wort)
- Präfix (beginnt mit Wort)
- Platzhalter (mit "\*" oder "?" Filter)
- Phrase (eine Textfolge in einem Dokument)
- Boolescher Wert (komplexe Suchvorgänge, die Abfragen kombinieren)

Während Lucene Sanitäranlagen auf niedriger Ebene für die Suche bereitstellt, stellt Elasticsearch den Server bereit, der sich auf Lucene befindet. Elasticsearch fügt Funktionen auf höherer Ebene hinzu, um das Arbeiten von Lucene zu vereinfachen, einschließlich einer RESTful-API für den Zugriff auf die Indizierungs- und Suchfunktionen von Lucene. Darüber hinaus bietet es eine verteilte Infrastruktur, die in der Lage ist, eine enorme Skalierbarkeit, Fehlertoleranz und hohe Verfügbarkeit zu bieten.

Für größere cloudnative Anwendungen mit komplexen Suchanforderungen ist Elasticsearch als managed Service in Azure verfügbar. Microsoft Azure Marketplace enthält vorkonfigurierte Vorlagen, die Entwickler zum Bereitstellen eines Elasticsearch-Clusters in Azure verwenden können.

Im Microsoft Azure Marketplace können Entwickler vorkonfigurierte Vorlagen verwenden, die erstellt wurden, um einen Elasticsearch-Cluster in Azure schnell bereitzustellen. Mithilfe des von Azure verwalteten Angebots können Sie bis zu 50 Datenknoten, 20 koordinierende Knoten und drei dedizierte Masterknoten bereitstellen.

## <a name="summary"></a>Zusammenfassung

In diesem Kapitel wurde ein detaillierter Blick auf Daten in Cloud-nativen Systemen dargestellt. Wir begannen damit, die Datenspeicherung in monolithischen Anwendungen mit Datenspeichermustern in Cloud-nativen Systemen zu kontrastieren. Wir untersuchten Datenmuster, die in Cloud-nativen Systemen implementiert wurden, einschließlich dienstübergreifender Abfragen, verteilter Transaktionen und Muster für systeme mit hohem Volumen. Wir haben SQL mit NoSQL-Daten kontrastiert. Wir haben uns die in Azure verfügbaren Datenspeicheroptionen angesehen, die sowohl Microsoft-zentrierte als auch Open-Source-Optionen enthalten. Schließlich haben wir caching und Elasticsearch in einer Cloud-nativen Anwendung diskutiert.

### <a name="references"></a>References

- [Muster „CQRS“ (Command and Query Responsibility Segregation)](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Event Sourcing-Muster](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [RDBMSs vs. NoSQL-Datenbanken: Übersicht](https://maxivak.com/rdbms-vs-nosql-databases/)

- [Warum ist RDBMS Partition Tolerant in CAP Theorem nicht verfügbar und warum ist es verfügbar?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Materialisierte Sicht](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Alles, was Sie wirklich über Open-Source-Datenbanken wissen müssen](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Muster „Kompensierende Transaktion“](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Saga-Muster](https://microservices.io/patterns/data/saga.html)

- [Saga-Muster | Implementieren von Geschäftstransaktionen mithilfe von Microservices](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Muster „Kompensierende Transaktion“](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Hinter dem 9-Ball: Cosmos DB Consistency Levels erklärt](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Erkunden der verschiedenen Typen von NoSQL-Datenbanken Teil II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [Auf RDBMS-, NoSQL- und NewSQL-Datenbanken. Interview mit John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL vs NewSQL: Der vollständige Vergleich](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: Vier Eigenschaften von Kubernetes-Native-Datenbanken](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [KakerlakeDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Vitess](https://vitess.io/)

- [Elasticsearch: The Definitive Guide (Elasticsearch: Die ultimative Anleitung)](http://shop.oreilly.com/product/0636920028505.do)
  
- [Einführung in Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[VorherigeS](azure-caching.md)
>[Weiter](resiliency.md) <!-- Next Chapter -->
