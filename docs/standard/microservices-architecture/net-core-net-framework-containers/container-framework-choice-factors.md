---
title: 'Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker'
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Entscheidungstabelle, .NET Frameworks zur Verwendung für Docker
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639180"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="0dcdc-104">Entscheidungstabelle: .NET Frameworks zur Verwendung für Docker</span><span class="sxs-lookup"><span data-stu-id="0dcdc-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="0dcdc-105">In der folgenden Entscheidungstabelle wird zusammengefasst, ob .NET Framework oder .NET Core verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0dcdc-105">The following decision table summarizes whether to use .NET Framework or .NET Core.</span></span> <span data-ttu-id="0dcdc-106">Beachten Sie, dass Sie für Linux-Container Linux-basierte Docker-Hosts (VMs oder Server) und für Windows-Container Windows Server-basierte Docker-Hosts (VMs oder Server) benötigen.</span><span class="sxs-lookup"><span data-stu-id="0dcdc-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dcdc-107">Ihre Entwicklungscomputer führen einen Docker-Host aus: entweder Linux oder Windows.</span><span class="sxs-lookup"><span data-stu-id="0dcdc-107">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="0dcdc-108">Verwandte Microservices, die Sie zusammen in einer Lösung ausführen und testen wollen, müssen alle auf der gleichen Containerplattform ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0dcdc-108">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="0dcdc-109"><strong>Architektur/App-Typ</strong></span><span class="sxs-lookup"><span data-stu-id="0dcdc-109"><strong>Architecture / App Type</strong></span></span></th>
<th><span data-ttu-id="0dcdc-110"><strong>Linux-Container</strong></span><span class="sxs-lookup"><span data-stu-id="0dcdc-110"><strong>Linux containers</strong></span></span></th>
<th><span data-ttu-id="0dcdc-111"><strong>Windows-Container</strong></span><span class="sxs-lookup"><span data-stu-id="0dcdc-111"><strong>Windows Containers</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0dcdc-112">Microservices in Containern</span><span class="sxs-lookup"><span data-stu-id="0dcdc-112">Microservices on containers</span></span></td>
<td><span data-ttu-id="0dcdc-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-113">.NET Core</span></span></td>
<td><span data-ttu-id="0dcdc-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-114">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0dcdc-115">Monolithische App</span><span class="sxs-lookup"><span data-stu-id="0dcdc-115">Monolithic app</span></span></td>
<td><span data-ttu-id="0dcdc-116">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-116">.NET Core</span></span></td>
<td><p><span data-ttu-id="0dcdc-117">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-117">.NET Framework</span></span></p>
<p><span data-ttu-id="0dcdc-118">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-118">.NET Core</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0dcdc-119">Klassenbeste Leistung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="0dcdc-119">Best-in-class performance and scalability</span></span></td>
<td><span data-ttu-id="0dcdc-120">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-120">.NET Core</span></span></td>
<td><span data-ttu-id="0dcdc-121">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-121">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0dcdc-122">Migration von Windows Server-Legacy-App („braunes Feld“) in Container</span><span class="sxs-lookup"><span data-stu-id="0dcdc-122">Windows Server legacy app ("brown-field") migration to containers</span></span></td>
<td>--</td>
<td><span data-ttu-id="0dcdc-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-123">.NET Framework</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0dcdc-124">Neue containerbasierte Entwicklung („grünes Feld“)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-124">New container-based development ("green-field")</span></span></td>
<td><span data-ttu-id="0dcdc-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-125">.NET Core</span></span></td>
<td><span data-ttu-id="0dcdc-126">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-126">.NET Core</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0dcdc-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-127">ASP.NET Core</span></span></td>
<td><span data-ttu-id="0dcdc-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-128">.NET Core</span></span></td>
<td><p><span data-ttu-id="0dcdc-129">.NET Core (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-129">.NET Core (recommended)</span></span></p>
<p><span data-ttu-id="0dcdc-130">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-130">.NET Framework</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0dcdc-131">ASP.NET 4 (MVC 5, Web-API 2 und Web Forms)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-131">ASP.NET 4 (MVC 5, Web API 2, and Web Forms)</span></span></td>
<td>--</td>
<td><span data-ttu-id="0dcdc-132">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-132">.NET Framework</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0dcdc-133">SignalR-Dienste</span><span class="sxs-lookup"><span data-stu-id="0dcdc-133">SignalR services</span></span></td>
<td><span data-ttu-id="0dcdc-134">.NET Core 2.1 oder eine höhere Version</span><span class="sxs-lookup"><span data-stu-id="0dcdc-134">.NET Core 2.1 or higher version</span></span></td>
<td><p><span data-ttu-id="0dcdc-135">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-135">.NET Framework</span></span></p>
<p><span data-ttu-id="0dcdc-136">.NET Core 2.1 oder eine höhere Version</span><span class="sxs-lookup"><span data-stu-id="0dcdc-136">.NET Core 2.1 or higher version</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0dcdc-137">WCF, WF und andere Legacyframeworks</span><span class="sxs-lookup"><span data-stu-id="0dcdc-137">WCF, WF, and other legacy frameworks</span></span></td>
<td><span data-ttu-id="0dcdc-138">WCF in .NET Core (nur die WCF-Clientbibliothek)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-138">WCF in .NET Core (only the WCF client library)</span></span></td>
<td><p><span data-ttu-id="0dcdc-139">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-139">.NET Framework</span></span></p>
<p><span data-ttu-id="0dcdc-140">WCF in .NET Core (nur die WCF-Clientbibliothek)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-140">WCF in .NET Core (only the WCF client library)</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0dcdc-141">Nutzung von Azure-Diensten</span><span class="sxs-lookup"><span data-stu-id="0dcdc-141">Consumption of Azure services</span></span></td>
<td><p><span data-ttu-id="0dcdc-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-142">.NET Core</span></span></p>
<p><span data-ttu-id="0dcdc-143">(Auf lange Sicht werden alle Azure-Dienste Client-SDKs für .NET Core bereitstellen)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-143">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
<td><p><span data-ttu-id="0dcdc-144">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0dcdc-144">.NET Framework</span></span></p>
<p><span data-ttu-id="0dcdc-145">.NET Core</span><span class="sxs-lookup"><span data-stu-id="0dcdc-145">.NET Core</span></span></p>
<p><span data-ttu-id="0dcdc-146">(Auf lange Sicht werden alle Azure-Dienste Client-SDKs für .NET Core bereitstellen)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-146">(eventually all Azure services will provide client SDKs for .NET Core)</span></span></p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
><span data-ttu-id="0dcdc-147">[Zurück](net-framework-container-scenarios.md)
>[Weiter](net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="0dcdc-147">[Previous](net-framework-container-scenarios.md)
[Next](net-container-os-targets.md)</span></span>
