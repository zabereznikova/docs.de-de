---
title: Verwenden von F# in Azure
description: Anleitung zur Verwendung von Azure-Diensten mit F##
keywords: Azure, Cloud, Visual F#, F#, funktionale Programmierung, .NET, .NET Core
author: sylvanc
ms.author: phcart
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: FAD4D11E-703A-42D4-9F72-893D9E0F569B
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: bb02383a15b4c9617f3ec89a11fe8a4cb3572584
ms.lasthandoff: 04/05/2017

---


# <a name="using-f-on-azure"></a>Verwenden von F# in Azure

F# ist eine hervorragende Sprache für die Cloudprogrammierung und wird häufig zum Schreiben von ASP.NET-Webanwendungen, Clouddiensten, in der Cloud gehosteten Microservices und für die skalierbare Datenverarbeitung verwendet.

In den folgenden Abschnitten finden Sie Ressourcen zur Verwendung einer Reihe von Azure-Diensten mit F#.

> [!NOTE]
> Wenn ein bestimmter Azure-Dienst in dieser Dokumentation nicht erläutert wird, wenden Sie sich entweder an die Azure Functions- oder die .NET-Dokumentation für diesen Dienst. Einige Azure-Dienste sind sprachunabhängig und erfordern keine sprachspezifische Dokumentation und sind hier nicht aufgeführt.

## <a name="using-azure-virtual-machines-with-f"></a>Verwenden von Azure Virtual Machines mit F## #

Azure unterstützt eine Vielzahl von Konfigurationen von virtuellen Computern. Informationen dazu finden Sie unter [Linux und Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).

Um F# auf einem virtuellen Computer zum Ausführen, für die Kompilierung und/oder zum Erstellen von Skripts zu installieren, gehen Sie unter [Use F# on Linux (Verwenden von F# unter Linux)](http://fsharp.org/use/linux) und [Use F# on Windows (Verwenden von F# unter Windows)](http://fsharp.org/use/windows).


## <a name="using-azure-functions-with-f"></a>Verwenden von Azure Functions mit F## #

