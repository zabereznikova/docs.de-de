---
title: 'Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker'
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entscheidungstabelle, .NET Frameworks zur Verwendung für Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0e384fabca88d8ad6f93ae626140fb3d5dcaf971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker

Im Folgenden wird zusammengefasst, ob .NET Framework oder .NET Core und Windows- oder Linux-Container verwendet werden sollen. Beachten Sie, dass Sie für Linux-Container Linux-basierte Docker-Hosts (VMs oder Server) und für Windows-Container Windows Server-basierte Docker-Hosts (VMs oder Server) benötigen.

Es gibt verschiedene Features Ihrer Anwendung, die diese Entscheidung beeinflussen. Sie sollten die Wichtigkeit dieser Features abwägen, bevor Sie Ihre Entscheidung treffen.

> [!IMPORTANT]
> Ihre Entwicklungscomputer führen einen Docker-Host aus: entweder Linux oder Windows. Verwandte Microservices, die Sie zusammen in einer Lösung ausführen und testen wollen, müssen alle auf der gleichen Containerplattform ausgeführt werden.

* Sie entscheiden sich für **Microservices auf Containern**:
    - Sie sollten *.NET Core* für die .NET-Implementierung auswählen.
    - Sie können entweder *Linux-Container* oder *Windows-Container* als Containerplattform verwenden.
* Sie entscheiden sich für eine **monolithische Anwendung**:
    - Sie können entweder *.NET Core* oder *.NET Framework* zur Implementierung verwenden.
    - Wenn Sie sich für *.NET Core* entschieden haben, können Sie als Containerplattform entweder *Linux-Container* oder *Windows-Container* auswählen.
    - Wenn Sie sich für *.NET Framework* entschieden haben, müssen Sie als Containerplattform *Windows-Container* auswählen.
* Bei Ihrer Anwendung handelt es sich um eine **neue containerbasierte Entwicklung („Green-field“)**.
    - Sie sollten *.NET Core* für die .NET-Implementierung auswählen.
    - Sie können als Containerplattform entweder *Linux-Container* oder *Windows-Container* verwenden.
* Es handelt sich bei Ihrer Anwendung um eine **Legacy-App („brown-field“) für die Migration von Windows Server zu Containern**.
    - Sie entscheiden sich aufgrund der Frameworkabhängigkeiten für *.NET Framework* als .NET-Implementierung:
    - Sie müssen aufgrund der Abhängigkeit von .NET Framework *Windows-Container* als Containerplattform auswählen.
* Sie streben **Leistung und Skalierbarkeit der Spitzenklasse** als Entwurfsziel für Ihre Anwendung an.
    - Sie sollten *.NET Core* für die .NET-Implementierung auswählen.
    - Sie können als Containerplattform entweder *Linux-Container* oder *Windows-Container* verwenden.
* Sie haben Ihre Anwendung mit **ASP.NET Core** erstellt.
    - Sie sollten *.NET Core* für die .NET-Implementierung auswählen.
    - Sie können die Implementierung von *.NET Framework* verwenden, wenn Sie über andere Frameworkabhängigkeiten verfügen.
    - Wenn Sie sich für *.NET Core* entschieden haben, können Sie als Containerplattform entweder *Linux-Container* oder *Windows-Container* auswählen.
    - Wenn Sie sich für *.NET Framework* entschieden haben, müssen Sie *Windows-Container* als Containerplattform auswählen.
* Sie haben Ihre Anwendung mit **ASP.NET 4 (MVC 5, Web API 2 und Web Forms)** erstellt.
    - Sie entscheiden sich aufgrund der Frameworkabhängigkeiten für *.NET Framework* als .NET-Implementierung:
    - Sie müssen aufgrund der Abhängigkeit von .NET Framework *Windows-Container* als Containerplattform auswählen.
* Ihre Anwendung verwendet **SignalR-Dienste**.
    - Sie können entweder *.NET Framework* oder *.NET Core 2.1 (wenn veröffentlicht) oder höher* für die .NET-Implementierung auswählen.
    - Sie müssen *Windows-Container* als Containerplattform auswählen, wenn Sie sich für die SignalR-Implementierung in .NET Framework entschieden haben.
    - Sie können als Containerplattform entweder Linux-Container oder Windows-Container auswählen, wenn Sie die SignalR-Implementierung in .NET Core 2.1 oder höher (wenn veröffentlicht) ausgewählt haben.  
    - Wenn **SignalR-Dienste** auf *.NET Core* ausgeführt werden, können Sie *Linux-Container oder Windows-Container* verwenden.
* Ihre Anwendung verwendet **WCF, WF und andere Legacyframeworks**.
    - Sie haben sich für *.NET Framework* oder *.NET Core (in der Übersicht zu einem zukünftigen Release)* entschieden.
    - Sie müssen aufgrund der Abhängigkeit von .NET Framework *Windows-Container* als Containerplattform auswählen.
* Ihre Anwendung umfasst die **Nutzung von Azure-Diensten**.
    - Sie haben *.NET Framework* oder *.NET Core (irgendwann sollen alle Azure-Dienste Client SDKs für .NET Core bereitstellen)* für die .NET-Implementierung ausgewählt.
    - Sie müssen *Windows-Container* als Containerplattform auswählen, wenn Sie .NET Framework-Client-APIs verwenden.
    - Wenn Sie die für *.NET Core* verfügbaren Client-APIs verwenden, können Sie zwischen *Linux-Containern und Windows-Containern* entscheiden.

>[!div class="step-by-step"]
[Zurück] (net-framework-container-scenarios.md) [Weiter] (net-container-os-targets.md)
