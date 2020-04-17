---
title: Blazor App Hosting-Modelle
description: Erfahren Sie mehr über die verschiedenen Möglichkeiten zum Hosten einer Blazor-App, z. B. im Browser auf WebAssembly oder auf dem Server.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 77a022b01efba01038790c9601ea03f315a28fdf
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607931"
---
# <a name="blazor-app-hosting-models"></a>Blazor App Hosting-Modelle

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor-Apps können in IIS wie ASP.NET Web Forms-Apps gehostet werden. Blazor-Apps können auch auf eine der folgenden Arten gehostet werden:

- Client-Seite im Browser in WebAssembly.
- Serverseitig in einer ASP.NET Core-App.

## <a name="blazor-webassembly-apps"></a>Blazor WebAssembly-Apps

Blazor WebAssembly-Apps werden direkt im Browser auf einer WebAssembly-basierten .NET-Laufzeit ausgeführt. Blazor WebAssembly-Apps funktionieren ähnlich wie Front-End-JavaScript-Frameworks wie Angular oder React. Anstatt jedoch JavaScript zu schreiben, schreiben Sie C. Die .NET-Laufzeit wird zusammen mit der App-Assembly und allen erforderlichen Abhängigkeiten zusammen mit der App heruntergeladen. Es sind keine Browser-Plugins oder Erweiterungen erforderlich.

Die heruntergeladenen Assemblys sind normale .NET-Assemblys, wie Sie es in jeder anderen .NET-App verwenden würden. Da die Laufzeit .NET Standard unterstützt, können Sie vorhandene .NET Standard-Bibliotheken mit Ihrer Blazor WebAssembly-App verwenden. Diese Assemblys werden jedoch weiterhin in der Sicherheitssandbox des Browsers ausgeführt. Einige Funktionen können <xref:System.PlatformNotSupportedException>eine auslösen, z. B. den Versuch, auf das Dateisystem zuzugreifen oder beliebige Netzwerkverbindungen zu öffnen.

Wenn die App geladen wird, wird die .NET-Laufzeit gestartet und auf die App-Assembly gerichtet. Die App-Startlogik wird ausgeführt, und die Stammkomponenten werden gerendert. Blazor berechnet die UI-Aktualisierungen basierend auf der gerenderten Ausgabe der Komponenten. Die DOM-Aktualisierungen werden dann angewendet.

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazor WebAssembly-Apps laufen rein clientseitig. Solche Apps können auf statischen Websitehosting-Lösungen wie GitHub Pages oder Azure Static Website Hosting bereitgestellt werden. .NET ist auf dem Server überhaupt nicht erforderlich. Eine tiefe Verknüpfung mit Teilen der App erfordert in der Regel eine Routinglösung auf dem Server. Die Routinglösung leitet Anforderungen an den Stamm der App um. Diese Umleitung kann z. B. mithilfe von URL-Umschreibungsregeln in IIS behandelt werden.

Um alle Vorteile von Blazor und Full-Stack .NET Web-Entwicklung zu erhalten, hosten Sie Ihre Blazor WebAssembly App mit ASP.NET Core. Durch die Verwendung von .NET auf client und auf dem Server können Sie Code einfach freigeben und Ihre App mithilfe einer konsistenten Reihe von Sprachen, Frameworks und Tools erstellen. Blazor bietet praktische Vorlagen zum Einrichten einer Lösung, die sowohl eine Blazor WebAssembly-App als auch ein ASP.NET Core-Hostprojekt enthält. Wenn die Lösung erstellt wird, werden die erstellten statischen Dateien aus der Blazor-App von der ASP.NET Core-App gehostet, wobei das Fallback-Routing bereits eingerichtet ist.

## <a name="blazor-server-apps"></a>Blazor Server-Apps

