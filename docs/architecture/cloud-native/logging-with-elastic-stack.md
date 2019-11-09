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
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="11ea9-103">Protokollierung mit Elastic Stack</span><span class="sxs-lookup"><span data-stu-id="11ea9-103">Logging with Elastic Stack</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="11ea9-104">Es gibt viele gute zentralisierte Protokollierungs Tools, die sich von kostenlosen Open Source-Tools bis hin zu kostspieligen Optionen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="11ea9-105">In vielen Fällen sind die kostenlosen Tools so gut wie die kostenpflichtigen Angebote.</span><span class="sxs-lookup"><span data-stu-id="11ea9-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="11ea9-106">Ein solches Tool ist eine Kombination aus drei Open Source-Komponenten: Elastic Search, logstash und kibana.</span><span class="sxs-lookup"><span data-stu-id="11ea9-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>
<span data-ttu-id="11ea9-107">Gemeinsam werden diese Tools als elastischer Stapel oder Elk-Stapel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="11ea9-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="11ea9-108">Was sind die Vorteile von Elastic Stack?</span><span class="sxs-lookup"><span data-stu-id="11ea9-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="11ea9-109">Elastischer Stapel ermöglicht die zentralisierte Protokollierung in kostengünstiger, skalierbarer und cloudfreundlicher Weise.</span><span class="sxs-lookup"><span data-stu-id="11ea9-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="11ea9-110">Mit der Benutzeroberfläche wird die Datenanalyse optimiert, sodass Sie sich mit der Verwendung von Erkenntnissen aus Ihren Daten beschäftigen können, anstatt mit einer umständlich-Schnittstelle zu kämpfen.</span><span class="sxs-lookup"><span data-stu-id="11ea9-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="11ea9-111">Es unterstützt eine Vielzahl von Eingaben, sodass Sie in der Lage sind, Protokoll-und Metrikdaten weiterhin in das System zu übertragen, wenn die verteilte Anwendung mehr und unterschiedliche Dienste umfasst.</span><span class="sxs-lookup"><span data-stu-id="11ea9-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="11ea9-112">Der elastische Stapel unterstützt auch schnelle Suchvorgänge, auch über große Datasets hinweg, sodass es auch für große Anwendungen möglich ist, ausführliche Daten zu protokollieren und dennoch in der Lage zu sein, ihn in einer leistungsfähigen Weise sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="11ea9-112">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="11ea9-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="11ea9-113">Logstash</span></span>

