---
title: Blazor-App-Hostingmodelle
description: Erfahren Sie mehr über die verschiedenen Möglichkeiten zum Hosten einer blazor-APP, einschließlich des Browsers in Webassembly oder auf dem Server.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 5bf55fa686691acc25508d3d9a6dfaf8aca321ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841948"
---
# <a name="blazor-app-hosting-models"></a>Blazor-App-Hostingmodelle

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor-Apps können genauso wie ASP.net Web Forms-apps in IIS gehostet werden. Blazor-Apps können auch auf eine der folgenden Arten gehostet werden:

- Client seitig im Browser in Webassembly.
- Server seitig in einer ASP.net Core-app.

## <a name="blazor-webassembly-apps"></a>Blazor Webassembly-apps

Blazor Webassembly-apps werden direkt im Browser auf einer webassemblybasierten .NET-Laufzeit ausgeführt. Blazor-webassemblyanwendungen funktionieren auf ähnliche Weise wie Front-End-JavaScript-Frameworks wie Angular oder reagieren. Anstatt jedoch JavaScript zu schreiben, schreiben C#Sie. Die .NET-Laufzeit wird zusammen mit der APP-Assembly und allen erforderlichen Abhängigkeiten mit der App heruntergeladen. Es sind keine Browser-Plug-ins oder Erweiterungen erforderlich.

Die heruntergeladenen Assemblys sind normale .NET-Assemblys, wie Sie in jeder anderen .net-App verwenden würden. Da die Common Language Runtime .NET Standard unterstützt, können Sie vorhandene .NET Standard Bibliotheken mit ihrer blazor Webassembly-App verwenden. Diese Assemblys werden jedoch weiterhin im Browser-Sicherheits Sandbox ausgeführt. Einige Funktionen lösen möglicherweise eine <xref:System.PlatformNotSupportedException>aus, z. b. den Zugriff auf das Dateisystem oder das Öffnen beliebiger Netzwerkverbindungen.

Wenn die App geladen wird, wird die .NET-Laufzeit gestartet, und es wird auf die APP-Assembly verwiesen. Die APP-Start Logik wird ausgeführt, und die Stamm Komponenten werden gerendert. Blazor berechnet die Aktualisierungen der Benutzeroberfläche basierend auf der gerenderten Ausgabe der Komponenten. Anschließend werden die DOM-Updates angewendet.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazor Webassembly-apps werden nur auf Clientseite ausgeführt. Solche Apps können für statische Site Hosting-Lösungen wie GitHub-Seiten oder das Hosting von Azure Static-Websites bereitgestellt werden. .Net ist auf dem Server nicht erforderlich. Die Tiefe Verknüpfung mit den Teilen der APP erfordert in der Regel eine Routing Lösung auf dem Server. Die Routing Lösung leitet Anforderungen an den Stamm der App um. Diese Umleitung kann beispielsweise mithilfe von URL-Rewrite-Regeln in IIS verarbeitet werden.

Um alle Vorteile von blazor und der vollständigen .net-Webentwicklung zu erhalten, hosten Sie Ihre blazor Webassembly-App mit ASP.net Core. Wenn Sie .net sowohl auf dem Client als auch auf dem Server verwenden, können Sie Code problemlos freigeben und die App mithilfe eines konsistenten Satzes von Sprachen, Frameworks und Tools erstellen. Blazor bietet praktische Vorlagen zum Einrichten einer Projekt Mappe, die sowohl eine blazor Webassembly-App als auch ein ASP.net Core Host Projekt enthält. Wenn die Lösung erstellt wird, werden die erstellten statischen Dateien aus der blazor-APP von der ASP.net Core-App gehostet, wobei das Fall Back Routing bereits eingerichtet ist.

## <a name="blazor-server-apps"></a>Blazor-Server-apps

