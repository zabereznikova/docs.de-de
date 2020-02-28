---
title: Merkmale moderner Webanwendungen
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Merkmale moderner Webanwendungen
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: d70fa54adeb505fd37807399402281dfda67cf52
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451563"
---
# <a name="characteristics-of-modern-web-applications"></a>Merkmale moderner Webanwendungen

> "… mit dem richtigen Design sind die Features leicht zu handhaben. Dieses Vorgehen ist mühselig, führt aber zum Erfolg.“  
> _\- Dennis Ritchie_

Bei modernen Webanwendungen haben die Benutzer hohe Erwartungen und größere Ansprüche als je zuvor. Heutige Webanwendungen sollen rund um die Uhr auf der ganzen Welt verfügbar und mit praktisch jeder Geräte- oder Bildschirmgröße verwendbar sein. Webanwendungen müssen sicher, flexibel und skalierbar sein, um den Anforderungen zu entsprechen. Komplexe Szenarios müssen zunehmend von einer umfassenden Benutzeroberfläche verarbeitet werden, die mit JavaScript auf dem Client basiert und effizient über Web-APIs kommuniziert.

ASP.NET Core ist für moderne Webanwendungen und cloudbasierte Hostingszenarios optimiert. Der modulare Aufbau ermöglicht es den Anwendungen, nur von den Features abhängig zu sein, die tatsächlich verwendet werden. Dies verbessert die Anwendungssicherheit und Leistung, während die Ressourcenanforderungen für das Hosting reduziert werden.

## <a name="reference-application-eshoponweb"></a>Referenzanwendung: eShopOnWeb

Der Leitfaden enthält auch eine Referenzanwendung, _eShopOnWeb_, die einige der Prinzipien und Empfehlungen demonstriert. Bei der Anwendung handelt es sich um einen einfachen Onlineshop, in dem man einen Katalog nach Shirts, Kaffeebechern und anderen Marketingartikeln durchsuchen kann. Die Referenzanwendung ist bewusst einfach gehalten, damit sie leicht verstanden werden kann.

![eShopOnWeb](./media/image2-1.png)

**Abbildung 2-1.** eShopOnWeb

> ### <a name="reference-application"></a>Referenzanwendung
>
> - **eShopOnWeb**  
>   <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Cloudbasiert und skalierbar

ASP.NET Core ist für die Cloud (öffentliche Cloud, private Cloud, jede andere Cloud) optimiert, da sie wenig Speicher benötigt, aber einen hohen Durchsatz hat. Der geringere Speicherbedarf von ASP.NET Core-Anwendungen bedeutet, dass Sie mehr als eine Anwendung auf der gleichen Hardware hosten können und für weniger Ressourcen bezahlen, wenn Sie die Cloudhostingdienste mit nutzungsbasierter Bezahlung verwenden. Aufgrund des hohen Durchsatzes können Sie mehr Kunden von einer Anwendung mit der gleichen Hardware bedienen und zusätzlich die Notwendigkeit reduzieren, in Server und Hostinginfrastruktur zu investieren.

## <a name="cross-platform"></a>Plattformübergreifend

ASP.NET Core ist plattformübergreifend und kann unter Linux, macOS und Windows ausgeführt werden. Dadurch entstehen viele neue Optionen für die Entwicklung und Bereitstellung von Apps, die mit ASP.NET Core erstellt werden. Docker-Container – sowohl unter Linux als auch unter Windows – können ASP.NET Core-Anwendungen ausführen und diesen ermöglichen, die Vorteile von [Containern und Microservices](../microservices/index.md) zu nutzen.

## <a name="modular-and-loosely-coupled"></a>Modular und lose gekoppelt

NuGet-Pakete sind wesentliche Bestandteile in .Net Core, und ASP.NET Core-Anwendungen werden aus vielen Bibliotheken über NuGet zusammengesetzt. Die Genauigkeit der Funktionen hilft bei der Gewährleistung, dass Apps nur von den Funktionen abhängen, die sie tatsächlich benötigen, und diese bereitstellen. Dadurch wird deren Speicherbedarf und die Oberfläche von Sicherheitsrisiken reduziert.

