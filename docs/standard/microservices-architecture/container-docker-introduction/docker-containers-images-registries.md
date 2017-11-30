---
title: Docker-Containern, Bilder und Registrierungen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Docker-Containern, Bilder und Registrierungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="82618-104">Docker-Containern, Bilder und Registrierungen</span><span class="sxs-lookup"><span data-stu-id="82618-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="82618-105">Wenn Sie Docker verwenden zu können, erstellt ein Entwickler eine Anwendung oder Dienst und Pakete sie und ihre Abhängigkeiten in einem containerimage.</span><span class="sxs-lookup"><span data-stu-id="82618-105">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="82618-106">Ein Image ist eine statische Darstellung der app oder Dienst, Konfiguration und seine Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="82618-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="82618-107">Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert.</span><span class="sxs-lookup"><span data-stu-id="82618-107">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="82618-108">Container werden zunächst in einer Entwicklungsumgebung oder PC getestet.</span><span class="sxs-lookup"><span data-stu-id="82618-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="82618-109">Entwickler sollten Bilder in einer Registrierung speichern die fungiert als eine Bibliothek mit Images und ist erforderlich, wenn für die Produktion Orchestrators bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="82618-109">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="82618-110">Docker verwaltet eine öffentliche Registrierung über [Docker Hub](https://hub.docker.com/); andere Anbieter stellen Registrierungen für verschiedene Sammlungen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="82618-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="82618-111">Alternativ können Unternehmen haben eine private Registrierung on-Premises für ihre eigenen Docker-Images.</span><span class="sxs-lookup"><span data-stu-id="82618-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="82618-112">Abbildung 2 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="82618-112">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="82618-113">Es zeigt auch die mehrere Registrierung Angebote von anderen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="82618-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="82618-114">**Abbildung 2 – 4**.</span><span class="sxs-lookup"><span data-stu-id="82618-114">**Figure 2-4**.</span></span> <span data-ttu-id="82618-115">Taxonomie Docker-Begriffe und Konzepte</span><span class="sxs-lookup"><span data-stu-id="82618-115">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="82618-116">Einfügen von Bildern in einer Registrierung ermöglicht das Speichern von statischen und unveränderlichen Anwendungskomponenten, z. B. alle ihre Abhängigkeiten auf einer Frameworkebene.</span><span class="sxs-lookup"><span data-stu-id="82618-116">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="82618-117">Diese Bilder können mit Versionsangabe und in mehreren Umgebungen bereitgestellt werden und bieten daher eine konsistente Bereitstellungseinheit.</span><span class="sxs-lookup"><span data-stu-id="82618-117">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="82618-118">Privates Image-Registrierungen entweder gehostet lokal oder in der Cloud werden empfohlen, wenn:</span><span class="sxs-lookup"><span data-stu-id="82618-118">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="82618-119">Die Bilder müssen aufgrund der Vertraulichkeit nicht öffentlich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="82618-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="82618-120">Möchten Sie die minimale Netzwerklatenz zwischen der Bilder und der ausgewählten bereitstellungsumgebung haben.</span><span class="sxs-lookup"><span data-stu-id="82618-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="82618-121">Wenn Ihre produktionsumgebung Azure-Cloud ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist.</span><span class="sxs-lookup"><span data-stu-id="82618-121">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="82618-122">Auf ähnliche Weise Wenn Ihre produktionsumgebung lokal ist sollten Sie ein lokaler Docker Trusted Registry innerhalb der gleichen lokalen Netzwerk zur Verfügung zu haben.</span><span class="sxs-lookup"><span data-stu-id="82618-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="82618-123">[Vorherigen] (Docker-terminology.md) [weiter] (.. /NET-Core-NET-Framework-Containers/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="82618-123">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
