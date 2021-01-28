---
title: Verwenden von F# in Azure
description: Anleitung zur Verwendung von Azure-Diensten mit F#
author: sylvanc
ms.date: 07/29/2020
ms.custom: devx-track-fsharp
ms.openlocfilehash: 16599aa48776acee05edf8201cdd148a87507cdb
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899409"
---
# <a name="using-f-on-azure"></a>Verwenden von F# in Azure

F# ist eine hervorragende Sprache für die Cloudprogrammierung und wird häufig zum Schreiben von ASP.NET-Webanwendungen, Clouddiensten, in der Cloud gehosteten Microservices und für die skalierbare Datenverarbeitung verwendet.

In den folgenden Abschnitten finden Sie Ressourcen zur Verwendung einer Reihe von Azure-Diensten mit F#.

> [!NOTE]
> Wenn ein bestimmter Azure-Dienst in dieser Dokumentation nicht erläutert wird, wenden Sie sich entweder an die Azure Functions- oder die .NET-Dokumentation für diesen Dienst. Einige Azure-Dienste sind sprachunabhängig und erfordern keine sprachspezifische Dokumentation und sind hier nicht aufgeführt.

## <a name="using-azure-virtual-machines-with-f"></a>Verwenden von Azure Virtual Machines mit F\#

Azure unterstützt eine Vielzahl von Konfigurationen von virtuellen Computern. Informationen dazu finden Sie unter [Linux und Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).

Um F# auf einem virtuellen Computer zum Ausführen, für die Kompilierung und/oder zum Erstellen von Skripts zu installieren, gehen Sie unter [Use F# on Linux (Verwenden von F# unter Linux)](https://fsharp.org/use/linux) und [Use F# on Windows (Verwenden von F# unter Windows)](https://fsharp.org/use/windows).

## <a name="using-azure-functions-with-f"></a>Verwenden von Azure Functions mit F\#

