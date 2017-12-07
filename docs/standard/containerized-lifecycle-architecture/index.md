---
title: "Einführung in Container und Docker"
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4e79c4658492516e33efc0b33408e3d4220640f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="f9d07-104">Einführung in Container und Docker</span><span class="sxs-lookup"><span data-stu-id="f9d07-104">Introduction to containers and Docker</span></span>

<span data-ttu-id="f9d07-105">Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="f9d07-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="f9d07-106">Die Containeranwendung kann anschließend als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f9d07-106">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="f9d07-107">Genauso wie die Transportbranche standardisierte Container verwendet, um Waren per Schiff, Bahn oder LKW zu bewegen (unabhängig von der Ladung, die sich darin befindet), fungieren Softwarecontainer als eine Standardeinheit von Software, die verschiedenen Code und Abhängigkeiten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="f9d07-107">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="f9d07-108">Das Containerisieren von Software ermöglicht es Entwicklern und IT-Experten, diese Container ohne oder mit nur geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f9d07-108">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="f9d07-109">Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem (OS) außerdem voneinander.</span><span class="sxs-lookup"><span data-stu-id="f9d07-109">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="f9d07-110">Containeranwendungen werden auf einem Containerhost ausgeführt, der unter dem Betriebssystem (Linux oder Windows) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f9d07-110">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="f9d07-111">Daher haben Container einen erheblich geringeren Speicherbedarf als die Images für virtuelle Computer (VM).</span><span class="sxs-lookup"><span data-stu-id="f9d07-111">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="f9d07-112">Jeder Container kann wie in Abbildung 1-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="f9d07-112">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="f9d07-113">Abbildung 1-1: Mehrere Container, die auf einem Containerhost ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="f9d07-113">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="f9d07-114">In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.</span><span class="sxs-lookup"><span data-stu-id="f9d07-114">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="f9d07-115">Ein weiterer Vorteil, den Containerisierung mit sich bringt, ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="f9d07-115">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="f9d07-116">Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen.</span><span class="sxs-lookup"><span data-stu-id="f9d07-116">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="f9d07-117">Aus der Sicht einer Anwendung ähnelt das *Instanziieren eines Images* (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App.</span><span class="sxs-lookup"><span data-stu-id="f9d07-117">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="f9d07-118">Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9d07-118">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="f9d07-119">Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f9d07-119">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="f9d07-120">Der wichtigste Vorteil ist die Isolation zwischen Entwicklung und Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="f9d07-120">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f9d07-121">[Weiter] (what-is-docker.md)</span><span class="sxs-lookup"><span data-stu-id="f9d07-121">[Next] (what-is-docker.md)</span></span>
