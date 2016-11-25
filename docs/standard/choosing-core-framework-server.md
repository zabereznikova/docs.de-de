---
title: "Wahl zwischen .NET Core und .NET Framework für Server-Apps"
description: "Ein Leitfaden für die Auswahl der NET-Konfiguration für die Erstellung einer Server-App in .NET."
keywords: .NET, .NET Core, .NET Framework
author: cartermp
manager: wpickett
ms.author: phcart
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 155553e4-89a2-418d-be88-4e75f6c3cc69
translationtype: Human Translation
ms.sourcegitcommit: d6ce9e3dd3c1189f35d147d140bb45095b3d77a5
ms.openlocfilehash: a0563f7437711ddbee309803e97ab653aa160337

---

# <a name="choosing-between-net-core-and-net-framework-for-server-apps"></a>Wahl zwischen .NET Core und .NET Framework für Server-Apps

Bei der Erstellung von serverseitigen Anwendungen mit .NET werden zwei Runtimeoptionen unterstützt: .NET Framework und .NET Core. Beide nutzen viele gemeinsame .NET-Plattformkomponenten, und bei beiden stimmt ein Teil des Codes überein. Allerdings gibt es auch grundlegende Unterschiede. Daher richtet sich Ihre Entscheidung danach, was Sie erreichen möchten.  Dieser Artikel stellt Anleitungen dazu bereit, welche Variante in welchen Fällen verwendet werden sollte.

In folgenden Fällen sollten Sie .NET Core für Ihre Serveranwendung verwenden:

* Es bestehen plattformübergreifende Anforderungen.
* Sie möchten Microservices erstellen.
* Sie verwenden Docker-Container.
* Sie sind auf skalierbare Hochleistungssysteme angewiesen.
* Sie müssen je nach Anwendung verschiedene .NET-Versionen parallel installieren.

In folgenden Fällen sollten Sie .NET Framework für Ihre Serveranwendung verwenden:

* Sie verwenden für Ihre Anwendung derzeit .NET Framework (empfohlen wird eine Erweiterung anstelle einer Migration).
* Sie sind auf die Verwendung von .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen angewiesen, die für .NET Core nicht verfügbar sind.
* Sie sind auf die Verwendung von .NET-Technologien angewiesen, die für .NET Core nicht verfügbar sind.
* Sie müssen eine Plattform verwenden, die .NET Core nicht unterstützt.

## <a name="when-to-choose-net-core"></a>In welchen Fällen sollte .NET Core verwendet werden?

Im Folgenden werden die zuvor genannten Gründe für die Entscheidung für .NET Core ausführlicher erläutert.

### <a name="cross-platform-needs"></a>Plattformübergreifende Anforderungen

Wenn eine Anwendung (Web/Dienst) plattformübergreifend (Windows, Linux und macOS) ausgeführt werden soll, ist .NET Core eindeutig die beste Wahl.

