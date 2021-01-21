---
title: 'Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker'
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entscheidungstabelle, .NET Frameworks zur Verwendung für Docker
ms.date: 01/13/2021
ms.openlocfilehash: 35f101b3f4030e081068677b3754363bf6cd8210
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188659"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker

In der folgenden Entscheidungstabelle wird zusammengefasst, ob .NET Framework oder .NET 5 verwendet werden soll. Beachten Sie, dass Sie für Linux-Container Linux-basierte Docker-Hosts (VMs oder Server) und für Windows-Container Windows Server-basierte Docker-Hosts (VMs oder Server) benötigen.

> [!IMPORTANT]
> Ihre Entwicklungscomputer führen einen Docker-Host aus: entweder Linux oder Windows. Verwandte Microservices, die Sie zusammen in einer Lösung ausführen und testen wollen, müssen alle auf der gleichen Containerplattform ausgeführt werden.

| Architektur/App-Typ | Linux-Container | Windows-Container |
|-------------------------|------------------|--------------------|
| Microservices in Containern | .NET 5 | .NET 5 |
| Monolithische App | .NET 5 | .NET Framework <br/> .NET 5 |
| Klassenbeste Leistung und Skalierbarkeit | .NET 5 | .NET 5 |
| Migration von Windows Server-Legacy-App („braunes Feld“) in Container | -- | .NET Framework |
| Neue containerbasierte Entwicklung („grünes Feld“) | .NET 5 | .NET 5 |
| ASP.NET Core | .NET 5 | .NET 5 (empfohlen) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, Web-API 2 und Web Forms) | -- | .NET Framework |
| SignalR-Dienste | .NET Core 2.1 oder eine höhere Version | .NET Framework <br/> .NET Core 2.1 oder eine höhere Version |
| WCF, WF und andere Legacyframeworks | WCF in .NET Core (nur Clientbibliothek) | .NET Framework <br/> WCF in .NET 5 (nur Clientbibliothek) |
| Nutzung von Azure-Diensten | .NET 5 <br/> (Auf lange Sicht stellen die meisten Azure-Dienste Client-SDKs für .NET 5 bereit.) | .NET Framework <br/> .NET 5 <br/> (Auf lange Sicht stellen die meisten Azure-Dienste Client-SDKs für .NET 5 bereit.) |

>[!div class="step-by-step"]
>[Zurück](net-framework-container-scenarios.md)
>[Weiter](net-container-os-targets.md)