Erinnern Sie sich aus der Beschreibung der [blazor-Architektur](architecture-comparison.md#blazor) , dass blazor-Komponenten Ihre Ausgabe in eine zwischen Abstraktion Rendering`RenderTree`Rendering Das blazor-Framework vergleicht dann, was gerendert wurde, was zuvor gerendert wurde. Die Unterschiede werden auf das DOM angewendet. Blazor-Komponenten sind von der Anwendung ihrer gerenderten Ausgabe entkoppelt. Folglich müssen die Komponenten selbst nicht in demselben Prozess ausgeführt werden wie der Prozess, der die Benutzeroberfläche aktualisiert. Tatsächlich müssen Sie nicht einmal auf dem gleichen Computer ausgeführt werden.

In blazor-Server-apps werden die Komponenten auf dem Server und nicht auf der Clientseite im Browser ausgeführt. Benutzeroberflächen Ereignisse, die im Browser auftreten, werden über eine Echtzeitverbindung an den Server gesendet. Die Ereignisse werden an die richtigen Komponenten Instanzen weitergeleitet. Die Komponenten werden gerbt, und der berechnete UI-diff wird serialisiert und an den Browser gesendet, in dem Sie auf das DOM angewendet wird.

![Blazor Server](media/hosting-models/blazor-server.png)

Das blazor-Server Hostingmodell ist möglicherweise vertraut, wenn Sie ASP.NET AJAX und das <xref:System.Web.UI.UpdatePanel>-Steuerelement verwendet haben. Das `UpdatePanel` Steuerelement übernimmt das Anwenden partieller Seiten Aktualisierungen als Reaktion auf Triggerereignisse auf der Seite. Wenn Sie ausgelöst wird, fordert die `UpdatePanel` eine partielle Aktualisierung an und wendet Sie dann an, ohne die Seite aktualisieren zu müssen. Der Status der Benutzeroberfläche wird mit `ViewState`verwaltet. Blazor-Server-apps unterscheiden sich geringfügig insofern, als die APP eine aktive Verbindung mit dem Client erfordert. Außerdem wird der gesamte Status der Benutzeroberfläche auf dem Server beibehalten. Abgesehen von diesen Unterschieden sind die beiden Modelle konzeptionell ähnlich.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Auswählen des richtigen blazor-Hostingmodells

Wie in der Dokumentation des [blazor-Hostingmodells](https://docs.microsoft.com/aspnet/core/blazor/hosting-models#server-side)beschrieben, haben die verschiedenen blazor-Hostingmodelle unterschiedliche Kompromisse.

Das Webassembly-Hostingmodell von blazor bietet die folgenden Vorteile:

- Es gibt keine serverseitige .net-Abhängigkeit. Die APP funktioniert nach dem Herunterladen auf den Client vollständig.
- Client Ressourcen und-Funktionen sind vollständig ausgelastet.
- Die Arbeit wird vom Server an den Client verlagert.
- Ein ASP.net Core Webserver ist nicht erforderlich, um die APP zu hosten. Server lose Bereitstellungs Szenarien sind möglich (z. b. das Bereitstellen der APP aus einem CDN).

Die folgenden Nachteile des blazor-webassemblyhostingmodells lauten:

- Browser Funktionen schränken die APP ein.
- Kompatible Client Hardware und Software (z. b. webassemblyunterstützung) ist erforderlich.
- Die Download Größe ist größer, und die Auslastung von apps dauert länger.
- Die Unterstützung von .NET-Laufzeit und-Tools ist weniger ausgereift. Beispielsweise gibt es Einschränkungen in [.NET Standard](../../standard/net-standard.md) Unterstützung und Debuggen.

Umgekehrt bietet das Hostinganbieter des blazor-Servers die folgenden Vorteile:

- Die Download Größe ist wesentlich kleiner als eine Client seitige APP, und die APP lädt viel schneller.
- Die App nutzt vollständige Vorteile der Serverfunktionen, einschließlich der Verwendung von .net Core-kompatiblen APIs.
- .Net Core auf dem Server wird verwendet, um die APP auszuführen, sodass vorhandene .NET-Tools, wie z. b. das Debuggen, erwartungsgemäß funktionieren.
- Thin Clients werden unterstützt. Serverseitige apps arbeiten z. b. mit Browsern, die Webassembly nicht unterstützen, und auf Geräten mit Ressourcen Beschränkung.
- Die .net-C# /Codebasis der APP, einschließlich des Komponenten Codes der APP, wird nicht für Clients bereitgestellt.

Folgende Nachteile gelten für das serverhostingmodell des blazor-Servers:

- Höhere UI-Latenz. Jede Benutzerinteraktion umfasst einen Netzwerkhop.
- Es gibt keine Offline Unterstützung. Wenn die Client Verbindung fehlschlägt, funktioniert die APP nicht mehr.
- Skalierbarkeit ist eine Herausforderung für apps mit vielen Benutzern. Der Server muss mehrere Clientverbindungen verwalten und den Client Status verarbeiten.
- Ein ASP.net Core Server ist erforderlich, um der APP zu dienen. Server lose Bereitstellungs Szenarien sind nicht möglich. Beispielsweise können Sie die APP nicht über ein CDN bereitstellen.

Die vorherige Liste von vor-und Nachteile ist möglicherweise einschüchternd, aber Ihr Hostingmodell kann später geändert werden. Unabhängig vom ausgewählten blazor-Hostingmodell ist das Komponentenmodell *identisch*. Im Prinzip können dieselben Komponenten mit einem der beiden Hostingmodelle verwendet werden. Ihr app-Code ändert sich nicht. Es empfiehlt sich jedoch, Abstraktionen einzuführen, damit Ihre Komponentenmodell agnostisch bleiben. Die Abstraktionen ermöglichen es Ihrer APP, ein anderes Hostingmodell leichter zu übernehmen.

## <a name="deploy-your-app"></a>Bereitstellen der App

ASP.net Web Forms-apps werden in der Regel auf einem Windows Server-Computer oder-Cluster auf IIS gehostet. Blazor-Apps können auch folgende Aktionen ausführen:

- In IIS gehostet werden, entweder als statische Dateien oder als ASP.net Core-app.
- Nutzen Sie ASP.net Core Flexibilität, um auf verschiedenen Plattformen und Server Infrastrukturen gehostet zu werden. Beispielsweise können Sie eine blazor-App mit [nginx](/aspnet/core/host-and-deploy/linux-nginx) oder [Apache](/aspnet/core/host-and-deploy/linux-apache) unter Linux hosten. Weitere Informationen zum Veröffentlichen und Bereitstellen von blazor-apps finden Sie in der Dokumentation zur blazor [-Hosting-und-Bereitstellung](/aspnet/core/host-and-deploy/blazor/) .

Im nächsten Abschnitt sehen wir uns an, wie die Projekte für blazor Webassembly-und blazor-Server-Apps eingerichtet werden.

>[!div class="step-by-step"]
>[Zurück](architecture-comparison.md)
>[Weiter](project-structure.md)
