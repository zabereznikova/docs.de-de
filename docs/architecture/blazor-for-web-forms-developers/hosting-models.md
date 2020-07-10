---
title: BlazorApp-Hostingmodelle
description: Erfahren Sie mehr über die verschiedenen Möglichkeiten zum Hosten einer- Blazor app, einschließlich im Browser auf WebAssembly oder auf dem Server.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: a0d37392a65cfcbff9642476d9fdb1e5c662e66a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173262"
---
# <a name="blazor-app-hosting-models"></a>BlazorApp-Hostingmodelle

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

BlazorApps können genauso wie ASP.net Web Forms-apps in IIS gehostet werden. BlazorApps können auch auf eine der folgenden Arten gehostet werden:

- Client seitig im Browser auf WebAssembly .
- Server seitig in einer ASP.net Core-app.

## <a name="blazor-webassembly-apps"></a>BlazorWebAssemblyapps

BlazorWebAssemblyapps werden direkt im Browser auf einer WebAssembly -basierten .NET-Laufzeit ausgeführt. BlazorWebAssemblyapps funktionieren auf ähnliche Weise wie Front-End-JavaScript-Frameworks wie Angular oder reagieren. Anstatt jedoch JavaScript zu schreiben, schreiben Sie c#. Die .NET-Laufzeit wird zusammen mit der APP-Assembly und allen erforderlichen Abhängigkeiten mit der App heruntergeladen. Es sind keine Browser-Plug-ins oder Erweiterungen erforderlich.

Die heruntergeladenen Assemblys sind normale .NET-Assemblys, wie Sie in jeder anderen .net-App verwenden würden. Da die Common Language Runtime .NET Standard unterstützt, können Sie vorhandene .NET Standard Bibliotheken mit Ihrer Blazor WebAssembly App verwenden. Diese Assemblys werden jedoch weiterhin im Browser-Sicherheits Sandbox ausgeführt. Einige Funktionen lösen möglicherweise einen aus <xref:System.PlatformNotSupportedException> , z. b. den Zugriff auf das Dateisystem oder das Öffnen beliebiger Netzwerkverbindungen.

Wenn die App geladen wird, wird die .NET-Laufzeit gestartet, und es wird auf die APP-Assembly verwiesen. Die APP-Start Logik wird ausgeführt, und die Stamm Komponenten werden gerendert. Blazorberechnet die Aktualisierungen der Benutzeroberfläche auf der Grundlage der gerenderten Ausgabe der Komponenten. Anschließend werden die DOM-Updates angewendet.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

BlazorWebAssemblyAnwendungen werden nur auf Clientseite ausgeführt. Solche Apps können für statische Site Hosting-Lösungen wie GitHub-Seiten oder das Hosting von Azure Static-Websites bereitgestellt werden. .Net ist auf dem Server nicht erforderlich. Die Tiefe Verknüpfung mit den Teilen der APP erfordert in der Regel eine Routing Lösung auf dem Server. Die Routing Lösung leitet Anforderungen an den Stamm der App um. Diese Umleitung kann beispielsweise mithilfe von URL-Rewrite-Regeln in IIS verarbeitet werden.

BlazorHosten Sie Ihre Blazor App mit ASP.net Core, um alle Vorteile der .net-Webentwicklung mit vollständiger Stapel Menge zu erhalten WebAssembly . Wenn Sie .net sowohl auf dem Client als auch auf dem Server verwenden, können Sie Code problemlos freigeben und die App mithilfe eines konsistenten Satzes von Sprachen, Frameworks und Tools erstellen. Blazorbietet praktische Vorlagen zum Einrichten einer Projekt Mappe, die sowohl eine Blazor WebAssembly -App als auch ein ASP.net Core-Host Projekt enthält. Wenn die Lösung erstellt wird, werden die erstellten statischen Dateien aus der Blazor App von der ASP.net Core-App gehostet, wobei das Fall Back Routing bereits eingerichtet ist.

## <a name="blazor-server-apps"></a>BlazorServer-apps