<span data-ttu-id="11ea9-114">Die erste Komponente ist " [logstash](https://www.elastic.co/products/logstash)".</span><span class="sxs-lookup"><span data-stu-id="11ea9-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="11ea9-115">Dieses Tool wird zum Erfassen von Protokollinformationen aus einer Vielzahl von verschiedenen Quellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="11ea9-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="11ea9-116">Logstash kann z. b. Protokolle von einem Datenträger lesen und auch Nachrichten aus Protokollierungs Bibliotheken wie [serilog](https://serilog.net/)empfangen.</span><span class="sxs-lookup"><span data-stu-id="11ea9-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="11ea9-117">Logstash kann einige grundlegende Filter und Erweiterungen für die Protokolle ausführen, sobald sie eintreffen.</span><span class="sxs-lookup"><span data-stu-id="11ea9-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="11ea9-118">Wenn Ihre Protokolle beispielsweise IP-Adressen enthalten, kann logstash so konfiguriert werden, dass eine geografische Suche durchführen und ein Land oder sogar eine Ursprungs Stadt für diese Nachricht abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="11ea9-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="11ea9-119">Serilog ist eine Protokollierungs Bibliothek für .NET-Sprachen, die eine parametrisierte Protokollierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="11ea9-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="11ea9-120">Anstatt eine Text Protokollmeldung zu erzeugen, die Felder einbettet, werden die Parameter getrennt aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="11ea9-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="11ea9-121">Dies ermöglicht eine intelligentere Filterung und Suche.</span><span class="sxs-lookup"><span data-stu-id="11ea9-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="11ea9-122">In Abbildung 7-2 wird eine Beispielkonfiguration für das serilog zum Schreiben in logstash angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ea9-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="11ea9-123">**Abbildung 7-2** Serilog-Konfiguration zum direkten Schreiben von Protokollinformationen in logstash über http</span><span class="sxs-lookup"><span data-stu-id="11ea9-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="11ea9-124">Logstash würde eine Konfiguration verwenden, die wie in Abbildung 7-3 dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="11ea9-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span>

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

<span data-ttu-id="11ea9-125">**Abbildung 7-3** : eine logstash-Konfiguration zum Verarbeiten von Protokollen aus serilog</span><span class="sxs-lookup"><span data-stu-id="11ea9-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="11ea9-126">Für Szenarien, in denen eine umfangreiche Protokoll Bearbeitung nicht erforderlich ist, gibt es eine Alternative zu logstash, die als [Beats](https://www.elastic.co/products/beats)bezeichnet wird</span><span class="sxs-lookup"><span data-stu-id="11ea9-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="11ea9-127">Beats ist eine Reihe von Tools, die eine Vielzahl von Daten aus Protokollen zu Netzwerkdaten und Betriebszeit Informationen sammeln können.</span><span class="sxs-lookup"><span data-stu-id="11ea9-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="11ea9-128">Viele Anwendungen verwenden logstash und Beats.</span><span class="sxs-lookup"><span data-stu-id="11ea9-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="11ea9-129">Nachdem die Protokolle von logstash erfasst wurden, müssen Sie an einem Ort abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="11ea9-130">Obwohl logstash viele verschiedene Ausgaben unterstützt, ist eine der aufregendsten bei der elastischen Suche.</span><span class="sxs-lookup"><span data-stu-id="11ea9-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="11ea9-131">Elastische Suche</span><span class="sxs-lookup"><span data-stu-id="11ea9-131">Elastic search</span></span>

<span data-ttu-id="11ea9-132">Bei der elastischen Suche handelt es sich um ein leistungsfähiges Suchmodul, das Protokolle nach dem Eintreffen indizieren kann</span><span class="sxs-lookup"><span data-stu-id="11ea9-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="11ea9-133">Dadurch wird das Ausführen von Abfragen für die Protokolle schnell.</span><span class="sxs-lookup"><span data-stu-id="11ea9-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="11ea9-134">Bei der elastischen Suche können große Mengen von Protokollen verarbeitet und in Extremfällen auf viele Knoten horizontal hochskaliert werden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="11ea9-135">Protokollmeldungen, die so erstellt wurden, dass Sie Parameter enthalten oder über Parameter verfügen, die durch die logstash-Verarbeitung voneinander getrennt wurden, können direkt abgefragt werden, da elasticsearch diese Informationen beibehält.</span><span class="sxs-lookup"><span data-stu-id="11ea9-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="11ea9-136">Eine Abfrage, die nach den ersten 10 Seiten sucht, die von `jill@example.com`besucht werden, wird in Abbildung 7-4 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11ea9-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

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

<span data-ttu-id="11ea9-137">**Abbildung 7-4** : eine elasticsearch-Abfrage zum Suchen der zehn wichtigsten Seiten, die von einem Benutzer besucht werden</span><span class="sxs-lookup"><span data-stu-id="11ea9-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="11ea9-138">Visualisieren von Informationen mit kibana-webdashboards</span><span class="sxs-lookup"><span data-stu-id="11ea9-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="11ea9-139">Die letzte Komponente des Stapels ist kibana.</span><span class="sxs-lookup"><span data-stu-id="11ea9-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="11ea9-140">Mit diesem Tool werden interaktive Visualisierungen in einem Webdashboard bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="11ea9-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="11ea9-141">Dashboards können auch von Benutzern erstellt werden, die nicht technisch sind.</span><span class="sxs-lookup"><span data-stu-id="11ea9-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="11ea9-142">Die meisten Daten, die im elasticsearch-Index ansässig sind, können in die kibana-Dashboards eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="11ea9-143">Einzelne Benutzer haben möglicherweise unterschiedliche Dashboardansichten, und kibana ermöglicht diese Anpassung durch das zulassen Benutzer spezifischer Dashboards.</span><span class="sxs-lookup"><span data-stu-id="11ea9-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="11ea9-144">Installieren des elastischen Stapels in Azure</span><span class="sxs-lookup"><span data-stu-id="11ea9-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="11ea9-145">Der elastische Stapel kann auf verschiedene Weise auf Azure installiert werden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="11ea9-146">Wie immer ist es möglich, [virtuelle Computer bereitzustellen und elastischen Stapel direkt auf Ihnen zu installieren](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="11ea9-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="11ea9-147">Diese Option wird von einigen erfahrenen Benutzern bevorzugt, da Sie den höchsten Grad an Anpassungsmöglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="11ea9-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="11ea9-148">Durch die Bereitstellung von Infrastructure-as-a-Service wird ein erheblicher Verwaltungsaufwand eingeführt, bei dem die Mitarbeiter, die diesen Weg nehmen, den Besitz aller Aufgaben übernehmen, die mit der Infrastruktur als Dienst verbunden sind, z. b. das Sichern der Computer und das aktuelle aufbewahren</span><span class="sxs-lookup"><span data-stu-id="11ea9-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="11ea9-149">Eine Option mit weniger Aufwand besteht darin, einen der vielen docker-Container zu verwenden, auf denen der elastische Stapel bereits konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="11ea9-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="11ea9-150">Diese Container können in einem vorhandenen Kubernetes-Cluster abgelegt und neben Anwendungscode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11ea9-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="11ea9-151">Der Container [sebp/Elk](https://elk-docker.readthedocs.io/) ist ein gut dokumentierter und getesteter Container für elastische Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="11ea9-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="11ea9-152">Eine andere Möglichkeit ist ein [kürzlich kündigter Elk-as-a-Service-Angebot](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="11ea9-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="11ea9-153">Verweise</span><span class="sxs-lookup"><span data-stu-id="11ea9-153">References</span></span>

- [<span data-ttu-id="11ea9-154">Installieren des elastischen Stapels in Azure</span><span class="sxs-lookup"><span data-stu-id="11ea9-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="11ea9-155">[Zurück](observability-patterns.md)
>[Weiter](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="11ea9-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
