---
title: Elasticsearch in Cloud-native Anwendungen
description: Erfahren Sie mehr über das Hinzufügen elastischer Suchfunktionen zu cloudbasierten Anwendungen.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: e956f28877d88ce5279944964a877efc324918b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614083"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="1beee-103">Elasticsearch in einer cloudbasierten App</span><span class="sxs-lookup"><span data-stu-id="1beee-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="1beee-104">Elasticsearch ist ein verteiltes Such-und Analysesystem, das komplexe Suchfunktionen über verschiedene Datentypen hinweg ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1beee-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="1beee-105">Es ist Open Source und häufig beliebt.</span><span class="sxs-lookup"><span data-stu-id="1beee-105">It's open source and widely popular.</span></span> <span data-ttu-id="1beee-106">Berücksichtigen Sie, wie die folgenden Unternehmen elasticsearch in Ihre Anwendung integrieren:</span><span class="sxs-lookup"><span data-stu-id="1beee-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="1beee-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) für Volltext und inkrementell (suchen Sie nach dem Typ) suchen.</span><span class="sxs-lookup"><span data-stu-id="1beee-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="1beee-108">[GitHub](https://www.elastic.co/customers/github) für die Indizierung und Bereitstellung über 8 Millionen Coderepositorys.</span><span class="sxs-lookup"><span data-stu-id="1beee-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="1beee-109">[Docker](https://www.elastic.co/customers/docker) , um die Container Bibliothek sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="1beee-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="1beee-110">Elasticsearch basiert auf der [Apache Lucene](https://lucene.apache.org/core/) -Volltext-Suchmaschine.</span><span class="sxs-lookup"><span data-stu-id="1beee-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="1beee-111">Lucene bietet eine hochleistungsfähige Dokument Indizierung und-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1beee-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="1beee-112">Die Daten werden mit einem umgekehrten Indizierungs Schema indiziert – anstatt Seiten zu Schlüsselwörtern zu zuordnen, werden Schlüsselwörter auf Seiten wie ein Glossar am Ende eines Buchs zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1beee-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="1beee-113">Lucene bietet leistungsstarke Funktionen für die Abfrage Syntax und kann Daten nach folgenden Abfragen Abfragen:</span><span class="sxs-lookup"><span data-stu-id="1beee-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="1beee-114">Begriff (ein vollständiges Wort)</span><span class="sxs-lookup"><span data-stu-id="1beee-114">Term (a full word)</span></span>
- <span data-ttu-id="1beee-115">Prefix (beginnt mit Word)</span><span class="sxs-lookup"><span data-stu-id="1beee-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="1beee-116">Platzhalter Zeichen (mithilfe von " \* "-oder "?"-Filtern)</span><span class="sxs-lookup"><span data-stu-id="1beee-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="1beee-117">Ausdruck (eine Sequenz von Text in einem Dokument)</span><span class="sxs-lookup"><span data-stu-id="1beee-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="1beee-118">Boolescher Wert (komplexe Suchvorgänge, die Abfragen kombinieren)</span><span class="sxs-lookup"><span data-stu-id="1beee-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="1beee-119">Während Lucene auf niedriger Ebene für die Suche sorgt, bietet elasticsearch den Server, der auf Lucene basiert.</span><span class="sxs-lookup"><span data-stu-id="1beee-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="1beee-120">Elasticsearch bietet Funktionen höherer Ebene, um das Arbeiten mit Lucene zu vereinfachen, einschließlich einer Rest-API für den Zugriff auf die Indizierungs-und Suchfunktionen von lucene.</span><span class="sxs-lookup"><span data-stu-id="1beee-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="1beee-121">Außerdem wird eine verteilte Infrastruktur bereitgestellt, die eine enorme Skalierbarkeit, Fehlertoleranz und hohe Verfügbarkeit bietet.</span><span class="sxs-lookup"><span data-stu-id="1beee-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="1beee-122">Für größere Native cloudanwendungen mit komplexen Suchanforderungen ist elasticsearch als verwalteter Dienst in Azure verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1beee-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="1beee-123">Der Microsoft Azure Marketplace bietet vorkonfigurierte Vorlagen, die Entwickler verwenden können, um einen elasticsearch-Cluster in Azure bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1beee-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="1beee-124">Aus dem Microsoft Azure Marketplace können Entwickler vorkonfigurierte Vorlagen verwenden, die für die schnelle Bereitstellung eines elasticsearch-Clusters in Azure entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="1beee-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="1beee-125">Mit dem von Azure verwalteten Angebot können Sie bis zu 50 Datenknoten, 20 koordinierende Knoten und drei dedizierte Master Knoten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1beee-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="1beee-126">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1beee-126">Summary</span></span>