[Azure Functions](https://azure.microsoft.com/services/functions/) ist eine Lösung zum einfachen Ausführen kleiner Codestücke oder „Funktionen“ in der Cloud. Sie können nur den Code schreiben, den Sie für Ihr vorliegendes Problem benötigen, und müssen sich keine Sorgen über die Ausführung der gesamten Anwendung oder der Infrastruktur machen. Ihre Funktionen sind mit Ereignissen in Azure Storage und anderen in der Cloud gehosteten Ressourcen verbunden. Daten fließen über Funktionsargumente in Ihre F#-Funktionen. Sie können die Entwicklungssprache Ihrer Wahl verwenden und auf Azure vertrauen, dass skaliert wird, wenn dies erforderlich ist.

Azure Functions unterstützt F# als Hauptprogrammiersprache mit effizienter, reaktiver, skalierbare Ausführung von F#-Code. Referenzdokumentationen zur Verwendung von F# mit Azure Functions finden Sie unter [F#-Entwicklerreferenz zu Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-reference-fsharp).

Weitere Ressourcen für die Verwendung von Azure Functions und F#:

* [Scale Up Azure Functions in F# Using Suave (Zentrales Aufwärtsskalieren von Azure Functions in F# mit Suave)](http://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)
* [How to create Azure function in F# (Erstellen von Azure-Funktionen in F#)](https://mnie.github.io/2016-09-08-AzureFunctions/)

## <a name="using-azure-storage-with-f"></a>Verwenden von Azure Storage mit F## #

Azure Storage ist eine Ebene von Speicherlösung für moderne Anwendungen, die auf Dauerhaftigkeit., Verfügbarkeit und Skalierbarkeit für die Bedürfnisse ihrer Kunden beruhen. F#-Programme können direkt mit Azure-Speicherdiensten mithilfe der in den folgenden Artikeln beschriebenen Methoden interagieren.

* [Erste Schritte mit Azure Blob Storage mit F#](blob-storage.md)
* [Erste Schritte mit Azure File Storage mit F#](file-storage.md)
* [Erste Schritte mit Azure Queue Storage mit F#](queue-storage.md)
* [Erste Schritte mit Azure Table Storage mit F#](table-storage.md)

Azure Storage kann auch in Verbindung mit Azure Functions über die deklarative Konfiguration anstatt mit expliziten API-Aufrufen verwendet werden. Beispiele für F# finden Sie unter [Azure Functions – Storage-Blobbindungen](https://docs.microsoft.com/azure/azure-functions/functions-bindings-storage).

## <a name="using-azure-app-service-with-f"></a>Verwenden von Azure App Service mit F## #

[Azure App Service](https://azure.microsoft.com/services/app-service/) ist eine Cloudplattform zum Erstellen leistungsstarker Web- und mobilen Apps, die sich überall mit Daten verbinden, ob in der Cloud oder lokal.

* [F# Azure Web API example (Beispiel für eine F#-Azure-Web-API)](https://github.com/fsprojects/azure-webapi-example)
* [Hosting F# in a web application on Azure (Hosten von F# in einer Web-Anwendung in Azure)](https://github.com/isaacabraham/fsharp-demonstrator)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a>Verwenden von Apache Spark mit F# mit Azure HDInsight

[Apache Spark für Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) ist ein Open-Source-Verarbeitungsframework, das umfangreiche Anwendungen zur Datenanalyse ausführt. Durch Azure kann Apache Spark einfach und kosteneffektiv bereitgestellt werden. Entwickeln Sie Ihre Spark-Anwendung in F# mithilfe von [Mobius](https://github.com/Microsoft/Mobius), einer .NET-API für Spark.

* [Implementing Spark Apps in F# using Mobius (Implementieren von Spark-APps in F# mit Mobius)](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)
* [Example F# Spark Apps using Mobius (Beispiel einer F#-Spark-App mithilfe von Mobius)](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-documentdb-with-f"></a>Verwenden von Azure DocumentDB mit F## #

[Azure DocumentDB](https://azure.microsoft.com/services/documentdb/) ist ein NoSQL-Dienst für hochverfügbare, global verteilte Apps.

Azure DocumentDB kann mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions mit F#, die auf Änderungen in DocumentDB-Sammlungen reagieren oder diese verursachen. (Weitere Informationen finden Sie unter [DocumentDB-Bindungen in Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-bindings-documentdb)) oder
2. Mithilfe der [.NET SDK für Azure](https://docs.microsoft.com/azure/documentdb/documentdb-get-started-quickstart). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="using-azure-event-hubs-with-f"></a>Verwenden von Azure Event Hubs mit F## #

[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) stellt Telemetrieerfassung im Cloudmaßstab von Websites, Apps und Geräten bereit.

Azure Event Hubs kann mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions mit F#, was durch Ereignisse ausgelöst wird. (Weitere Informationen finden Sie unter [Event Hub-Bindungen für Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-bindings-event-hubs)) oder
2. Mithilfe der [.NET SDK für Azure](https://docs.microsoft.com/azure/event-hubs/event-hubs-csharp-ephcs-getstarted). Beachten Sie, dass diese Beispiele in C# geschrieben sind.

## <a name="using-azure-notification-hubs-with-f"></a>Verwenden von Azure Notification Hubs mit F## #

[Azure Notification Hubs](https://docs.microsoft.com/azure/notification-hubs/) ist eine plattformübergreifende, erweiterbare Pushinfrastruktur, die Ihnen ermöglicht, Pushbenachrichtigungen von Mobilgeräten von jedem Backend (in der Cloud oder lokal) zu jeder mobilen Plattform zu senden.

Azure Notification Hubs können mit F# auf zwei Arten verwendet werden:

1. Durch die Erstellung von Azure Functions in F#, wodurch Ergebnisse an Notification Hub gesendet werden. (Weitere Informationen finden Sie unter [Azure Functions Notification Hub-Ausgabebindung](https://docs.microsoft.com/azure/azure-functions/functions-bindings-notification-hubs) oder
2. Mithilfe der [.NET SDK für Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/). Beachten Sie, dass diese Beispiele in C# geschrieben sind.


## <a name="implementing-webhooks-on-azure-with-f"></a>Implementieren von WebHooks auf Azure mit F# #

Ein [Webhook](https://en.wikipedia.org/wiki/Webhook) ist ein Rückruf, der durch eine Webanfrage ausgelöst wird. Webhooks werden von Websites wie GitHub verwendet, um Ereignisse zu signalisieren. 

Webhooks können in F# implementiert und in Azure durch [HTTP- und Webhookbindungen in Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-bindings-http-webhook) gehostet werden.

## <a name="using-webjobs-with-f"></a>Verwendung von WebJobs mit F# #

[WebJobs](https://docs.microsoft.com/en-us/azure/app-service-web/web-sites-create-web-jobs) sind Programme, die Sie in Ihrer App Service-Web-App auf drei Arten ausführen können: bedarfsgesteuert, kontinuierlich oder zeitplanmäßig.

[Beispiel für F# WebJob](https://github.com/andredublin/fsharp-azure-webjob)

## <a name="implementing-timers-on-azure-with-f"></a>Implementieren von Timern in Azure mit F## #

Timer lösen Aufruffunktionen auf Grundlage eines Zeitplans, einmal oder wiederkehrend aus.

Timer können in F# implementiert und in Azure durch einen [Timerauslöser in Azure Functions in F#](https://docs.microsoft.com/azure/azure-functions/functions-bindings-timer) gehostet werden.

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a>Bereitstellen und Verwalten von Azure-Ressourcen mit F#-Skripts #

Azure-VMs können programmgesteuert bereitgestellt und von F#-Skripts mithilfe der Microsoft.Azure.Management-Pakete und APIs verwaltet werden. Bespiele finden Sie unter [Erste Schritte mit den Verwaltungsbibliotheken für .NET](https://msdn.microsoft.com/library/dn722415.aspx) und [Azure Resource Manager-Bereitstellung im Vergleich zur klassischen Bereitstellung: Grundlegendes zu Bereitstellungsmodellen und zum Status von Ressourcen](https://docs.microsoft.com/azure/azure-resource-manager/resource-manager-deployment-model).

Auch andere Azure-Ressourcen können möglicherweise auch von f#-Skripts bereitgestellt und verwaltet werden, die über die gleichen Komponenten verfügen. Beispielsweise können Sie Speicherkonten erstellen, Azure Cloud Services bereitstellen, Azure DocumentDB-Instanzen erstellen und Azure Notification Hubs programmgesteuert von F#-Skripts verwalten.

Die Verwendung von F#-Skripts zum Bereitstellen und Verwalten von Ressourcen ist normalerweise nicht notwendig. Beispielsweise können Azure-Ressourcen möglicherweise auch direkt von JSON-Vorlagebeschreibungen bereitgestellt werden, die parametrisiert werden können. Informationen, einschließlich Beispiele wie die [Azure-Schnellstartvorlagen](https://azure.microsoft.com/documentation/templates/), finden Sie unter [Bewährte Methoden für das Erstellen von Azure Resource Manager-Vorlagen](https://docs.microsoft.com/azure/azure-resource-manager/resource-manager-template-best-practices).

## <a name="other-resources"></a>Weitere Ressourcen

* [Die vollständige Dokumentation für alle Azure-Dienste](https://docs.microsoft.com/azure/)

