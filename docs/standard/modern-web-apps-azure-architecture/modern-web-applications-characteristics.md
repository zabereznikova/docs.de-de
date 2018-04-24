---
title: Merkmale moderner Webanwendungen
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Merkmale moderner Webanwendungen
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4f12b6860f1c4efe0f55cae4fefd8cd5f4539095
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="characteristics-of-modern-web-applications"></a>Merkmale moderner Webanwendungen

> "… mit dem richtigen Design sind die Features leicht zu handhaben. Dieses Vorgehen ist mühselig, führt aber zum Erfolg.“  
> _\- Dennis Ritchie_

## <a name="summary"></a>Zusammenfassung

Bei modernen Webanwendungen haben die Benutzer hohe Erwartungen und größere Ansprüche als je zuvor. Heutige Webanwendungen sollen rund um die Uhr auf der ganzen Welt verfügbar und mit praktisch jeder Geräte- oder Bildschirmgröße verwendbar sein. Webanwendungen müssen sicher, flexibel und skalierbar sein, um den Anforderungen zu entsprechen. Komplexe Szenarios müssen zunehmend von einer umfassenden Benutzeroberfläche verarbeitet werden, die mit JavaScript auf dem Client basiert und effizient über Web-APIs kommuniziert.

ASP.NET Core ist für moderne Webanwendungen und cloudbasierte Hostingszenarios optimiert. Der modulare Aufbau ermöglicht es den Anwendungen, nur von den Features abhängig zu sein, die tatsächlich verwendet werden. Dies verbessert die Anwendungssicherheit und Leistung, während die Ressourcenanforderungen für das Hosting reduziert werden.

## <a name="reference-application-eshoponweb"></a>Referenzanwendung: eShopOnWeb

Der Leitfaden enthält auch eine Referenzanwendung, *eShopOnWeb*, die einige der Prinzipien und Empfehlungen demonstriert. Bei der Anwendung handelt es sich um einen einfachen Onlineshop, in dem man einen Katalog nach Shirts, Kaffeebechern und anderen Marketingartikeln durchsuchen kann. Die Referenzanwendung ist bewusst einfach gehalten, damit sie leicht verstanden werden kann.

**Abbildung 2-1.** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>Referenzanwendung
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Cloudbasiert und skalierbar

ASP.NET Core ist für die Cloud (öffentliche Cloud, private Cloud, jede andere Cloud) optimiert, da sie wenig Speicher benötigt, aber einen hohen Durchsatz hat. Der geringere Speicherbedarf von ASP.NET Core-Anwendungen bedeutet, dass Sie mehr als eine Anwendung auf der gleichen Hardware hosten können und für weniger Ressourcen bezahlen, wenn Sie die Cloudhostingdienste mit nutzungsbasierter Bezahlung verwenden. Aufgrund des hohen Durchsatzes können Sie mehr Kunden von einer Anwendung mit der gleichen Hardware bedienen und zusätzlich die Notwendigkeit reduzieren, in Server und Hostinginfrastruktur zu investieren.

## <a name="cross-platform"></a>Plattformübergreifend

ASP.NET Core ist plattformübergreifend und kann unter Linux, MacOS und Windows ausgeführt werden. Dadurch entstehen viele neue Optionen für die Entwicklung und Bereitstellung von Apps, die mit ASP.NET Core erstellt werden. Docker-Container, die heutzutage normalerweise Linux ausführen, können ASP.NET Core-Anwendungen ausführen und diesen ermöglichen, die Vorteile von [Containern und Microservices](../microservices-architecture/index.md) zu nutzen.

## <a name="modular-and-loosely-coupled"></a>Modulare und lose Kopplung

NuGet-Pakete sind wesentliche Bestandteile in .Net Core, und ASP.NET Core-Anwendungen werden aus vielen Bibliotheken über NuGet zusammengesetzt. Die Genauigkeit der Funktionen hilft bei der Gewährleistung, dass Apps nur von den Funktionen abhängen, die sie tatsächlich benötigen, und diese bereitstellen. Dadurch wird deren Speicherbedarf und die Oberfläche von Sicherheitsrisiken reduziert.

ASP.NET Core unterstützt auch vollumfänglich die Abhängigkeitsinjektion, sowohl auf interner Ebene als auch auf Anwendungsebene. Schnittstellen verfügen über mehrere Implementierungen, die nach Bedarf ausgelagert werden können. Abhängigkeitsinjektionen ermöglichen es Anwendungen, an diese Schnittstellen zu koppeln. Dies erleichtert das Erweitern, Verwalten und Testen.

## <a name="easily-tested-with-automated-tests"></a>Problemloses Testen mit automatisierten Tests

