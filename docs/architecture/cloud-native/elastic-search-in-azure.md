---
title: Elasticsearch in Cloud-nativen Anwendungen
description: Erfahren Sie mehr über das Hinzufügen von Elastic Search-Funktionen zu cloudnativen Anwendungen.
author: robvet
ms.date: 03/02/2020
ms.openlocfilehash: da6b9402cf266f5a298b05cf837805b2377bc75a
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805563"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="5e8dd-103">Elasticsearch in einer Cloud-nativen App</span><span class="sxs-lookup"><span data-stu-id="5e8dd-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="5e8dd-104">Elasticsearch ist ein verteiltes Such- und Analysesystem, das komplexe Suchfunktionen für verschiedene Datentypen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="5e8dd-105">Es ist Open Source und sehr beliebt.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-105">It's open source and widely popular.</span></span> <span data-ttu-id="5e8dd-106">Überlegen Sie, wie die folgenden Unternehmen Elasticsearch in ihre Anwendung integrieren:</span><span class="sxs-lookup"><span data-stu-id="5e8dd-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="5e8dd-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) für Volltext und inkrementelle (Suche während der Eingabe) Suche.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="5e8dd-108">[GitHub](https://www.elastic.co/customers/github) soll über 8 Millionen Code-Repositorys indizieren und verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="5e8dd-109">[Docker,](https://www.elastic.co/customers/docker) um seine Containerbibliothek auffindbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="5e8dd-110">Elasticsearch basiert auf der [Apache Lucene](https://lucene.apache.org/core/) Volltext-Suchmaschine.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="5e8dd-111">Lucene bietet eine leistungsstarke Dokumentindizierung und Abfrage.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="5e8dd-112">Es indiziert Daten mit einem invertierten Indizierungsschema – anstatt Seiten Zuschlüsselwörtern zuzuordnen, ordnet es Keywords Seiten wie ein Glossar am Ende eines Buches zu.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="5e8dd-113">Lucene verfügt über leistungsstarke Abfragesyntaxfunktionen und kann Daten abfragen durch:</span><span class="sxs-lookup"><span data-stu-id="5e8dd-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="5e8dd-114">Begriff (ein vollständiges Wort)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-114">Term (a full word)</span></span>
- <span data-ttu-id="5e8dd-115">Präfix (beginnt mit Wort)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="5e8dd-116">Platzhalter (mit "\*" oder "?" Filter)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="5e8dd-117">Phrase (eine Textfolge in einem Dokument)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="5e8dd-118">Boolescher Wert (komplexe Suchvorgänge, die Abfragen kombinieren)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="5e8dd-119">Während Lucene Sanitäranlagen auf niedriger Ebene für die Suche bereitstellt, stellt Elasticsearch den Server bereit, der sich auf Lucene befindet.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="5e8dd-120">Elasticsearch fügt Funktionen auf höherer Ebene hinzu, um das Arbeiten von Lucene zu vereinfachen, einschließlich einer RESTful-API für den Zugriff auf die Indizierungs- und Suchfunktionen von Lucene.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="5e8dd-121">Darüber hinaus bietet es eine verteilte Infrastruktur, die in der Lage ist, eine enorme Skalierbarkeit, Fehlertoleranz und hohe Verfügbarkeit zu bieten.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="5e8dd-122">Für größere cloudnative Anwendungen mit komplexen Suchanforderungen ist Elasticsearch als managed Service in Azure verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="5e8dd-123">Microsoft Azure Marketplace enthält vorkonfigurierte Vorlagen, die Entwickler zum Bereitstellen eines Elasticsearch-Clusters in Azure verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="5e8dd-124">Im Microsoft Azure Marketplace können Entwickler vorkonfigurierte Vorlagen verwenden, die erstellt wurden, um einen Elasticsearch-Cluster in Azure schnell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="5e8dd-125">Mithilfe des von Azure verwalteten Angebots können Sie bis zu 50 Datenknoten, 20 koordinierende Knoten und drei dedizierte Masterknoten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="5e8dd-126">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="5e8dd-126">Summary</span></span>

