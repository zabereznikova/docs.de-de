---
title: Allgemeine Anleitung
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Allgemeine Anleitung
ms.date: 09/11/2018
ms.openlocfilehash: 2fa66d7593b764a8df4d9acc20f93d3f8fb26174
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73089647"
---
# <a name="general-guidance"></a><span data-ttu-id="96b7f-103">Allgemeine Anleitung</span><span class="sxs-lookup"><span data-stu-id="96b7f-103">General guidance</span></span>

<span data-ttu-id="96b7f-104">Dieser Abschnitt enthält eine Zusammenfassung darüber, wann .NET Core bzw. .NET Framework verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="96b7f-104">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="96b7f-105">In den folgenden Abschnitten werden weitere Informationen dazu bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="96b7f-105">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="96b7f-106">Sie sollten .NET Core mit Linux- oder Windows-Containern für Ihre containerisierte Docker-Serveranwendung verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="96b7f-106">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

- <span data-ttu-id="96b7f-107">Es bestehen plattformübergreifende Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="96b7f-107">You have cross-platform needs.</span></span> <span data-ttu-id="96b7f-108">Sie beispielsweise Linux- und Windows-Container verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="96b7f-108">For example, you want to use both Linux and Windows Containers.</span></span>

- <span data-ttu-id="96b7f-109">Die Architektur Ihrer Anwendung auf Microservices basiert</span><span class="sxs-lookup"><span data-stu-id="96b7f-109">Your application architecture is based on microservices.</span></span>

- <span data-ttu-id="96b7f-110">Sie Container schnell starten müssen und den Ressourcenbedarf pro Container gering halten möchten, um eine höhere Dichte oder mehr Container pro Hardwareeinheit zu erreichen und Ihre Kosten zu senken</span><span class="sxs-lookup"><span data-stu-id="96b7f-110">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="96b7f-111">Kurz gesagt sollte Ihre Wahl standardmäßig auf .NET Core fallen, wenn Sie neue .NET-Containeranwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="96b7f-111">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="96b7f-112">.NET Core weist viele Vorteile auf und entspricht dem Konzept und der Arbeitsweise von Containern am besten.</span><span class="sxs-lookup"><span data-stu-id="96b7f-112">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="96b7f-113">Ein zusätzlicher Vorteil bei der Verwendung von .NET Core besteht darin, dass Sie verschiedene Versionen von .NET für Anwendungen auf dem gleichen Computer parallel ausführen können.</span><span class="sxs-lookup"><span data-stu-id="96b7f-113">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="96b7f-114">Dieser Vorteil ist wichtiger für Server oder virtuelle Computer, die keine Container verwenden, da durch Container die Versionen von .NET isoliert werden, die für die App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="96b7f-114">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="96b7f-115">(Solange diese mit dem zugrunde liegenden Betriebssystem kompatibel sind)</span><span class="sxs-lookup"><span data-stu-id="96b7f-115">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="96b7f-116">Sie sollten .NET Framework für Ihre containerisierte Docker-Serveranwendung verwenden, wenn:</span><span class="sxs-lookup"><span data-stu-id="96b7f-116">You should use .NET Framework for your containerized Docker server application when:</span></span>

- <span data-ttu-id="96b7f-117">Ihre Anwendung derzeit .NET Framework verwendet und starke Abhängigkeiten von Windows aufweist</span><span class="sxs-lookup"><span data-stu-id="96b7f-117">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

- <span data-ttu-id="96b7f-118">Sie Windows-APIs verwenden müssen, die von .NET Core nicht unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="96b7f-118">You need to use Windows APIs that are not supported by .NET Core.</span></span>

- <span data-ttu-id="96b7f-119">Sie .NET-Bibliotheken von Drittanbietern oder NuGet-Pakete verwenden müssen, die für .NET Core nicht verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="96b7f-119">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="96b7f-120">Das Verwenden von .NET Framework auf Docker kann Ihre Bereitstellungen verbessern, indem Bereitstellungsprobleme reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="96b7f-120">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="96b7f-121">Dieses [Lift & Shift-Szenario](https://aka.ms/liftandshiftwithcontainersebook) ist wichtig für das Containerisieren von veralteten Anwendungen, die ursprünglich mit dem herkömmlichen .NET Framework entwickelt wurden, z.B. mit ASP.NET WebForms, MVC-Web-Apps oder WCF-Diensten (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="96b7f-121">This ["lift and shift" scenario](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="96b7f-122">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="96b7f-122">Additional resources</span></span>

- <span data-ttu-id="96b7f-123">**E-Book: Modernize existing .NET Framework applications with Azure and Windows Containers** (E-Book: Modernisieren vorhandener .NET Framework-Anwendungen mit Azure und Windows-Containern)</span><span class="sxs-lookup"><span data-stu-id="96b7f-123">**E-book: Modernize existing .NET Framework applications with Azure and Windows Containers**</span></span>  
    https://aka.ms/liftandshiftwithcontainersebook

- <span data-ttu-id="96b7f-124">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Beispiel-Apps: Modernisieren von veralteten ASP.NET-Web-Apps mithilfe von Windows-Containern)</span><span class="sxs-lookup"><span data-stu-id="96b7f-124">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**</span></span>  
    https://aka.ms/eshopmodernizing

>[!div class="step-by-step"]
><span data-ttu-id="96b7f-125">[Zurück](index.md)
>[Weiter](net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="96b7f-125">[Previous](index.md)
[Next](net-core-container-scenarios.md)</span></span>