<span data-ttu-id="1beee-127">In diesem Kapitel wurde eine ausführliche Betrachtung der Daten in Cloud-Native-Systemen vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="1beee-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="1beee-128">Wir haben damit begonnen, Datenspeicherung in monolithischen Anwendungen mit Daten Speicherungs Mustern in cloudbasierten Systemen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="1beee-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="1beee-129">Wir haben uns mit Datenmustern beschäftigt, die in cloudbasierten Systemen implementiert sind, einschließlich Dienst übergreifender Abfragen, verteilter Transaktionen und Mustern zum Umgang mit Systemen mit hohem Volumen.</span><span class="sxs-lookup"><span data-stu-id="1beee-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="1beee-130">Wir haben gegen SQL mit nosql-Daten verglichen.</span><span class="sxs-lookup"><span data-stu-id="1beee-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="1beee-131">Wir haben uns mit den in Azure verfügbaren Datenspeicher Optionen beschäftigt, die sowohl Microsoft-zentrierte als auch Open-Source-Optionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1beee-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="1beee-132">Schließlich haben wir das Caching und elasticsearch in einer Cloud-native Anwendung erläutert.</span><span class="sxs-lookup"><span data-stu-id="1beee-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="1beee-133">Referenzen</span><span class="sxs-lookup"><span data-stu-id="1beee-133">References</span></span>

- [<span data-ttu-id="1beee-134">Muster „CQRS“ (Command and Query Responsibility Segregation)</span><span class="sxs-lookup"><span data-stu-id="1beee-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="1beee-135">Muster für Ereignis Beschaffung</span><span class="sxs-lookup"><span data-stu-id="1beee-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="1beee-136">Warum ist RDBMS im Cap-Theorem nicht tolerant und warum ist es verfügbar?</span><span class="sxs-lookup"><span data-stu-id="1beee-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="1beee-137">Materialisierte Sicht</span><span class="sxs-lookup"><span data-stu-id="1beee-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="1beee-138">Alles, was Sie wirklich über Open Source-Datenbanken wissen müssen</span><span class="sxs-lookup"><span data-stu-id="1beee-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="1beee-139">Muster „Kompensierende Transaktion“</span><span class="sxs-lookup"><span data-stu-id="1beee-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="1beee-140">Saga-Muster</span><span class="sxs-lookup"><span data-stu-id="1beee-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="1beee-141">Saga-Muster | Implementieren von Geschäftstransaktionen mithilfe von microservices</span><span class="sxs-lookup"><span data-stu-id="1beee-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="1beee-142">Muster „Kompensierende Transaktion“</span><span class="sxs-lookup"><span data-stu-id="1beee-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="1beee-143">Die folgenden 9-Ball-Cosmos DB Konsistenz Ebenen werden näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="1beee-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="1beee-144">Untersuchen der verschiedenen Typen von nosql-Datenbanken Teil II</span><span class="sxs-lookup"><span data-stu-id="1beee-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="1beee-145">Auf RDBMS-, nosql-und newsql-Datenbanken. Interview mit John Ryan</span><span class="sxs-lookup"><span data-stu-id="1beee-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="1beee-146">SQL vs nosql im Vergleich zu newsql: vollständiger Vergleich</span><span class="sxs-lookup"><span data-stu-id="1beee-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="1beee-147">Bindestrich: vier Eigenschaften von Kubernetes-systemeigenen Datenbanken</span><span class="sxs-lookup"><span data-stu-id="1beee-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="1beee-148">Cockroachdb</span><span class="sxs-lookup"><span data-stu-id="1beee-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="1beee-149">Tidb</span><span class="sxs-lookup"><span data-stu-id="1beee-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="1beee-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="1beee-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="1beee-151">Nicht mehr</span><span class="sxs-lookup"><span data-stu-id="1beee-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="1beee-152">Elasticsearch: The Definitive Guide (Elasticsearch: Die ultimative Anleitung)</span><span class="sxs-lookup"><span data-stu-id="1beee-152">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="1beee-153">Einführung in Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="1beee-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="1beee-154">[Zurück](azure-caching.md)
>[Weiter](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="1beee-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
