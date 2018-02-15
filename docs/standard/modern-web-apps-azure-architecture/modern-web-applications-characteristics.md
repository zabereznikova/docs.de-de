---
title: Merkmale der modernen Webanwendungen
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Merkmale der modernen Webanwendungen
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecef23870ac547f4b4066628da71f8af98c91b27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="characteristics-of-modern-web-applications"></a>Merkmale der modernen Webanwendungen

> "… ordnungsgemäßen entwerfen die im Lieferumfang der Funktionen zu zweit. Dieser Ansatz ist damit den mühseligen, jedoch weiterhin erfolgreich ausgeführt werden."  
> _\- Dennis Ritchie_

## <a name="summary"></a>Zusammenfassung

Innovative Webanwendungen verfügen über höhere Erwartungen der Benutzer und mehr Anforderungen als jemals zuvor. Heute Web-apps werden verfügbare 24/7 von an einer beliebigen Stelle in der ganzen Welt und von praktisch jedem Gerät verwendet werden kann oder Displaygröße erwartet. Webanwendungen muss sichere, flexible und skalierbare, um Spitzen in der Anforderung zu erfüllen. Zunehmend sollten komplexe Szenarien durch umfangreiche Benutzeroberflächen, die auf dem Client mithilfe von JavaScript und effiziente Kommunikation über Web-APIs erstellt verarbeitet werden.

ASP.NET Core ist für die modernen Webanwendungen und Cloud-basierten Hostingszenarien optimiert. Der modularen Aufbau ermöglicht Anwendungen nur die Funktionen abhängig, die sie tatsächlich verwenden, Verbessern der Sicherheit der Anwendung und die Leistung beim hosting ressourcenanforderungen reduziert.

## <a name="reference-application-eshoponweb"></a>Verweisen auf die Anwendung: eShopOnWeb

Dieser Leitfaden enthält eine Referenz-Anwendung, *eShopOnWeb*, veranschaulicht, dass einige der Prinzipien und Empfehlungen. Die Anwendung ist eine einfache Onlineshop unterstützt einen Katalog von Hemden Kaffeetassen und andere marketing Elemente durchsuchen. Die Verweis-Anwendung ist absichtlich einfach gehalten, um ihn leichter nachvollziehen können.

**Abbildung 2-1.** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>Referenz-Anwendung
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Cloudgehosteten und skalierbare

ASP.NET Core ist für die Cloud (öffentliche Cloud, private Cloud, keiner Cloud) optimiert, da es sich um Arbeitsspeicherstatus niedrig zu halten und hohem Durchsatz handelt. Die kleinere Ressourcenbedarf des ASP.NET Core Anwendungen bedeutet, dass können mehrere dieser Header auf derselben Hardware gehostet und Sie weniger Ressourcen bezahlen, wenn unter Verwendung der Pay-als wechseln Sie zum Hosten von Diensten. Die Durchsätze bedeutet, dass Sie mehr Kunden aus einer Anwendung erhält die gleiche Hardware weiter mindert die Notwendigkeit, die bei Servern und hosting-Infrastruktur zu investieren dienen können.

## <a name="cross-platform"></a>Plattformübergreifend

ASP.NET Core plattformübergreifende ist und auf Linux und MacOS sowie Windows ausgeführt werden kann. Viele neue Optionen für Entwicklung und Bereitstellung von apps mit ASP.NET Core wird geöffnet. Docker-Container, der in der Regel Linux derzeit ausgeführt wird, können als host für ASP.NET Core-Anwendungen, sodass sie die Vorteile nutzen [Container und Microservices](../microservices-architecture/index.md).

## <a name="modular-and-loosely-coupled"></a>Modulare und lose

NuGet-Pakete sind hohem Maße für Webdaten in .NET Core und ASP.NET Core apps bestehen viele Bibliotheken über NuGet. Dieser Granularität Funktionen trägt dazu bei apps nur abhängig und Funktionalität, die sie tatsächlich ihre Platzbedarf und Sicherheit Sicherheitsrisiko Oberfläche verringert benötigen, bereitstellen.

ASP.NET Core unterstützt auch vollständig Abhängigkeitsinjektion, intern sowohl auf Anwendungsebene. Schnittstellen können mehrere Implementierungen aufweisen, die ausgelagert werden können nach Bedarf. Abhängigkeitsinjektion kann apps für lose miteinander verknüpfen, die diese Schnittstellen, sodass sie einfacher zu erweitern, zu verwalten und zu testen.

## <a name="easily-tested-with-automated-tests"></a>Problemlos mit automatisierten Tests getestet.

