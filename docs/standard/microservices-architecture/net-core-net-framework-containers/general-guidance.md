---
title: Allgemeine Richtlinien
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Allgemeine Richtlinien"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a>Allgemeine Richtlinien

Dieser Abschnitt enthält eine Zusammenfassung der wann .NET Core oder .NET Framework auswählen. Wir bieten ausführliche Informationen zu diesen Optionen in den folgenden Abschnitten.

Verwenden Sie .NET Core, Linux- oder Windows-Container für die Datenvolumes Docker-Server-Anwendung beim:

-   Es bestehen plattformübergreifende Anforderungen. Sie möchten z. B. Linux und Windows-Container verwenden.

-   Ihre Anwendungsarchitektur basiert auf Microservices.

-   Sie müssen Containern schnell starten und einen geringen Ressourcenbedarf pro höhere Dichte zu erreichen oder die weitere Container pro Einheit Hardware anstreben, um die Kosten zu senken.

Kurz gesagt, sollten Sie bei der Erstellung neuer .NET Sammelartikeleinheit .NET Core als Standardwahl berücksichtigen. Er weist viele Vorteile und mit dem Container Philosophie und den Stil der Arbeit am besten entspricht.

Ein weiterer Vorteil der Verwendung von .NET Core ist, dass Sie nebeneinander .NET Versionen für Anwendungen, in dem gleichen Computer ausführen können. Dieser Vorteil ist wichtiger für Server oder virtuelle Computer, die nicht-Container verwenden, da der Container die Versionen von .NET isolieren, die die app benötigt. (Solange sie mit dem zugrunde liegenden Betriebssystem kompatibel sind.)

Sollten Sie .NET Framework, mit Windows-Container verwenden, für die Datenvolumes Docker-Server-Anwendung beim:

-   Die Anwendung derzeit verwendet .NET Framework und weist starke Abhängigkeiten von Windows.

-   Sie müssen Windows-APIs verwenden, die von .NET Core nicht unterstützt werden.

-   Sie müssen .NET Bibliotheken von Drittanbietern oder NuGet-Pakete, die nicht für die .NET Core verfügbar sind.

Mithilfe von .NET Framework auf Docker kann Ihre bereitstellungsumgebung verbessern, indem Sie Bereitstellungsprobleme minimieren. Dies [ *"lift- and -shift-Szenario* ](https://aka.ms/liftandshiftwithcontainersebook) ist wichtig für ältere Anwendungen, die ursprünglich mit herkömmlichen .NET Framework entwickelt wurden, wie ASP.NET Web Forms, MVC-apps oder WCF (web containerizing Windows Communication Foundation)-Dienste.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **e-Book: Aktualisieren von vorhandenen .NET Framework-Anwendungen mit Azure und Windows-Containern**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **Beispiel-apps: Modernisierung legacy ASP.NET Web-Apps mithilfe von Windows-Containern**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Net-Core-Container-scenarios.md)