<span data-ttu-id="5e8dd-127">In diesem Kapitel wurde ein detaillierter Blick auf Daten in Cloud-nativen Systemen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="5e8dd-128">Wir begannen damit, die Datenspeicherung in monolithischen Anwendungen mit Datenspeichermustern in Cloud-nativen Systemen zu kontrastieren.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="5e8dd-129">Wir untersuchten Datenmuster, die in Cloud-nativen Systemen implementiert wurden, einschließlich dienstübergreifender Abfragen, verteilter Transaktionen und Muster für systeme mit hohem Volumen.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="5e8dd-130">Wir haben SQL mit NoSQL-Daten kontrastiert.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="5e8dd-131">Wir haben uns die in Azure verfügbaren Datenspeicheroptionen angesehen, die sowohl Microsoft-zentrierte als auch Open-Source-Optionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="5e8dd-132">Schließlich haben wir caching und Elasticsearch in einer Cloud-nativen Anwendung diskutiert.</span><span class="sxs-lookup"><span data-stu-id="5e8dd-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="5e8dd-133">References</span><span class="sxs-lookup"><span data-stu-id="5e8dd-133">References</span></span>

- [<span data-ttu-id="5e8dd-134">Muster „CQRS“ (Command and Query Responsibility Segregation)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="5e8dd-135">Event Sourcing-Muster</span><span class="sxs-lookup"><span data-stu-id="5e8dd-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="5e8dd-136">Warum ist RDBMS Partition Tolerant in CAP Theorem nicht verfügbar und warum ist es verfügbar?</span><span class="sxs-lookup"><span data-stu-id="5e8dd-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="5e8dd-137">Materialisierte Ansicht</span><span class="sxs-lookup"><span data-stu-id="5e8dd-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="5e8dd-138">Alles, was Sie wirklich über Open-Source-Datenbanken wissen müssen</span><span class="sxs-lookup"><span data-stu-id="5e8dd-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="5e8dd-139">Muster „Kompensierende Transaktion“</span><span class="sxs-lookup"><span data-stu-id="5e8dd-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="5e8dd-140">Saga-Muster</span><span class="sxs-lookup"><span data-stu-id="5e8dd-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="5e8dd-141">Saga-Muster | Implementieren von Geschäftstransaktionen mithilfe von Microservices</span><span class="sxs-lookup"><span data-stu-id="5e8dd-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="5e8dd-142">Muster „Kompensierende Transaktion“</span><span class="sxs-lookup"><span data-stu-id="5e8dd-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="5e8dd-143">Hinter dem 9-Ball: Cosmos DB Consistency Levels erklärt</span><span class="sxs-lookup"><span data-stu-id="5e8dd-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="5e8dd-144">Erkunden der verschiedenen Typen von NoSQL-Datenbanken Teil II</span><span class="sxs-lookup"><span data-stu-id="5e8dd-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="5e8dd-145">Auf RDBMS-, NoSQL- und NewSQL-Datenbanken. Interview mit John Ryan</span><span class="sxs-lookup"><span data-stu-id="5e8dd-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="5e8dd-146">SQL vs NoSQL vs NewSQL: Der vollständige Vergleich</span><span class="sxs-lookup"><span data-stu-id="5e8dd-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="5e8dd-147">DASH: Vier Eigenschaften von Kubernetes-Native-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="5e8dd-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="5e8dd-148">KakerlakeDB</span><span class="sxs-lookup"><span data-stu-id="5e8dd-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="5e8dd-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="5e8dd-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="5e8dd-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="5e8dd-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="5e8dd-151">Vitess</span><span class="sxs-lookup"><span data-stu-id="5e8dd-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="5e8dd-152">Elasticsearch: The Definitive Guide (Elasticsearch: Die ultimative Anleitung)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-152">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="5e8dd-153">Einführung in Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="5e8dd-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="5e8dd-154">[Zurück](azure-caching.md)
>[Weiter](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="5e8dd-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
