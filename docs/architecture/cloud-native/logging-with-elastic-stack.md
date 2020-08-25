---
title: Protokollierung mit Elastic Stack
description: Protokollierung mithilfe von Elastic Stack, logstash und kibana
ms.date: 05/13/2020
ms.openlocfilehash: 32d9d0dae175d8d45d48b56d17f133b4cc432363
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811170"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="c7f8f-103">Protokollierung mit Elastic Stack</span><span class="sxs-lookup"><span data-stu-id="c7f8f-103">Logging with Elastic Stack</span></span>

<span data-ttu-id="c7f8f-104">Es gibt viele gute zentralisierte Protokollierungs Tools, die sich von kostenlosen Open Source-Tools bis hin zu kostspieligen Optionen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="c7f8f-105">In vielen Fällen sind die kostenlosen Tools so gut wie die kostenpflichtigen Angebote.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="c7f8f-106">Ein solches Tool ist eine Kombination aus drei Open Source-Komponenten: Elastic Search, logstash und kibana.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>

<span data-ttu-id="c7f8f-107">Gemeinsam werden diese Tools als elastischer Stapel oder Elk-Stapel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="c7f8f-108">Elastischer Stapel</span><span class="sxs-lookup"><span data-stu-id="c7f8f-108">Elastic Stack</span></span>

<span data-ttu-id="c7f8f-109">Der elastische Stapel ist eine leistungsstarke Option zum Sammeln von Informationen aus einem Kubernetes-Cluster.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-109">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="c7f8f-110">Kubernetes unterstützt das Senden von Protokollen an einen elasticsearch-Endpunkt, und zum [größten Teil](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)müssen Sie zunächst die Umgebungsvariablen wie in Abbildung 7-5 gezeigt festlegen:</span><span class="sxs-lookup"><span data-stu-id="c7f8f-110">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="c7f8f-111">**Abbildung 7-5**.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-111">**Figure 7-5**.</span></span> <span data-ttu-id="c7f8f-112">Konfigurationsvariablen für Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c7f8f-112">Configuration variables for Kubernetes</span></span>

<span data-ttu-id="c7f8f-113">Dadurch wird elasticsearch auf dem Cluster installiert, und das Ziel ist es, alle Cluster Protokolle an den Cluster zu senden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-113">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="c7f8f-114">![Ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für Protokolle anzeigt, die aus Kubernetes ](./media/kibana-dashboard.png)
 **Abbildung 7-6**erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-114">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="c7f8f-115">Ein Beispiel für ein kibana-Dashboard, das die Ergebnisse einer Abfrage für Protokolle anzeigt, die von Kubernetes erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-115">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="c7f8f-116">Was sind die Vorteile von Elastic Stack?</span><span class="sxs-lookup"><span data-stu-id="c7f8f-116">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="c7f8f-117">Elastischer Stapel ermöglicht die zentralisierte Protokollierung in kostengünstiger, skalierbarer und cloudfreundlicher Weise.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-117">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="c7f8f-118">Mit der Benutzeroberfläche wird die Datenanalyse optimiert, sodass Sie sich mit der Verwendung von Erkenntnissen aus Ihren Daten beschäftigen können, anstatt mit einer umständlich-Schnittstelle zu kämpfen.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-118">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="c7f8f-119">Es unterstützt eine Vielzahl von Eingaben, sodass Sie in der Lage sind, Protokoll-und Metrikdaten weiterhin in das System zu übertragen, wenn die verteilte Anwendung mehr und unterschiedliche Dienste umfasst.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-119">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="c7f8f-120">Der elastische Stapel unterstützt auch schnelle Suchvorgänge, auch über große Datasets hinweg, sodass es auch für große Anwendungen möglich ist, ausführliche Daten zu protokollieren und dennoch in der Lage zu sein, ihn in einer leistungsfähigen Weise sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-120">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="c7f8f-121">Logstash</span><span class="sxs-lookup"><span data-stu-id="c7f8f-121">Logstash</span></span>

