---
title: Docker-Containern, Bilder und Registrierungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0cccead8833c63f19b359f830f555e7ff31daa1a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="89420-104">Docker-Containern, Bilder und Registrierungen</span><span class="sxs-lookup"><span data-stu-id="89420-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="89420-105">Wenn Sie Docker verwenden zu können, erstellen Sie eine app oder den Dienst und die Paket sie und ihre Abhängigkeiten in einem containerimage.</span><span class="sxs-lookup"><span data-stu-id="89420-105">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="89420-106">Ein Image ist eine statische Darstellung der app oder Dienst, Konfiguration und seine Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="89420-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="89420-107">Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert.</span><span class="sxs-lookup"><span data-stu-id="89420-107">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="89420-108">Container werden zunächst in einer Entwicklungsumgebung oder PC getestet.</span><span class="sxs-lookup"><span data-stu-id="89420-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="89420-109">Durch das Speichern von Bildern in eine Registrierung, die als eine Bibliothek mit Images fungiert.</span><span class="sxs-lookup"><span data-stu-id="89420-109">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="89420-110">Sie benötigen eine Registrierung bei der Bereitstellung für die Produktion Orchestrators.</span><span class="sxs-lookup"><span data-stu-id="89420-110">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="89420-111">Docker verwaltet eine öffentliche Registrierung über [Docker Hub](https://hub.docker.com/); andere Anbieter stellen Registrierungen für verschiedene Sammlungen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="89420-111">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="89420-112">Alternativ können Unternehmen haben eine private Registrierung on-Premises für ihre eigenen Docker-Images.</span><span class="sxs-lookup"><span data-stu-id="89420-112">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="89420-113">Abbildung 1 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="89420-113">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="89420-114">Es zeigt auch die mehrere Registrierung Angebote von anderen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="89420-114">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="89420-115">Abbildung 1 – 4: Taxonomie Docker-Begriffe und Konzepte</span><span class="sxs-lookup"><span data-stu-id="89420-115">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="89420-116">Verlegen Sie Bilder in einer Registrierung verwenden, können Sie statische und unveränderlichen Anwendungskomponenten, einschließlich aller zugehörigen Abhängigkeiten an, auf einer Frameworkebene speichern.</span><span class="sxs-lookup"><span data-stu-id="89420-116">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="89420-117">Sie können verschiedene Versionen und Bereitstellen von Images in mehreren Umgebungen und und bieten so eine konsistente Bereitstellungseinheit.</span><span class="sxs-lookup"><span data-stu-id="89420-117">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="89420-118">Privates Image-Registrierungen, entweder lokal gehostet oder in der Cloud für den folgenden Situationen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="89420-118">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="89420-119">Die Bilder müssen aufgrund der Vertraulichkeit nicht öffentlich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="89420-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="89420-120">Möchten Sie die minimale Netzwerklatenz zwischen der Bilder und der ausgewählten bereitstellungsumgebung haben.</span><span class="sxs-lookup"><span data-stu-id="89420-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="89420-121">Wenn Ihre produktionsumgebung Azure ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist.</span><span class="sxs-lookup"><span data-stu-id="89420-121">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="89420-122">Auf ähnliche Weise Wenn Ihre produktionsumgebung lokal ist sollten Sie ein lokaler Docker Trusted Registry innerhalb der gleichen lokalen Netzwerk zur Verfügung zu haben.</span><span class="sxs-lookup"><span data-stu-id="89420-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="89420-123">[Vorherigen] (Docker-terminology.md) [weiter] (Docker-Anwendung-Lebenszyklus/index.md)</span><span class="sxs-lookup"><span data-stu-id="89420-123">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