ASP.NET Core-Anwendungen unterstützen Komponententests und ihre Anzahl lose verbundener Einzelsysteme und Unterstützung für Abhängigkeit einfügungen erleichtert Aspekte, die Infrastruktur gefälschte Implementierungen für Testzwecke austauschen. ASP.NET Core umfasst auch einen TestServer, die als Host-apps im Arbeitsspeicher verwendet werden kann. Funktionstests können anschließend Anfragen an in-Memory-Server, den vollständigen Anwendungszugriff Stapel (einschließlich Middleware, routing, modellbindung, Filter usw.)-Code und Empfangen einer Antwort in einem Bruchteil der Zeit würde es dauern zum Hosten der Anwendung auf einem echten server und stellen Sie Anforderungen über die Ebene des Netzwerks. Diese Tests sind besonders leicht zu schreiben und wertvolle für APIs, die zunehmend wichtig sind in modernen Webanwendungen.

## <a name="traditional-and-spa-behaviors-supported"></a>Herkömmliche und unterstützt SPA-Verhalten

Herkömmliche Webanwendungen haben wenig clientseitige Verhalten beteiligt, aber stattdessen verlassen haben, auf dem Server für alle Navigation, Abfragen und Updates, die von die app vorgenommen werden müssen. Jede neue Operation, die vom Benutzer vorgenommene würde in eine neue webanforderung mit dem Ergebnis wird eine vollständige Seite neu laden im Browser des Benutzers, der das Ende übersetzt werden. Klassische Model-View-Controller (MVC)-Frameworks folgen dieser Ansatz in der Regel mit der jede neue Anforderung für eine andere Controlleraktion, die wiederum würde und Arbeiten mit einem Modell eine Ansicht zurückgeben. Einige einzelne Vorgänge in einer gegebenen Seite möglicherweise mit AJAX (Asynchronous JavaScript and XML)-Funktionen erweitert werden, aber der Gesamtarchitektur der app verwendet werden, viele verschiedene MVC-Ansichten und URL-Endpunkte.

Single Page Applications (SPAs), umfassen, im Gegensatz dazu nur sehr wenige Laden von dynamisch generierten serverseitige-Seite (sofern vorhanden). Viele SPAs werden in statische HTML-Datei initialisiert, die die erforderlichen JavaScript-Bibliotheken zum Starten und Ausführen der app lädt. Diese apps stellen beanspruchter Web-APIs für ihren Anforderungen hinsichtlich der Daten, und stellen viel umfangreichere Benutzer bereitstellen können.

Viele Webanwendungen erfordern eine Kombination des Verhalten der herkömmlichen Web-Anwendung (in der Regel für Inhalt) und SPAs (für Interaktivität). ASP.NET Core unterstützt MVC und Web-APIs in der gleichen Anwendung verwenden den gleichen Satz von Tools und zugrunde liegende Framework-Bibliotheken.

## <a name="simple-development-and-deployment"></a>Einfache Entwicklung und Bereitstellung

ASP.NET Core-Anwendungen können mithilfe von einfachen Text-Editoren und Befehlszeilenschnittstellen oder voll ausgestatteten entwicklungsumgebungen wie Visual Studio geschrieben werden. Aufgrund eines monolithischen Anwendungen werden in der Regel einen einzelnen Endpunkt bereitgestellt. Bereitstellungen können leicht automatisiert werden, um Sie als Teil einer continuous Integration (CI) und die Pipeline für fortlaufende Übermittlung (CD) auftreten. Zusätzlich zu den herkömmlichen CI-CD-Tools Windows Azure verfügt über eine integrierte Unterstützung für Git-Repositorys und Updates können automatisch bereitgestellt werden, wenn sie an einem angegebenen Git Verzweigung oder Tag beziehen.

## <a name="traditional-aspnet-and-web-forms"></a>Herkömmliche ASP.NET und WebForms

Zusätzlich zu ASP.NET Core, herkömmlichen ASP.NET 4.x weiterhin eine robuste und zuverlässige Plattform zum Erstellen von Webanwendungen. ASP.NET unterstützt MVC und Web-API Entwicklungsmodellen sowie Web Forms, die sich gut für umfassende seitenbasierte Anwendungsentwicklung und verfügt über eine umfangreiche Drittanbieter-Komponente-Ökosystem. Windows Azure bietet hervorragende befolgter Unterstützung für ASP.NET 4.x-Anwendungen, und viele Entwickler mit dieser Plattform vertraut sind.

> ### <a name="references--modern-web-applications"></a>Verweise – moderner Webanwendungen
> - **Einführung in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/>
> - **Sechs Schlüssel Vorteile von ASP.NET Core, die anders und besser zu vereinfachen**  
> <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - **Testen in ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Choose-between-traditional-web-and-single-page-apps.md)