Erinnern Sie sich an die [Blazor-Architekturdiskussion,](architecture-comparison.md#blazor) dass Blazor-Komponenten ihre Ausgabe zu einer Zwischenabstraktion namens " `RenderTree`rendern. Das Blazor-Framework vergleicht dann das Gerendertwerden mit dem, was zuvor gerendert wurde. Die Unterschiede werden auf das DOM angewendet. Blazor-Komponenten sind von der Anwendung der gerenderten Ausgabe entkoppelt. Folglich müssen die Komponenten selbst nicht im gleichen Prozess wie der Prozess zur Aktualisierung der Benutzeroberfläche ausgeführt werden. Tatsächlich müssen sie nicht einmal auf demselben Computer laufen.

In Blazor Server-Apps werden die Komponenten auf dem Server statt auf der Clientseite im Browser ausgeführt. UI-Ereignisse, die im Browser auftreten, werden über eine Echtzeitverbindung an den Server gesendet. Die Ereignisse werden an die richtigen Komponenteninstanzen gesendet. Die Komponenten werden gerendert, und der berechnete UI-Diff wird serialisiert und an den Browser gesendet, in dem er auf das DOM angewendet wird.

![Blazor Server](media/hosting-models/blazor-server.png)

Das Blazor Server-Hostingmodell klingt möglicherweise vertraut, wenn <xref:System.Web.UI.UpdatePanel> Sie ASP.NET AJAX und das Steuerelement verwendet haben. Das `UpdatePanel` Steuerelement behandelt das Anwenden partieller Seitenaktualisierungen als Reaktion auf Triggerereignisse auf der Seite. Wenn diese `UpdatePanel` Option ausgelöst wird, fordert die eine teilweise Aktualisierung an und wendet sie dann an, ohne die Seite aktualisieren zu müssen. Der Status der Benutzeroberfläche `ViewState`wird mithilfe von verwaltet. Blazor Server-Apps unterscheiden sich dadurch, dass die App eine aktive Verbindung mit dem Client erfordert. Darüber hinaus wird der gesamte UI-Status auf dem Server beibehalten. Abgesehen von diesen Unterschieden sind sich die beiden Modelle konzeptionell ähnlich.

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>Wie wählt man das richtige Blazor-Hosting-Modell

Wie in den [Blazor Hosting-Modell-Dokumenten](/aspnet/core/blazor/hosting-models)beschrieben, haben die verschiedenen Blazor-Hosting-Modelle unterschiedliche Kompromisse.

Das Blazor WebAssembly-Hostingmodell hat die folgenden Vorteile:

- Es gibt keine .NET serverseitige Abhängigkeit. Die App funktioniert voll funktionsfähig, nachdem sie auf den Client heruntergeladen wurde.
- Clientressourcen und -funktionen werden vollständig genutzt.
- Die Arbeit wird vom Server auf den Client ausgelagert.
- Ein ASP.NET Core-Webserver ist zum Hosten der App nicht erforderlich. Serverlose Bereitstellungsszenarien sind möglich (z. B. die Bereitstellung der App über ein CDN).

Die Nachteile des Blazor WebAssembly-Hostingmodells sind:

- Browserfunktionen schränken die App ein.
- Leistungsfähige Clienthardware und -software (z. B. WebAssembly-Unterstützung) ist erforderlich.
- Die Downloadgröße ist größer, und das Laden von Apps dauert länger.
- .NET Laufzeit- und Tooling-Unterstützung ist weniger ausgereift. Beispielsweise gibt es Einschränkungen in [der .NET Standard-Unterstützung](../../standard/net-standard.md) und beim Debuggen.

Umgekehrt bietet das Blazor Server-Hostingmodell die folgenden Vorteile:

- Die Downloadgröße ist viel kleiner als eine clientseitige App, und die App wird viel schneller geladen.
- Die App nutzt die Serverfunktionen voll aus, einschließlich der Verwendung aller .NET Core-kompatiblen APIs.
- .NET Core auf dem Server wird zum Ausführen der App verwendet, sodass vorhandene .NET-Tools, z. B. Debuggen, wie erwartet funktionieren.
- Thin Clients werden unterstützt. Beispielsweise funktionieren serverseitige Apps mit Browsern, die WebAssembly nicht unterstützen, und auf geräten mit eingeschränkten Ressourcen.
- Die .NET/C-Codebasis der App, einschließlich des Komponentencodes der App, wird nicht für Clients bereitgestellt.

Die Nachteile des Blazor Server-Hostingmodells sind:

- Höhere UI-Latenz. Jede Benutzerinteraktion beinhaltet einen Netzwerk-Hop.
- Es gibt keine Offline-Unterstützung. Wenn die Clientverbindung fehlschlägt, funktioniert die App nicht mehr.
- Skalierbarkeit ist eine Herausforderung für Apps mit vielen Benutzern. Der Server muss mehrere Clientverbindungen verwalten und den Clientstatus verarbeiten.
- Für die App ist ein ASP.NET Core-Server erforderlich. Serverlose Bereitstellungsszenarien sind nicht möglich. Sie können die App z. B. nicht über ein CDN bedienen.

Die vorangehende Liste der Kompromisse kann einschüchternd sein, aber Ihr Hosting-Modell kann später geändert werden. Unabhängig vom ausgewählten Blazor-Hostingmodell ist das Komponentenmodell *identisch.* Grundsätzlich können dieselben Komponenten mit beiden Hosting-Modell verwendet werden. Ihr App-Code ändert sich nicht. Es ist jedoch eine gute Praxis, Abstraktionen einzuführen, damit Ihre Komponenten modellunabhängig bleiben. Die Abstraktionen ermöglichen es Ihrer App, ein anderes Hostingmodell einfacher zu übernehmen.

## <a name="deploy-your-app"></a>Bereitstellen Ihrer App

ASP.NET Web Forms-Apps werden in der Regel auf IIS auf einem Windows Server-Computer oder -Cluster gehostet. Blazor-Apps können auch:

- Werden Sie auf IIS gehostet, entweder als statische Dateien oder als ASP.NET Core-App.
- Nutzen Sie ASP.NET Die Flexibilität von Core, auf verschiedenen Plattformen und Serverinfrastrukturen gehostet zu werden. Sie können beispielsweise eine Blazor App mit [Nginx](/aspnet/core/host-and-deploy/linux-nginx) oder [Apache](/aspnet/core/host-and-deploy/linux-apache) unter Linux hosten. Weitere Informationen zum Veröffentlichen und Bereitstellen von Blazor-Apps finden Sie in der Dokumentation zum [Blazor-Hosting und zur Bereitstellung.](/aspnet/core/host-and-deploy/blazor/)

Im nächsten Abschnitt sehen wir uns die Einrichtung der Projekte für Blazor WebAssembly- und Blazor Server-Apps an.

>[!div class="step-by-step"]
>[Zurück](architecture-comparison.md)
>[Weiter](project-structure.md)
