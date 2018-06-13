---
title: Einführung in Container und Docker
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 8d1062aaea85cf810fa07b36252974eceb227c43
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32768280"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="4bfe3-103">Einführung in Container und Docker</span><span class="sxs-lookup"><span data-stu-id="4bfe3-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="4bfe3-104">Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="4bfe3-105">Die Containeranwendung kann anschließend als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="4bfe3-106">Genauso wie die Transportbranche standardisierte Container verwendet, um Waren per Schiff, Bahn oder LKW zu bewegen (unabhängig von der Ladung, die sich darin befindet), fungieren Softwarecontainer als eine Standardeinheit von Software, die verschiedenen Code und Abhängigkeiten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="4bfe3-107">Das Containerisieren von Software ermöglicht es Entwicklern und IT-Experten, diese Container ohne oder mit nur geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="4bfe3-108">Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem (OS) außerdem voneinander.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="4bfe3-109">Containeranwendungen werden auf einem Containerhost ausgeführt, der unter dem Betriebssystem (Linux oder Windows) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="4bfe3-110">Daher haben Container einen erheblich geringeren Speicherbedarf als die Images für virtuelle Computer (VM).</span><span class="sxs-lookup"><span data-stu-id="4bfe3-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="4bfe3-111">Jeder Container kann wie in Abbildung 1-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="4bfe3-112">Abbildung 1-1: Mehrere Container, die auf einem Containerhost ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="4bfe3-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="4bfe3-113">In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="4bfe3-114">Ein weiterer Vorteil, den Containerisierung mit sich bringt, ist die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="4bfe3-115">Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="4bfe3-116">Aus der Sicht einer Anwendung ähnelt das *Instanziieren eines Images* (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="4bfe3-117">Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="4bfe3-118">Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="4bfe3-119">Der wichtigste Vorteil ist die Isolation zwischen Entwicklung und Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="4bfe3-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4bfe3-120">[Weiter] (what-is-docker.md)</span><span class="sxs-lookup"><span data-stu-id="4bfe3-120">[Next] (what-is-docker.md)</span></span>
