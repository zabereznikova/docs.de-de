---
title: Docker-Container, -Images und -Registrierungen
description: Erfahren Sie, die wichtige Rolle, dass Registrierungen wie Docker Bereitstellung von Anwendungen allgemeine spielen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583315"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="22198-103">Docker-Container, -Images und -Registrierungen</span><span class="sxs-lookup"><span data-stu-id="22198-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="22198-104">Mithilfe von Docker erstellen Sie eine app oder -Dienst und -Paket, diese und ihre Abhängigkeiten in einem containerimage.</span><span class="sxs-lookup"><span data-stu-id="22198-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="22198-105">Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="22198-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="22198-106">Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22198-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="22198-107">Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.</span><span class="sxs-lookup"><span data-stu-id="22198-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="22198-108">Speichern Sie Bilder in einer Registrierung, die als eine Bibliothek mit Images fungiert.</span><span class="sxs-lookup"><span data-stu-id="22198-108">You store images in a registry, that acts as a library of images.</span></span> <span data-ttu-id="22198-109">Sie benötigen eine Registrierung bei der Bereitstellung für produktionsorchestratoren.</span><span class="sxs-lookup"><span data-stu-id="22198-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="22198-110">Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit, einschließlich der [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span><span class="sxs-lookup"><span data-stu-id="22198-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="22198-111">Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.</span><span class="sxs-lookup"><span data-stu-id="22198-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="22198-112">Abbildung 1 – 4 zeigt, wie Images und Registrierungen in Docker andere Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="22198-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="22198-113">Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.</span><span class="sxs-lookup"><span data-stu-id="22198-113">It also shows the multiple registry offerings from vendors.</span></span>

![Grundlegende Taxonomie in Docker: Die Registrierung ist wie eine virtuelle Bibliothek, in denen Bilder sind, gespeichert und abgerufen werden, für das Erstellen von Containern, um Dienste oder Web-apps ausführen.](./media/image4.png)

<span data-ttu-id="22198-118">**Abbildung 1-4.**</span><span class="sxs-lookup"><span data-stu-id="22198-118">**Figure 1-4**.</span></span> <span data-ttu-id="22198-119">Taxonomie der Docker-Begriffe und -Konzepte</span><span class="sxs-lookup"><span data-stu-id="22198-119">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="22198-120">Durch das Einfügen von Images in einer Registrierung, können Sie statische und unveränderliche anwendungsbereitstellung, einschließlich aller ihrer Abhängigkeiten auf Frameworkebene speichern.</span><span class="sxs-lookup"><span data-stu-id="22198-120">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="22198-121">Sie können verschiedene Versionen und Images in mehreren Umgebungen bereitstellen und dadurch eine konsistente Bereitstellungseinheit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="22198-121">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="22198-122">Private Imageregistrierungen, die lokal oder in der Cloud gehostet werden, werden empfohlen, wenn:</span><span class="sxs-lookup"><span data-stu-id="22198-122">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="22198-123">Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen</span><span class="sxs-lookup"><span data-stu-id="22198-123">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="22198-124">Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten</span><span class="sxs-lookup"><span data-stu-id="22198-124">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="22198-125">Beispielsweise ist die produktionsumgebung auf Azure, wahrscheinlich Ihre Images speichern möchten [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so, dass die Netzwerklatenz minimal ist.</span><span class="sxs-lookup"><span data-stu-id="22198-125">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="22198-126">Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="22198-126">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="22198-127">[Zurück](docker-terminology.md)
>[Weiter](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="22198-127">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