Erinnern Sie sich aus der [ Blazor Architektur](architecture-comparison.md#blazor) Diskussion, dass Blazor Komponenten Ihre Ausgabe in eine zwischen Abstraktion mit dem Namen renderingrenden `RenderTree` Das Blazor Framework vergleicht dann, was gerendert wurde, was zuvor gerendert wurde. Die Unterschiede werden auf das DOM angewendet. BlazorKomponenten sind von der Anwendung ihrer gerenderten Ausgabe entkoppelt. Folglich müssen die Komponenten selbst nicht in demselben Prozess ausgeführt werden wie der Prozess, der die Benutzeroberfläche aktualisiert. Tatsächlich müssen Sie nicht einmal auf dem gleichen Computer ausgeführt werden.

In Blazor Server-apps werden die Komponenten auf dem Server anstelle der Clientseite im Browser ausgeführt. Benutzeroberflächen Ereignisse, die im Browser auftreten, werden über eine Echtzeitverbindung an den Server gesendet. Die Ereignisse werden an die richtigen Komponenten Instanzen weitergeleitet. Die Komponenten werden gerbt, und der berechnete UI-diff wird serialisiert und an den Browser gesendet, in dem Sie auf das DOM angewendet wird.

![BlazorServers](media/hosting-models/blazor-server.png)

Das Blazor Hostingmodell des Servers ist möglicherweise vertraut, wenn Sie ASP.NET AJAX und das-Steuerelement verwendet haben <xref:System.Web.UI.UpdatePanel> . Das- `UpdatePanel` Steuerelement übernimmt das Anwenden partieller Seiten Aktualisierungen als Reaktion auf Triggerereignisse auf der Seite. Wenn Sie ausgelöst wird, `UpdatePanel` fordert eine partielle Aktualisierung an und wendet Sie dann an, ohne die Seite aktualisieren zu müssen. Der Status der Benutzeroberfläche wird mithilfe von verwaltet `ViewState` . BlazorServer-apps unterscheiden sich geringfügig insofern, als die APP eine aktive Verbindung mit dem Client erfordert. Außerdem wird der gesamte Status der Benutzeroberfläche auf dem Server beibehalten. Abgesehen von diesen Unterschieden sind die beiden Modelle konzeptionell ähnlich.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Auswählen des richtigen Blazor Hostingmodells

Wie in der Dokumentation des [ Blazor Hostingmodells](/aspnet/core/blazor/hosting-models)beschrieben, Blazor haben die verschiedenen Hostingmodelle unterschiedliche Kompromisse.

Das Blazor WebAssembly Hostingmodell bietet die folgenden Vorteile:

- Es besteht keine serverseitige .NET-Abhängigkeit. Die APP funktioniert nach dem Herunterladen auf den Client vollständig.
- Die Ressourcen und Funktionen des Clients werden voll genutzt.
- Die Arbeit wird vom Server auf den Client verlagert.
- Es ist kein ASP.NET Core-Webserver zum Hosten der App erforderlich. Serverlose Bereitstellungsszenarios sind möglich (z. B. das Bereitstellen der App aus einem CDN).

Die Nachteile des Blazor WebAssembly Hostingmodells lauten:

- Browser Funktionen schränken die APP ein.
- Kompatible Client Hardware und Software (z. b WebAssembly . Support) sind erforderlich.
- Die Downloadmenge ist größer und die Ladezeit der Apps länger.
- Die Unterstützung für die .NET-Runtime und -Tools ist weniger ausgereift. Beispielsweise gibt es Einschränkungen in [.NET Standard](../../standard/net-standard.md) Unterstützung und Debuggen.

Umgekehrt bietet das Blazor serverhostingmodell die folgenden Vorteile:

- Die Download Größe ist wesentlich kleiner als eine Client seitige APP, und die APP lädt viel schneller.
- Die App nutzt vollständige Vorteile der Serverfunktionen, einschließlich der Verwendung von .net Core-kompatiblen APIs.
- Da auf dem Server .NET Core zum Ausführen der App verwendet wird, funktionieren vorhandene .NET-Tools, wie das Debuggen, erwartungsgemäß.
- Thin Clients werden unterstützt. Serverseitige apps funktionieren z. b. mit Browsern, die WebAssembly und auf Geräten mit eingeschränkter Ressourcen nicht unterstützen.
- Die .NET-/C#-Codebasis der App, einschließlich des Komponentencodes, werden nicht für Clients bereitgestellt.

Folgende Nachteile gelten für das Blazor serverhostingmodell:

- Höhere UI-Latenz. Bei jeder Benutzerinteraktion fällt ein Netzwerkhop an.
- Es gibt keine Offlineunterstützung. Bei einer Unterbrechung der Clientverbindung funktioniert die App nicht mehr.
- Die Skalierbarkeit ist bei Apps mit vielen Benutzern schwierig. Der Server muss eine Vielzahl von Clientverbindungen verwalten und Clientzustände verarbeiten.
- Zum Bereitstellen der App ist ein ASP.NET Core-Server erforderlich. Server lose Bereitstellungs Szenarien sind nicht möglich. Beispielsweise können Sie die APP nicht über ein CDN bereitstellen.

Die vorherige Liste von vor-und Nachteile ist möglicherweise einschüchternd, aber Ihr Hostingmodell kann später geändert werden. Unabhängig vom Blazor ausgewählten Hostingmodell ist das Komponentenmodell *identisch*. Im Prinzip können dieselben Komponenten mit einem der beiden Hostingmodelle verwendet werden. Ihr app-Code ändert sich nicht. Es empfiehlt sich jedoch, Abstraktionen einzuführen, damit Ihre Komponentenmodell agnostisch bleiben. Die Abstraktionen ermöglichen es Ihrer APP, ein anderes Hostingmodell leichter zu übernehmen.

## <a name="deploy-your-app"></a>Bereitstellen Ihrer App

ASP.net Web Forms-apps werden in der Regel auf einem Windows Server-Computer oder-Cluster auf IIS gehostet. BlazorApps können auch folgende Aktionen ausführen:

- In IIS gehostet werden, entweder als statische Dateien oder als ASP.net Core-app.
- Nutzen Sie ASP.net Core Flexibilität, um auf verschiedenen Plattformen und Server Infrastrukturen gehostet zu werden. Beispielsweise können Sie eine- Blazor App mit [nginx](/aspnet/core/host-and-deploy/linux-nginx) oder [Apache](/aspnet/core/host-and-deploy/linux-apache) unter Linux hosten. Weitere Informationen zum Veröffentlichen und Bereitstellen von Blazor apps finden Sie in der Blazor Dokumentation zu [Hosting und Bereitstellung](/aspnet/core/host-and-deploy/blazor/) .

Im nächsten Abschnitt sehen wir uns an, wie die Projekte für Blazor WebAssembly und Blazor Server-Apps eingerichtet werden.

>[!div class="step-by-step"]
>[Zurück](architecture-comparison.md)
>[Weiter](project-structure.md)
