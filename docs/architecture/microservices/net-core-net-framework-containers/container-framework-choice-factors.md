---
title: 'Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker'
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entscheidungstabelle, .NET Frameworks zur Verwendung für Docker
ms.date: 09/11/2018
ms.openlocfilehash: 8ffe2b7bc0bee976d3a63b274994dbcc8aef0c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628318"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker

In der folgenden Entscheidungstabelle wird zusammengefasst, ob .NET Framework oder .NET Core verwendet werden sollen. Beachten Sie, dass Sie für Linux-Container Linux-basierte Docker-Hosts (VMs oder Server) und für Windows-Container Windows Server-basierte Docker-Hosts (VMs oder Server) benötigen.

> [!IMPORTANT]
> Ihre Entwicklungscomputer führen einen Docker-Host aus: entweder Linux oder Windows. Verwandte Microservices, die Sie zusammen in einer Lösung ausführen und testen wollen, müssen alle auf der gleichen Containerplattform ausgeführt werden.

| Architektur/App-Typ | Linux-Container | Windows-Container |
|-------------------------|------------------|--------------------|
| Microservices in Containern | .NET Core | .NET Core |
| Monolithische App | .NET Core | .NET Framework <br/> .NET Core |
| Klassenbeste Leistung und Skalierbarkeit | .NET Core | .NET Core |
| Migration von Windows Server-Legacy-App („braunes Feld“) in Container | -- | .NET Framework |
| Neue containerbasierte Entwicklung („grünes Feld“) | .NET Core | .NET Core |
| ASP.NET Core | .NET Core | .NET Core (empfohlen) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, Web-API 2 und Web Forms) | -- | .NET Framework |
| SignalR-Dienste | .NET Core 2.1 oder eine höhere Version | .NET Framework <br/> .NET Core 2.1 oder eine höhere Version |
| WCF, WF und andere Legacyframeworks | WCF in .NET Core (nur Clientbibliothek) | .NET Framework <br/> WCF in .NET Core (nur Clientbibliothek) |
| Nutzung von Azure-Diensten | .NET Core <br/> (Auf lange Sicht werden die meisten Azure-Dienste Client-SDKs für .NET Core bereitstellen) | .NET Framework <br/> .NET Core <br/> (Auf lange Sicht werden die meisten Azure-Dienste Client-SDKs für .NET Core bereitstellen) |

>[!div class="step-by-step"]
>[Zurück](net-framework-container-scenarios.md)
>[Weiter](net-container-os-targets.md)