.NET Core unterstützt auch die zuvor genannten Betriebssysteme für Ihre Entwicklungsarbeitsstation. Visual Studio bietet eine integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) für Windows.  Sie können auch Visual Studio Code unter macOS, Linux und Windows verwenden. Diese Betriebssysteme bieten vollständige Unterstützung für .NET Core – einschließlich IntelliSense und Debugging. Sie können .NET Core auch mit den meisten Editoren von Drittanbietern verwenden, wie z.B. Sublime, Emacs oder VI, und Sie können IntelliSense-Editor-Funktionen mithilfe des Open Source-Projekts [Omnisharp](http://www.omnisharp.net/) nutzen. Da Sie die .NET Core-Befehlszeilentools direkt verwenden können, die für alle unterstützten Plattformen verfügbar sind, ist ein Code-Editor überflüssig.

### <a name="microservices-architecture"></a>Microservicearchitektur

.NET Core ist die beste Wahl, wenn Sie ein microservicezentriertes System aufbauen möchten, das aus mehreren unabhängigen, dynamisch skalierbaren, zustandsbehafteten oder zustandslosen Microservices besteht. .NET Core benötigt nur wenig Ressourcen, und die API-Oberfläche kann auf den Umfang des jeweiligen Microservice minimiert werden. Mit einer Microservicearchitektur können Sie außerdem Technologien dienstübergreifend miteinander kombinieren. So ermöglichen Sie eine graduelle Übernahme von .NET Core für neue Microservices, die in Verbindung mit anderen mithilfe von .NET Framework, Java, Ruby oder anderen monolithischen Technologien entwickelten Microservices oder Diensten verwendet werden.

Ihnen steht eine Vielzahl verschiedener Infrastrukturplattformen zur Verfügung. Für große und komplexe Microservicesysteme können Sie [Azure Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) verwenden. Für zustandslose Microservices können Sie auch andere Produkte verwenden, z.B. [Azure App Service](https://azure.microsoft.com/en-us/services/app-service/). Auf Docker basierende Alternativen zu Microservices sind – wie nachstehend erläutert – mit allen Arten von Microservice-Implementierungen kompatibel. All diese Plattformen unterstützen .NET Core und eignen sich daher ideal zum Hosten Ihrer Microservices.

### <a name="containers"></a>Container

Container werden häufig in Verbindung mit einer Microservicearchitektur eingesetzt, obwohl sie auch für Web-Apps oder Dienste mit jedem beliebigen Architekturmuster verwendet werden können. .NET Framework lässt sich auch für Windows-Container verwenden, allerdings eignet sich .NET Core durch die Modularität und den einfachen Aufbau ideal für Container.  Die Imagegröße eines mit .NET Core erstellten und bereitgestellten Containers ist wesentlich kleiner als bei .NET Framework.  Aufgrund der plattformübergreifenden Struktur können Sie Server-Apps zum Beispiel in Linux-Docker-Containern bereitstellen.

Sie können dann Ihre Docker-Container in Ihrer eigenen Linux- oder Windows-Infrastruktur hosten oder einen Clouddienst nutzen, z.B. [Azure Container Service](https://azure.microsoft.com/en-us/services/container-service/), mit dem Ihre containerbasierte Anwendung in der Cloud verwaltet, orchestriert und skaliert werden kann.

### <a name="a-need-for-high-performance-and-scalable-systems"></a>Bedarf an skalierbaren Hochleistungssystemen

Wenn Sie für Ihr System die bestmögliche Leistung und Skalierbarkeit benötigen, sind .NET Core und ASP.NET Core die besten Optionen für Sie. ASP.NET Core ist im Vergleich zu ASP.NET um ein Zehnfaches leistungsfähiger und steht im Vergleich zu anderen bekannten Branchentechnologien für Microservices, wie Java Servlets, Go und Node.js, an der Spitze.

Dies betrifft insbesondere Microservicearchitekturen, in denen Hunderte von Microservices ausgeführt werden können. Mit ASP.NET Core können Sie Ihr System mit einer wesentlich geringeren Anzahl von Servern/VMs ausführen und damit letztendlich Kosten für Infrastruktur und Hosting einsparen.

### <a name="a-need-for-side-by-side-of-net-versions-per-application-level"></a>Bedarf an parallel ausführbaren .NET-Versionen pro Anwendungsebene

Wenn Sie Anwendungen mit Abhängigkeiten von verschiedenen Frameworkversionen in .NET installieren möchten, müssen Sie .NET Core verwenden, das Ihnen eine vollständig parallele Ausführung ermöglicht. Die einfache parallele Installation verschiedener Versionen von .NET Core auf demselben Computer ermöglicht Ihnen, mehrere Dienste auf demselben Server zu hosten, wobei jeder dieser Dienste in seiner eigenen Version von .NET Core ausgeführt wird. So vermeiden Sie Risiken und sparen Kosten für Anwendungsupgrades und IT-Vorgänge.

## <a name="when-to-choose-net-framework"></a>In welchen Fällen sollte .NET Framework verwendet werden?

Während .NET Core erhebliche Vorteile für neue Anwendungen und Anwendungsmuster bietet, ist .NET Framework nach wie vor erste Wahl für viele vorhandene Szenarien. Daher ist eine Verdrängung durch .NET Core für sämtliche Serveranwendungen nicht abzusehen.

### <a name="current-net-framework-applications"></a>Vorhandene .NET Framework-Anwendungen

In den meisten Fällen müssen Sie Ihre vorhandenen Anwendungen nicht zu .NET Core migrieren. Stattdessen wird die Verwendung von .NET Core empfohlen, wenn Sie eine vorhandene Anwendung erweitern möchten, z.B. durch Schreiben eines neuen Webdiensts in ASP.NET Core.

### <a name="a-need-to-use-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Notwendigkeit von .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen, die für .NET Core nicht verfügbar sind

.NET Standard kommt in Bibliotheken immer häufiger zum Einsatz und ermöglicht die gemeinsame Nutzung von Code in allen .NET-Varianten einschließlich .NET Core. Mit .NET Standard 2.0 wird dies noch einfacher, weil die .NET Core API-Oberfläche wesentlich größer wird und .NET Core-Anwendungen vorhandene .NET Framework-Bibliotheken direkt verwenden können. Dieser Übergang erfolgt allerdings nicht sofort. Daher wird empfohlen, die Bibliotheken, die für Ihre Anwendungen erforderlich sind, genau zu prüfen, bevor Sie sich für einen Weg entscheiden.

### <a name="a-need-to-use-net-technologies-not-available-for-net-core"></a>Notwendigkeit von .NET-Technologien, die für .NET Core nicht verfügbar sind

Einige .NET Framework-Technologien sind in .NET Core nicht verfügbar. Manche dieser Technologien werden in höheren .NET Core-Versionen verfügbar sein. Andere können jedoch für die neuen Anwendungsmuster, auf die .NET Core abzielt, nicht verwendet werden und werden möglicherweise nie verfügbar sein. Die folgende Liste enthält die häufigsten Technologien, die von .NET Core 1.0 nicht unterstützt werden:

* ASP.NET Web Forms-Anwendungen: ASP.NET Web Forms ist nur in .NET Framework verfügbar, daher können Sie ASP.NET Core bzw. .NET Core für dieses Szenario nicht verwenden. Eine Integration von ASP.NET Web Forms in .NET Core ist zurzeit nicht geplant.

* ASP.NET Web Pages-Anwendungen: ASP.NET Web Pages ist in ASP.NET Core 1.0 nicht enthalten. Die Integration in künftige Versionen ist jedoch geplant, wie in der [Roadmap für .NET Core](https://github.com/aspnet/Home/wiki/Roadmap) erläutert.

* Implementierung von ASP.NET SignalR-Server/-Client. Im Veröffentlichungszeitrahmen für .NET Core 1.0 (Juni 2016) ist ASP.NET SignalR für ASP.NET Core nicht verfügbar (weder Client noch Server). Die Integration in künftige Versionen ist jedoch geplant, wie in der [Roadmap für .NET Core](https://github.com/aspnet/Home/wiki/Roadmap) erläutert. Die Vorschau ist für die GitHub-Repositorys sowohl für die [Serverseite](https://github.com/aspnet/SignalR-Server) als auch für die [Clientbibliotheken](https://github.com/aspnet/SignalR-Client-Net) verfügbar.

* Implementierung von WCF-Diensten. Auch wenn WCF-Dienste über eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) von .NET Core genutzt werden, ist die WCF-Serverimplementierung ab Juni 2016 nur in .NET Framework verfügbar. Dieses Szenario ist nicht Bestandteil der derzeitigen Pläne für .NET Core, wird jedoch für die Zukunft in Betracht gezogen.

* Workflowbezogene Dienste: Windows Workflow Foundation (WF), Workflow Services (WCF + WF in einem einzigen Dienst) und WCF Data Services (zuvor bekannt als „ADO.NET Data Services“) sind nur in .NET Framework verfügbar, und eine Integration in .NET Core ist nicht geplant.

* Sprachunterstützung: Visual Basic und F# verfügen derzeit über keine Toolunterstützung für .NET Core, beide Sprachen werden jedoch in Visual Studio 2017 und höheren Versionen von Visual Studio unterstützt.

Zusätzlich zur offiziellen Roadmap gibt es andere Frameworks, die in .NET Core portiert werden sollen. Eine vollständige Liste finden Sie auf GitHub bei den „Issues“ zu CoreFX, die als [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) gekennzeichnet sind. Beachten Sie, dass diese Liste keine Verpflichtung für Microsoft darstellt, diese Komponenten in .NET Core zu integrieren. Die Liste sammelt lediglich die Wünsche der Community, solche Komponenten einzuführen. Wenn Sie sich für eine der oben aufgeführten Komponenten interessieren, können Sie sich gerne auf GitHub an den Diskussionen beteiligen. Wenn Ihrer Ansicht nach noch etwas fehlt, [eröffnen Sie im CoreFX Repository ein neues „Issue“](https://github.com/dotnet/corefx/issues/new).

### <a name="a-need-to-use-a-platform-that-doesnt-support-net-core"></a>Notwendigkeit einer Plattform, die .NET Core nicht unterstützt

Einige Plattformen von Microsoft oder Drittanbietern unterstützen .NET Core nicht. Zum Beispiel wird für einige Azure-Dienste, wie z.B. Service Fabric Stateful Reliable Services und Service Fabric Reliable Actors, .NET Framework benötigt. Einige andere Dienste stellen ein SDK bereit, das noch nicht für die Nutzung in .NET Core verfügbar ist. Dies ist allerdings nur vorübergehend der Fall, weil .NET Core von sämtlichen Azure-Diensten verwendet wird. In der Zwischenzeit können Sie anstelle des Client-SDKs stets die entsprechende REST-API verwenden.

## <a name="further-resources"></a>Weitere Ressourcen

* [Leitfaden für .NET Core](../core/index.md)
* [Portieren von .NET Framework zu .NET Core](../core/porting/index.md)
* [Leitfaden zu .NET Framework in Docker](../framework/index.md)
* [.NET-Komponenten – Übersicht](components.md)


<!--HONumber=Nov16_HO3-->