[Azure Functions](https://azure.microsoft.com/services/functions/) ist eine Lösung zum einfachen Ausführen kleiner Codestücke oder „Funktionen“ in der Cloud. Sie können nur den Code schreiben, den Sie für Ihr vorliegendes Problem benötigen, und müssen sich keine Sorgen über die Ausführung der gesamten Anwendung oder der Infrastruktur machen. Ihre Funktionen sind mit Ereignissen in Azure Storage und anderen in der Cloud gehosteten Ressourcen verbunden. Daten fließen über Funktionsargumente in Ihre F#-Funktionen. Sie können die Entwicklungssprache Ihrer Wahl verwenden und auf Azure vertrauen, dass skaliert wird, wenn dies erforderlich ist.

Azure Functions unterstützt F# als Hauptprogrammiersprache mit effizienter, reaktiver, skalierbare Ausführung von F#-Code. Referenzdokumentationen zur Verwendung von F# mit Azure Functions finden Sie unter [F#-Entwicklerreferenz zu Azure Functions](/azure/azure-functions/functions-reference-fsharp).

Weitere Ressourcen für die Verwendung von Azure Functions und F#:

* [Scale Up Azure Functions in F# Using Suave (Zentrales Aufwärtsskalieren von Azure Functions in F# mit Suave)](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [How to create Azure function in F# (Erstellen von Azure-Funktionen in F#)](https://www.mnie.me/azurefunctions)
* [Verwenden des Azure-Typanbieters mit Azure Functions](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a>Verwenden von Azure Storage mit F\#

Azure Storage ist eine Ebene von Speicherlösung für moderne Anwendungen, die auf Dauerhaftigkeit., Verfügbarkeit und Skalierbarkeit für die Bedürfnisse ihrer Kunden beruhen. F#-Programme können mithilfe der in den folgenden Artikeln beschriebenen Methoden direkt mit Azure-Speicherdiensten interagieren.

* [Erste Schritte mit Azure Blob Storage mit F#](blob-storage.md)
* [Erste Schritte mit Azure File Storage mit F#](file-storage.md)
* [Erste Schritte mit Azure Queue Storage mit F#](queue-storage.md)
* [Erste Schritte mit Azure Table Storage mit F#](table-storage.md)

Azure Storage kann auch in Verbindung mit Azure Functions über die deklarative Konfiguration anstatt mit expliziten API-Aufrufen verwendet werden. Beispiele für F# finden Sie unter [Azure Functions – Storage-Blobbindungen](/azure/azure-functions/functions-bindings-storage).

## <a name="using-azure-app-service-with-f"></a>Verwenden von Azure App Service mit F\#

[Azure App Service](https://azure.microsoft.com/services/app-service/) ist eine Cloudplattform zum Erstellen leistungsstarker Web- und mobilen Apps, die sich überall mit Daten verbinden, ob in der Cloud oder lokal.

* [F# Azure Web API example (Beispiel für eine F#-Azure-Web-API)](https://github.com/fsprojects/azure-webapi-example)
* [Hosting F# in a web application on Azure (Hosten von F# in einer Web-Anwendung in Azure)](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-on-azure-hdinsight-or-azure-databricks"></a>Verwenden von Apache Spark mit F# in Azure HDInsight oder Azure Databricks

[Apache Spark für Azure HDInsight](/azure/hdinsight/spark/apache-spark-overview) ist ein Open-Source-Verarbeitungsframework, das umfangreiche Anwendungen zur Datenanalyse ausführt. [Azure Databricks](/azure/databricks/scenarios/what-is-azure-databricks) ist eine Apache Spark-basierte Analyseplattform, die für die Microsoft Azure-Clouddienstplattform optimiert ist. Durch Azure kann Apache Spark einfach und kosteneffektiv bereitgestellt werden. Entwickeln Sie Ihre Spark-Anwendung in F# mithilfe von [.NET for Apache Spark](../../spark/what-is-apache-spark-dotnet.md), den .NET-Bindungen für Apache Spark.

* [F#-Beispiele für .NET for Apache Spark](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.FSharp.Examples)
* [Installieren von interaktiven .NET-Jupyter-Notebooks in Azure HDInsight](../../spark/how-to-guides/hdinsight-notebook-installation.md)
* [Übermitteln von Apache Spark-Aufträgen an Azure HDInsight](../../spark/how-to-guides/hdinsight-deploy-methods.md)
* [Übermitteln von Apache Spark-Aufträgen an Azure Databricks](../../spark/how-to-guides/databricks-deploy-methods.md)

## <a name="using-azure-cosmos-db-with-f"></a>Verwenden von Azure Cosmos DB mit F\#

[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) ist ein NoSQL-Dienst für hochverfügbare, global verteilte Apps.

Azure Cosmos DB kann auf zwei Arten mit F# verwendet werden:

1. Durch die Erstellung von Azure Functions mit F#, die auf Änderungen in Azure Cosmos DB-Sammlungen reagieren oder diese verursachen (Siehe [Azure Cosmos DB-Bindungen für Azure Functions](/azure/azure-functions/functions-bindings-cosmosdb))
2. Durch Verwendung des [Azure Cosmos DB .NET SDK für die SQL-API](/azure/cosmos-db/sql-api-sdk-dotnet) (die zugehörigen Beispiele wurden in C# geschrieben)

## <a name="using-azure-event-hubs-with-f"></a>Verwenden von Azure Event Hubs mit F\#

[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) stellt Telemetrieerfassung im Cloudmaßstab von Websites, Apps und Geräten bereit.

Azure Event Hubs kann mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions mit F#, was durch Ereignisse ausgelöst wird. (Weitere Informationen finden Sie unter [Event Hub-Bindungen für Azure Functions](/azure/azure-functions/functions-bindings-event-hubs)) oder
2. Mithilfe der [.NET SDK für Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="using-azure-notification-hubs-with-f"></a>Verwenden von Azure Notification Hubs mit F\#

[Azure Notification Hubs](/azure/notification-hubs/) ist eine plattformübergreifende, erweiterbare Pushinfrastruktur, die Ihnen ermöglicht, Pushbenachrichtigungen von Mobilgeräten von jedem Backend (in der Cloud oder lokal) zu jeder mobilen Plattform zu senden.

Azure Notification Hubs können mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions in F#, wodurch Ergebnisse an Notification Hub gesendet werden. (Weitere Informationen finden Sie unter [Azure Functions Notification Hub-Ausgabebindung](/azure/azure-functions/functions-bindings-notification-hubs) oder
2. Mithilfe der [.NET SDK für Azure](/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="implementing-webhooks-on-azure-with-f"></a>Implementieren von WebHooks in Azure mit F\#

Ein [Webhook](https://en.wikipedia.org/wiki/Webhook) ist ein Rückruf, der durch eine Webanfrage ausgelöst wird. Webhooks werden von Websites wie GitHub verwendet, um Ereignisse zu signalisieren.

Webhooks können in F# implementiert und in Azure durch [HTTP- und Webhookbindungen in Azure Functions](/azure/azure-functions/functions-bindings-http-webhook) gehostet werden.

## <a name="using-webjobs-with-f"></a>Verwendung von WebJobs mit F\#

[WebJobs](/azure/app-service-web/web-sites-create-web-jobs) sind Programme, die Sie in Ihrer App Service-Web-App auf drei Arten ausführen können: bedarfsgesteuert, kontinuierlich oder zeitplanmäßig.

[Beispiel für F# WebJob](https://github.com/jrr/webjob-project-examples)

## <a name="implementing-timers-on-azure-with-f"></a>Implementieren von Timern in Azure mit F\#

Timer lösen Aufruffunktionen auf Grundlage eines Zeitplans, einmal oder wiederkehrend aus.

Timer können in F# implementiert und in Azure durch einen [Timerauslöser in Azure Functions in F#](/azure/azure-functions/functions-bindings-timer) gehostet werden.

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a>Bereitstellen und Verwalten von Azure-Ressourcen mit F#-Skripts

Azure-VMs können programmgesteuert bereitgestellt und von F#-Skripts mithilfe der Microsoft.Azure.Management-Pakete und APIs verwaltet werden. Bespiele finden Sie unter [Erste Schritte mit den Verwaltungsbibliotheken für .NET](/previous-versions/azure/dn722415(v=azure.100)) und [Azure Resource Manager-Bereitstellung im Vergleich zur klassischen Bereitstellung: Grundlegendes zu Bereitstellungsmodellen und zum Status von Ressourcen](/azure/azure-resource-manager/resource-manager-deployment-model).

Auch andere Azure-Ressourcen können möglicherweise auch von F#-Skripts bereitgestellt und verwaltet werden, die über die gleichen Komponenten verfügen. Beispielsweise können Sie Speicherkonten erstellen, Azure Cloud Services bereitstellen, Azure Cosmos DB-Instanzen erstellen und Azure Notification Hubs programmgesteuert über F#-Skripts verwalten.

Die Verwendung von F#-Skripts zum Bereitstellen und Verwalten von Ressourcen ist normalerweise nicht notwendig. Beispielsweise können Azure-Ressourcen möglicherweise auch direkt über JSON-Vorlagenbeschreibungen bereitgestellt werden, die parametrisiert werden können. Informationen, einschließlich Beispiele wie die [Azure-Schnellstartvorlagen](https://azure.microsoft.com/resources/templates/), finden Sie unter [Bewährte Methoden für das Erstellen von Azure Resource Manager-Vorlagen](/azure/azure-resource-manager/resource-manager-template-best-practices).

## <a name="other-resources"></a>Weitere Ressourcen

* [Die vollständige Dokumentation für alle Azure-Dienste](/azure/)