ASP.NET Core unterstützt auch vollumfänglich die [Abhängigkeitsinjektion](https://deviq.com/dependency-injection/), sowohl auf interner Ebene als auch auf Anwendungsebene. Schnittstellen verfügen über mehrere Implementierungen, die nach Bedarf ausgelagert werden können. Durch Abhängigkeitsinjektionen ist es möglich, Anwendungen eher lose an diese Schnittstellen zu koppeln als an bestimmte Implementierungen. Dies erleichtert das Erweitern, Verwalten und Testen der Anwendungen.

## <a name="easily-tested-with-automated-tests"></a>Problemloses Testen mit automatisierten Tests

ASP.NET Core-Anwendungen unterstützen Komponententests. Deren lose Kopplung und Unterstützung für Abhängigkeitsinjektionen erleichtern das Austauschen der Infrastrukturprobleme mit falschen Implementierungen zu Testzwecken. ASP.NET Core umfasst auch einen TestServer, der verwendet werden kann, um Anwendungen im Arbeitsspeicher zu hosten. Funktionstests können dann Anforderungen an diesen In-Memory-Server stellen, den vollständigen Anwendungsstapel ausführen (einschließlich Middleware, Routing, Modellbindung, Filter usw.) und eine Antwort erhalten. Dies alles geschieht in einem Bruchteil der Zeit, die benötigt werden würde, um die Anwendung auf einem echten Server zu hosten und Anforderungen über die Netzwerkschicht zu stellen. Diese Tests sind für APIs, die bei modernen Webanwendungen zunehmend wichtiger werden, besonders einfach zu schreiben und wertvoll.

## <a name="traditional-and-spa-behaviors-supported"></a>Herkömmliches Verhalten und SPA-Verhalten unterstützt

Herkömmliche Webanwendungen verfügen über wenig clientseitiges Verhalten. Stattdessen verlassen sie sich bei allen Navigationen, Abfragen und Updates, die die Anwendung benötigen könnte, auf den Server. Jeder neue vom Benutzer ausgeführte Vorgang würde in eine neue Webanforderung verschoben werden. Das Ergebnis wäre ein vollständiges Neuladen der Seite im Browser des Benutzers. Klassische MVC-Frameworks folgen normalerweise diesem Verfahren, bei dem jede neue Anforderung zu einer anderen Controlleraktion gehört, die wiederum mit einem Modell arbeiten und eine Ansicht zurückgeben würde. Einige individuelle Vorgänge auf einer vorhandenen Seite könnten mit der AJAX-Funktion (Asynchronous JavaScript And XML) erweitert werden, aber die Gesamtarchitektur der Anwendung hat viele verschiedene MVC-Ansichten und URL-Endpunkte verwendet. Zusätzlich unterstützt ASP.NET Core MVC auch Razor Pages, eine einfachere Möglichkeit zum Organisieren von Seiten im MVC-Stil.

Single-Page-Webanwendungen (SPAs) schließen dagegen wenige dynamisch erstellte serverseitige Ladevorgänge der Seite ein (sofern vorhanden). Viele SPAs werden innerhalb einer statischen HTML-Datei initialisiert, die die notwendigen JavaScript-Bibliotheken lädt, um die Anwendung zu starten und auszuführen. Diese Anwendungen führen zu einer hohen Auslastung der Web-APIs für deren Datenanforderungen und können für mehr Benutzerfreundlichkeit sorgen.

Viele Webanwendungen verfügen über eine Kombination aus den Verhaltensweisen von herkömmlichen Webanwendungen (normalerweise für Inhalte) und SPAs (für Interaktivität). ASP.NET Core unterstützt sowohl MVC-APIs (Ansichten oder seitenbasierte) als auch Web-APIs in derselben Anwendung. Dabei werden das gleiche Toolset und die gleichen zugrunde liegenden Frameworkbibliotheken verwendet.

## <a name="simple-development-and-deployment"></a>Einfache Entwicklung und Bereitstellung

ASP.NET Core-Anwendungen können mithilfe einfacher Text-Editoren und Befehlszeilenschnittstellen oder voll funktionsfähiger Entwicklungsumgebungen wie Visual Studio geschrieben werden. Monolithische Anwendungen werden normalerweise für einen einfachen Endpunkt bereitgestellt. Bereitstellungen können leicht automatisiert werden, um sie als Teil einer Continuous Integration (CI) und Continuous Delivery-Pipeline (CD) auftreten zu lassen. Zusätzlich zu den herkömmlichen CI-/CD-Tools bietet Microsoft Azure integrierte Unterstützung für Git-Repositorys und kann Updates automatisch bereitstellen, da diese für einen speziellen Git-Branch oder ein Git-Tag vorgesehen sind. Azure DevOps bietet eine voll ausgestattete CI/CD-Build- und Bereitstellungspipeline, und GitHub Actions ist eine weitere Option für dort gehostete Projekte.

## <a name="traditional-aspnet-and-web-forms"></a>ASP.NET und Web Forms (herkömmlich)

Neben ASP.NET Core ist das herkömmliche ASP.NET 4.x weiterhin eine stabile und zuverlässige Plattform zum Erstellen von Webanwendungen. ASP.NET unterstützt MVC- und Web-API-Entwicklungsmodelle sowie Web Forms, die gut für eine umfassende seitenbasierte Anwendungsentwicklung geeignet sind, und bietet eine umfangreiches Ökosystem für Drittanbieterkomponenten. Microsoft Azure bietet seit langem eine hervorragende Unterstützung für ASP.NET 4.x-Anwendungen, und viele Entwickler sind mit dieser Plattform vertraut.

## <a name="blazor"></a>Blazor

Blazor ist in ASP.NET Core 3.0 und höher enthalten. Das Tool bietet einen neuen Mechanismus zur Erstellung komplexer interaktiver Webclientanwendungen mit Razor, C# und ASP.NET Core. Es bietet eine weitere Lösung, die bei der Entwicklung moderner Webanwendungen berücksichtigt werden sollte. Es gibt zwei Versionen von Blazor: serverseitig und clientseitig.

Serverseitiges Blazor wurde 2019 mit ASP.NET Core 3.0 veröffentlicht. Wie der Name schon sagt, erfolgt die Ausführung auf dem Server, wobei Änderungen am Clientdokument über das Netzwerk an den Browser zurückgegeben werden. Serverseitiges Blazor bietet eine komplexe Clienterfahrung, ohne dass clientseitiges JavaScript erforderlich ist und ohne dass für jede Clientseiteninteraktion separate Seitenladevorgänge erforderlich sind. Änderungen an der geladenen Seite werden vom Server angefordert und von ihm verarbeitet und dann mittels SignalR an den Client zurückgesendet.

Clientseitiges Blazor wird 2020 veröffentlicht und macht das Rendern von Änderungen auf dem Server überflüssig. Stattdessen wird WebAssembly genutzt, um .NET-Code innerhalb des Clients auszuführen. Der Client kann weiterhin API-Aufrufe an den Server richten, um Daten anzufordern. Das gesamte clientseitige Verhalten erfolgt jedoch im Client über WebAssembly, das bereits von allen gängigen Browsern unterstützt wird und lediglich eine JavaScript-Bibliothek ist.

> ### <a name="references--modern-web-applications"></a>Ressourcen: Moderne Webanwendungen
>
> - **Einführung in ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/>
> - **Testen in ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Erste Schritte mit Blazor**  
>   <https://blazor.net/docs/get-started.html>

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](choose-between-traditional-web-and-single-page-apps.md)