ASP.NET Core-Anwendungen unterstützen Komponententests, und deren lose Kopplung und Unterstützung für Abhängigkeitsinjektionen erleichtert das Austauschen der Infrastrukturprobleme mit falschen Implementierungen zu Testzwecken. ASP.NET Core umfasst auch einen TestServer, der verwendet werden kann, um Anwendungen im Arbeitsspeicher zu hosten. Funktionstests können dann Anforderungen an diesen In-Memory-Server stellen, den vollständigen Anwendungsstapel ausführen (einschließlich Middleware, Routing, Modellbindung, Filter usw.) und eine Antwort erhalten. Dies alles geschieht in einem Bruchteil der Zeit, die benötigt werden würde, um die Anwendung auf einem echten Server zu hosten und Anforderungen über die Netzwerkschicht zu stellen. Diese Tests sind für APIs, die bei modernen Webanwendungen zunehmend wichtiger werden, besonders einfach zu schreiben und wertvoll.

## <a name="traditional-and-spa-behaviors-supported"></a>Unterstützte herkömmliche Verhaltensweisen und SPA-Verhaltensweisen

Herkömmliche Webanwendungen verfügen über wenig clientseitiges Verhalten. Stattdessen verlassen sie sich bei allen Navigationen, Abfragen und Updates, die die Anwendung benötigen könnte, auf den Server. Jeder neue vom Benutzer ausgeführte Vorgang würde in eine neue Webanforderung verschoben werden. Das Ergebnis wäre ein vollständiges Neuladen der Seite im Browser des Benutzers. Klassische MVC-Frameworks folgen normalerweise diesem Verfahren, bei dem jede neue Anforderung zu einer anderen Controlleraktion gehört, die wiederum mit einem Modell arbeiten und eine Ansicht zurückgeben würde. Einige individuelle Vorgänge auf einer vorhandenen Seite könnten mit der AJAX-Funktion (Asynchronous JavaScript And XML) erweitert werden, aber die Gesamtarchitektur der Anwendung hat viele verschiedene MVC-Ansichten und URL-Endpunkte verwendet.

Single-Page-Webanwendungen (SPAs) schließen dagegen wenige dynamisch erstellte serverseitige Ladevorgänge der Seite ein (sofern vorhanden). Viele SPAs werden innerhalb einer statischen HTML-Datei initialisiert, die die notwendigen JavaScript-Bibliotheken lädt, um die Anwendung zu starten und auszuführen. Diese Anwendungen führen zu einer hohen Auslastung der Web-APIs für deren Datenanforderungen und können für mehr Benutzerfreundlichkeit sorgen.

Viele Webanwendungen verfügen über eine Kombination aus den Verhaltensweisen von herkömmlichen Webanwendungen (normalerweise für Inhalte) und SPAs (für Interaktivität). ASP.NET Core unterstützt sowohl MVC- als auch Web-APIs in der gleichen Anwendung und verwendet das gleiche Toolset und die gleichen zugrunde liegenden Frameworkbibliotheken.

## <a name="simple-development-and-deployment"></a>Einfache Entwicklung und Bereitstellung

ASP.NET Core-Anwendungen können mithilfe von einfachen Text-Editoren und Befehlszeilenschnittstellen oder mit voll funktionsfähigen Entwicklungsumgebungen wie Visual Studio geschrieben werden. Monolithische Anwendungen werden normalerweise für einen einfachen Endpunkt bereitgestellt. Bereitstellungen können leicht automatisiert werden, um sie als Teil einer Continuous Integration (CI) und Continuous Delivery-Pipeline (CD) auftreten zu lassen. Zusätzlich zu den traditionellen CI-/CD-Tools verfügt Microsoft Azure über einen integrierten Support für Git-Repositorys und kann Updates automatisch bereitstellen, da diese für einen speziellen Git-Branch oder -Tag vorgesehen sind.

## <a name="traditional-aspnet-and-web-forms"></a>ASP.NET und Web Forms (herkömmlich)

Neben ASP.NET Core ist das herkömmliche ASP.NET 4.x weiterhin eine stabile und zuverlässige Plattform zum Erstellen von Webanwendungen. ASP.NET unterstützt MVC- und Web-API-Entwicklungsmodelle sowie Web Forms, das gut für eine umfassende seitenbasierte Anwendungsentwicklung geeignet ist, und bietet eine umfangreiches Ökosystem für Drittanbieterkomponenten. Windows Azure verfügt über einen guten, langfristigen Support für ASP.NET 4.x-Anwendungen, und viele Entwickler sind mit dieser Plattform vertraut.

> ### <a name="references--modern-web-applications"></a>Ressourcen: Moderne Webanwendungen
> - **Einführung in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/>
> - **Six Key Benefits of ASP.NET Core which make it Different and Better (Sechs Hauptvorteile von ASP.NET Core, die es anders und besser machen)**  
> <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - **Testen in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
[Zurück] (index.md) [Weiter] (choose-between-traditional-web-and-single-page-apps.md)
