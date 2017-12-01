---
title: "Entscheidungstabelle. .NET Framework-Versionen für Docker verwenden"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entscheidungstabelle, die .NET Framework-Versionen für Docker verwenden"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Entscheidungstabelle: .NET Framework-Versionen für Docker verwenden

Im folgenden zusammengefasst, ob .NET Framework oder .NET Core und Windows oder Linux-Container verwendet. Denken Sie daran, dass es für Linux-Containern benötigen Sie die Linux-basierte Docker-Hosts (virtuelle Computer oder Server), die für Windows-Container Windows Server werden benötigen Docker-Hosts (virtuelle Computer oder Server basierte).

Es gibt verschiedene Funktionen der Anwendung, die Ihre Entscheidung auswirken. Wägen Sie die Bedeutung dieser Funktionen bei Ihrer Entscheidung.

> [!IMPORTANT]
> Ihre Entwicklungscomputern werden ein Docker-Host, Linux- oder Windows ausgeführt werden. Verwandte Microservices, die Sie ausführen möchten und Testen zusammen in einer Lösung müssen alle auf den gleichen Container-Plattform ausgeführt werden.

* Die Wahl der Anwendung-Architektur ist **Microservices für Container**.
    - Gewählter Implementierung .NET muss *.NET Core*.
    - Ihre Wahl der Container-Plattform kann es sich um *Linux-Containern* oder *Windows-Containern*.
* Die Wahl der Anwendung-Architektur ist eine **monolithischen Anwendung**.
    - Gewählter Implementierung .NET kann es sich um *.NET Core* oder *.NET Framework*.
    - Wenn Sie ausgewählt haben *.NET Core*, Ihre Wahl der Container-Plattform kann es sich um *Linux-Containern* oder *Windows-Containern*.
    - Wenn Sie ausgewählt haben *.NET Framework*, Ihre Wahl der Container-Plattform muss *Windows-Containern*.
* Die Anwendung ist ein **Container basierende Neuentwicklungen ("Grün-Field")**.
    - Gewählter Implementierung .NET muss *.NET Core*.
    - Ihre Wahl der Container-Plattform kann es sich um *Linux-Containern* oder *Windows-Containern*.
* Die Anwendung ist eine **legacy-app ("Brown-Field") Windows Server-Migration zu Containern**
    - Die Wahl des .NET Implementierung ist *.NET Framework* basierend auf der frameworkabhängigkeit.
    - Ihre Wahl der Container-Plattform muss *Windows-Containern* aufgrund der Abhängigkeit von .NET Framework.
* Ihre Anwendung Entwurfsziel ist die **in puncto Leistung und Skalierbarkeit**.
    - Gewählter Implementierung .NET muss *.NET Core*.
    - Ihre Wahl der Container-Plattform kann es sich um *Linux-Containern* oder *Windows-Containern*.
* Sie erstellt die Anwendung mit **ASP.NET Core**.
    - Gewählter Implementierung .NET muss *.NET Core*.
    - Sie können die *.NET Framework* haben andere Abhängigkeiten Framework-Implementierung.
    - Wenn Sie ausgewählt haben *.NET Core*, Ihre Wahl der Container-Plattform kann es sich um *Linux-Containern* oder *Windows-Containern*.
    - Wenn Sie ausgewählt haben *.NET Framework*, Ihre Wahl der Container-Plattform muss *Windows-Containern*.
* Sie erstellt die Anwendung mit **ASP.NET 4 (MVC 5, Web-API 2 und Web Forms)**.
    - Die Wahl des .NET Implementierung ist *.NET Framework* basierend auf der frameworkabhängigkeit.
    - Ihre Wahl der Container-Plattform muss *Windows-Containern* aufgrund der Abhängigkeit von .NET Framework.
* Ihre Anwendung verwendet **SignalR-Dienste**.
    - Gewählter Implementierung .NET möglich *.NET Framework*, oder *.NET Core 2.1 (wenn veröffentlicht) oder höher*.
    - Ihre Wahl der Container-Plattform muss *Windows-Containern* Wenn Sie die SignalR-Implementierung in .NET Framework ausgewählt haben.
    - Ihre Wahl der Container-Plattform kann Linux-Containern bzw. Windows-Containern werden, wenn Sie die SignalR-Implementierung in .NET Core 2.1 oder höher (wenn veröffentlicht) ausgewählt haben.  
    - Wenn **SignalR-Dienste** weiterlaufen *.NET Core*, können Sie *Linux Containern bzw. Windows-Containern*.
* Ihre Anwendung verwendet **WCF, WF und anderen älteren Frameworks**.
    - Die Wahl des .NET Implementierung ist *.NET Framework*, oder *.NET Core (in der Roadmap für eine künftige Version)*.
    - Ihre Wahl der Container-Plattform muss *Windows-Containern* aufgrund der Abhängigkeit von .NET Framework.
* Die Anwendung umfasst **Nutzung von Azure Services**.
    - Die Wahl des .NET Implementierung ist *.NET Framework*, oder *.NET Core (schließlich alle Azure Services gebe Client SDKs für .NET Core)*.
    - Ihre Wahl der Container-Plattform muss *Windows-Containern* bei Verwendung von .NET Framework-Client-APIs.
    - Bei Verwendung von Client-APIs zur *.NET Core*, Sie können außerdem auswählen, ob *Linux-Containern und Windows*.

>[!div class="step-by-step"]
[Vorherigen] (Net-Framework-Container-scenarios.md) [weiter] (Net-Container-os-targets.md)
