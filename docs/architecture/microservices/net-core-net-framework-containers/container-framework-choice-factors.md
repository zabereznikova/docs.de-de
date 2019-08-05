---
title: 'Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker'
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entscheidungstabelle, .NET Frameworks zur Verwendung für Docker
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675817"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker

In der folgenden Entscheidungstabelle wird zusammengefasst, ob .NET Framework oder .NET Core verwendet werden sollen. Beachten Sie, dass Sie für Linux-Container Linux-basierte Docker-Hosts (VMs oder Server) und für Windows-Container Windows Server-basierte Docker-Hosts (VMs oder Server) benötigen.

> [!IMPORTANT]
> Ihre Entwicklungscomputer führen einen Docker-Host aus: entweder Linux oder Windows. Verwandte Microservices, die Sie zusammen in einer Lösung ausführen und testen wollen, müssen alle auf der gleichen Containerplattform ausgeführt werden.

<table>
<thead>
<tr class="header">
<th><strong>Architektur/App-Typ</strong></th>
<th><strong>Linux-Container</strong></th>
<th><strong>Windows-Container</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microservices in Containern</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>Monolithische App</td>
<td>.NET Core</td>
<td><p>.NET Framework</p>
<p>.NET Core</p></td>
</tr>
<tr class="odd">
<td>Klassenbeste Leistung und Skalierbarkeit</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>Migration von Windows Server-Legacy-App („braunes Feld“) in Container</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="odd">
<td>Neue containerbasierte Entwicklung („grünes Feld“)</td>
<td>.NET Core</td>
<td>.NET Core</td>
</tr>
<tr class="even">
<td>ASP.NET Core</td>
<td>.NET Core</td>
<td><p>.NET Core (empfohlen)</p>
<p>.NET Framework</p></td>
</tr>
<tr class="odd">
<td>ASP.NET 4 (MVC 5, Web-API 2 und Web Forms)</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="even">
<td>SignalR-Dienste</td>
<td>.NET Core 2.1 oder eine höhere Version</td>
<td><p>.NET Framework</p>
<p>.NET Core 2.1 oder eine höhere Version</p></td>
</tr>
<tr class="odd">
<td>WCF, WF und andere Legacyframeworks</td>
<td>WCF in .NET Core (nur die WCF-Clientbibliothek)</td>
<td><p>.NET Framework</p>
<p>WCF in .NET Core (nur die WCF-Clientbibliothek)</p></td>
</tr>
<tr class="even">
<td>Nutzung von Azure-Diensten</td>
<td><p>.NET Core</p>
<p>(Auf lange Sicht werden alle Azure-Dienste Client-SDKs für .NET Core bereitstellen)</p></td>
<td><p>.NET Framework</p>
<p>.NET Core</p>
<p>(Auf lange Sicht werden alle Azure-Dienste Client-SDKs für .NET Core bereitstellen)</p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[Zurück](net-framework-container-scenarios.md)
>[Weiter](net-container-os-targets.md)
