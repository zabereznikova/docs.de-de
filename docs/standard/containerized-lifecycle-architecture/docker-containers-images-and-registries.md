---
title: Docker-Container, -Images und -Registrierungen
description: Erfahren Sie, die wichtige Rolle, dass Registrierungen wie Docker Bereitstellung von Anwendungen allgemeine spielen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a2e20e09561a5cc91aa29059fb8d19a14205bb5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221198"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="6eb24-103">Docker-Container, -Images und -Registrierungen</span><span class="sxs-lookup"><span data-stu-id="6eb24-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="6eb24-104">Mithilfe von Docker erstellen Sie eine app oder -Dienst und -Paket, diese und ihre Abhängigkeiten in einem containerimage.</span><span class="sxs-lookup"><span data-stu-id="6eb24-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="6eb24-105">Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="6eb24-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="6eb24-106">Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6eb24-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="6eb24-107">Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.</span><span class="sxs-lookup"><span data-stu-id="6eb24-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="6eb24-108">Speichern Sie Bilder in einer Registrierung, fungiert als eine Bibliothek mit Images.</span><span class="sxs-lookup"><span data-stu-id="6eb24-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="6eb24-109">Sie benötigen eine Registrierung bei der Bereitstellung für produktionsorchestratoren.</span><span class="sxs-lookup"><span data-stu-id="6eb24-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="6eb24-110">Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit.</span><span class="sxs-lookup"><span data-stu-id="6eb24-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="6eb24-111">Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.</span><span class="sxs-lookup"><span data-stu-id="6eb24-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="6eb24-112">Abbildung 1 – 4 zeigt, wie Images und Registrierungen in Docker andere Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="6eb24-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="6eb24-113">Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6eb24-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="6eb24-114">Abbildung 1 – 4: Taxonomie der Docker-Begriffe und -Konzepte</span><span class="sxs-lookup"><span data-stu-id="6eb24-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="6eb24-115">Durch das Einfügen von Images in einer Registrierung, können Sie statische und unveränderliche anwendungsbereitstellung, einschließlich aller ihrer Abhängigkeiten auf Frameworkebene speichern.</span><span class="sxs-lookup"><span data-stu-id="6eb24-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="6eb24-116">Sie können verschiedene Versionen und Images in mehreren Umgebungen bereitstellen und dadurch eine konsistente Bereitstellungseinheit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6eb24-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="6eb24-117">Private imageregistrierungen, entweder lokal gehostet oder in der Cloud, werden für den folgenden Situationen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="6eb24-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="6eb24-118">Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen</span><span class="sxs-lookup"><span data-stu-id="6eb24-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="6eb24-119">Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten</span><span class="sxs-lookup"><span data-stu-id="6eb24-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="6eb24-120">Beispielsweise wenn Ihre produktionsumgebung Azure ist, sollten Sie die Images in Azure Container Registry speichern, sodass Netzwerklatenz minimal ist.</span><span class="sxs-lookup"><span data-stu-id="6eb24-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="6eb24-121">Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6eb24-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6eb24-122">[Zurück](docker-terminology.md)
>[Weiter](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="6eb24-122">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