<span data-ttu-id="c7f8f-122">Die erste Komponente ist " [logstash](https://www.elastic.co/products/logstash)".</span><span class="sxs-lookup"><span data-stu-id="c7f8f-122">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="c7f8f-123">Dieses Tool wird zum Erfassen von Protokollinformationen aus einer Vielzahl von verschiedenen Quellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-123">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="c7f8f-124">Logstash kann z. b. Protokolle von einem Datenträger lesen und auch Nachrichten aus Protokollierungs Bibliotheken wie [serilog](https://serilog.net/)empfangen.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-124">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="c7f8f-125">Logstash kann einige grundlegende Filter und Erweiterungen für die Protokolle ausführen, sobald sie eintreffen.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-125">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="c7f8f-126">Wenn Ihre Protokolle beispielsweise IP-Adressen enthalten, kann logstash so konfiguriert werden, dass eine geografische Suche durchführen und ein Land oder sogar eine Ursprungs Stadt für diese Nachricht abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-126">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="c7f8f-127">Serilog ist eine Protokollierungs Bibliothek für .NET-Sprachen, die eine parametrisierte Protokollierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-127">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="c7f8f-128">Anstatt eine Text Protokollmeldung zu erzeugen, die Felder einbettet, werden die Parameter getrennt aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-128">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="c7f8f-129">Dies ermöglicht eine intelligentere Filterung und Suche.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-129">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="c7f8f-130">In Abbildung 7-7 wird eine Beispielkonfiguration für das serilog zum Schreiben in logstash angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-130">A sample Serilog configuration for writing to Logstash appears in Figure 7-7.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="c7f8f-131">**Abbildung 7-7**.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-131">**Figure 7-7**.</span></span> <span data-ttu-id="c7f8f-132">Serilog-Konfiguration zum direkten Schreiben von Protokollinformationen in logstash über http</span><span class="sxs-lookup"><span data-stu-id="c7f8f-132">Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="c7f8f-133">Logstash würde eine Konfiguration verwenden, die wie in Abbildung 7-8 dargestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-133">Logstash would use a configuration like the one shown in Figure 7-8.</span></span>

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

<span data-ttu-id="c7f8f-134">**Abbildung 7-8**.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-134">**Figure 7-8**.</span></span> <span data-ttu-id="c7f8f-135">Eine logstash-Konfiguration zum Verarbeiten von Protokollen aus serilog</span><span class="sxs-lookup"><span data-stu-id="c7f8f-135">A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="c7f8f-136">Für Szenarien, in denen eine umfangreiche Protokoll Bearbeitung nicht erforderlich ist, gibt es eine Alternative zu logstash, die als [Beats](https://www.elastic.co/products/beats)bezeichnet wird</span><span class="sxs-lookup"><span data-stu-id="c7f8f-136">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="c7f8f-137">Beats ist eine Reihe von Tools, die eine Vielzahl von Daten aus Protokollen zu Netzwerkdaten und Betriebszeit Informationen sammeln können.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-137">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="c7f8f-138">Viele Anwendungen verwenden logstash und Beats.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-138">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="c7f8f-139">Nachdem die Protokolle von logstash erfasst wurden, müssen Sie an einem Ort abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-139">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="c7f8f-140">Obwohl logstash viele verschiedene Ausgaben unterstützt, ist eine der aufregendsten bei der elastischen Suche.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-140">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="c7f8f-141">Elastic Search</span><span class="sxs-lookup"><span data-stu-id="c7f8f-141">Elastic search</span></span>

