---
title: "Einführung in Container und Docker"
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Einführung in Container und Docker"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8809ae41609ff0e2d2fc969d412cb5edc8939653
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="71b93-104">Einführung in Container und Docker</span><span class="sxs-lookup"><span data-stu-id="71b93-104">Introduction to Containers and Docker</span></span>

<span data-ttu-id="71b93-105">Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="71b93-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="71b93-106">Die Containeranwendung kann als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem (OS) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="71b93-106">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="71b93-107">So wie das Versenden von Containern es ermöglicht, Güter unabhängig von der enthaltenen Fracht per Schiff, Zug oder LKW zu transportieren, agieren Softwarecontainer als Standardeinheit für Software und können verschiedenen Code und verschiedene Abhängigkeiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="71b93-107">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="71b93-108">Das Containerisieren von Software auf diese Weise ermöglicht es Entwicklern und IT-Experten, diese ohne oder mit geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="71b93-108">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="71b93-109">Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem außerdem voneinander.</span><span class="sxs-lookup"><span data-stu-id="71b93-109">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="71b93-110">Containeranwendungen werden auf einem Containerhost ausgeführt, der auf dem Betriebssystem (Linux oder Windows) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71b93-110">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="71b93-111">Daher haben Container einen erheblich geringeren Speicherbedarf als die Images für virtuelle Computer (VM).</span><span class="sxs-lookup"><span data-stu-id="71b93-111">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="71b93-112">Jeder Container kann wie in Abbildung 2-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="71b93-112">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="71b93-113">In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.</span><span class="sxs-lookup"><span data-stu-id="71b93-113">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="71b93-114">**Abbildung 2-1**.</span><span class="sxs-lookup"><span data-stu-id="71b93-114">**Figure 2-1**.</span></span> <span data-ttu-id="71b93-115">Mehrere Container, die auf einem Containerhost ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="71b93-115">Multiple containers running on a container host</span></span>

<span data-ttu-id="71b93-116">Ein weiterer Vorteil der Containerisierung ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="71b93-116">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="71b93-117">Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen.</span><span class="sxs-lookup"><span data-stu-id="71b93-117">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="71b93-118">Aus der Sicht einer Anwendung ähnelt das Instanziieren eines Images (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App.</span><span class="sxs-lookup"><span data-stu-id="71b93-118">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="71b93-119">Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="71b93-119">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="71b93-120">Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="71b93-120">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="71b93-121">Der wichtigste Vorteil ist die Isolation zwischen Entwicklung und Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="71b93-121">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="71b93-122">[Zurück] (../index.md) [Weiter] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="71b93-122">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