<span data-ttu-id="c7f8f-142">Bei der elastischen Suche handelt es sich um ein leistungsfähiges Suchmodul, das Protokolle nach dem Eintreffen indizieren kann</span><span class="sxs-lookup"><span data-stu-id="c7f8f-142">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="c7f8f-143">Dadurch wird das Ausführen von Abfragen für die Protokolle schnell.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-143">It makes running queries against the logs quick.</span></span> <span data-ttu-id="c7f8f-144">Bei der elastischen Suche können große Mengen von Protokollen verarbeitet und in Extremfällen auf viele Knoten horizontal hochskaliert werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-144">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="c7f8f-145">Protokollmeldungen, die so erstellt wurden, dass Sie Parameter enthalten oder über Parameter verfügen, die durch die logstash-Verarbeitung voneinander getrennt wurden, können direkt abgefragt werden, da elasticsearch diese Informationen beibehält.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-145">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="c7f8f-146">Eine Abfrage, die nach den ersten 10 Seiten sucht, die von besucht `jill@example.com` werden, wird in Abbildung 7-9 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-146">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-9.</span></span>

```json
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

<span data-ttu-id="c7f8f-147">**Abbildung 7-9**.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-147">**Figure 7-9**.</span></span> <span data-ttu-id="c7f8f-148">Eine elasticsearch-Abfrage zum Suchen der zehn wichtigsten Seiten, die von einem Benutzer besucht werden</span><span class="sxs-lookup"><span data-stu-id="c7f8f-148">An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="c7f8f-149">Visualisieren von Informationen mit kibana-webdashboards</span><span class="sxs-lookup"><span data-stu-id="c7f8f-149">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="c7f8f-150">Die letzte Komponente des Stapels ist kibana.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-150">The final component of the stack is Kibana.</span></span> <span data-ttu-id="c7f8f-151">Mit diesem Tool werden interaktive Visualisierungen in einem Webdashboard bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-151">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="c7f8f-152">Dashboards können auch von Benutzern erstellt werden, die nicht technisch sind.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-152">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="c7f8f-153">Die meisten Daten, die im elasticsearch-Index ansässig sind, können in die kibana-Dashboards eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-153">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="c7f8f-154">Einzelne Benutzer haben möglicherweise unterschiedliche Dashboardansichten, und kibana ermöglicht diese Anpassung durch das zulassen Benutzer spezifischer Dashboards.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-154">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="c7f8f-155">Installieren des elastischen Stapels in Azure</span><span class="sxs-lookup"><span data-stu-id="c7f8f-155">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="c7f8f-156">Der elastische Stapel kann auf verschiedene Weise auf Azure installiert werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-156">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="c7f8f-157">Wie immer ist es möglich, [virtuelle Computer bereitzustellen und elastischen Stapel direkt auf Ihnen zu installieren](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="c7f8f-157">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="c7f8f-158">Diese Option wird von einigen erfahrenen Benutzern bevorzugt, da Sie den höchsten Grad an Anpassungsmöglichkeiten bietet.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-158">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="c7f8f-159">Durch die Bereitstellung von Infrastructure-as-a-Service wird ein erheblicher Verwaltungsaufwand eingeführt, bei dem die Mitarbeiter, die diesen Weg nehmen, den Besitz aller Aufgaben übernehmen, die mit der Infrastruktur als Dienst verbunden sind, z. b. das Sichern der Computer und das aktuelle aufbewahren</span><span class="sxs-lookup"><span data-stu-id="c7f8f-159">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="c7f8f-160">Eine Option mit weniger Aufwand besteht darin, einen der vielen docker-Container zu verwenden, auf denen der elastische Stapel bereits konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-160">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="c7f8f-161">Diese Container können in einem vorhandenen Kubernetes-Cluster abgelegt und neben Anwendungscode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-161">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="c7f8f-162">Der Container [sebp/Elk](https://elk-docker.readthedocs.io/) ist ein gut dokumentierter und getesteter Container für elastische Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c7f8f-162">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="c7f8f-163">Eine andere Möglichkeit ist ein [kürzlich kündigter Elk-as-a-Service-Angebot](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="c7f8f-163">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="c7f8f-164">Referenzen</span><span class="sxs-lookup"><span data-stu-id="c7f8f-164">References</span></span>

- [<span data-ttu-id="c7f8f-165">Installieren des elastischen Stapels in Azure</span><span class="sxs-lookup"><span data-stu-id="c7f8f-165">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="c7f8f-166">[Zurück](observability-patterns.md)
>[Weiter](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="c7f8f-166">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
