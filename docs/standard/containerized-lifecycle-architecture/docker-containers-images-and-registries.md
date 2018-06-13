---
title: Docker-Container, -Images und -Registrierungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 43b76f738fa4b7c89423a5b9fac7ef91f40880c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568731"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="c5257-103">Docker-Container, -Images und -Registrierungen</span><span class="sxs-lookup"><span data-stu-id="c5257-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="c5257-104">Wenn Sie Docker verwenden zu können, erstellen Sie eine app oder den Dienst und die Paket sie und ihre Abhängigkeiten in einem containerimage.</span><span class="sxs-lookup"><span data-stu-id="c5257-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="c5257-105">Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="c5257-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="c5257-106">Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert.</span><span class="sxs-lookup"><span data-stu-id="c5257-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="c5257-107">Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.</span><span class="sxs-lookup"><span data-stu-id="c5257-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="c5257-108">Durch das Speichern von Bildern in eine Registrierung, die als eine Bibliothek mit Images fungiert.</span><span class="sxs-lookup"><span data-stu-id="c5257-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="c5257-109">Sie benötigen eine Registrierung bei der Bereitstellung für die Produktion Orchestrators.</span><span class="sxs-lookup"><span data-stu-id="c5257-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="c5257-110">Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit.</span><span class="sxs-lookup"><span data-stu-id="c5257-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="c5257-111">Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.</span><span class="sxs-lookup"><span data-stu-id="c5257-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="c5257-112">Abbildung 1 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="c5257-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="c5257-113">Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c5257-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="c5257-114">Abbildung 1 – 4: Taxonomie Docker-Begriffe und Konzepte</span><span class="sxs-lookup"><span data-stu-id="c5257-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="c5257-115">Verlegen Sie Bilder in einer Registrierung verwenden, können Sie statische und unveränderlichen Anwendungskomponenten, einschließlich aller zugehörigen Abhängigkeiten an, auf einer Frameworkebene speichern.</span><span class="sxs-lookup"><span data-stu-id="c5257-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="c5257-116">Sie können verschiedene Versionen und Bereitstellen von Images in mehreren Umgebungen und und bieten so eine konsistente Bereitstellungseinheit.</span><span class="sxs-lookup"><span data-stu-id="c5257-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="c5257-117">Privates Image-Registrierungen, entweder lokal gehostet oder in der Cloud für den folgenden Situationen empfohlen:</span><span class="sxs-lookup"><span data-stu-id="c5257-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="c5257-118">Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen</span><span class="sxs-lookup"><span data-stu-id="c5257-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="c5257-119">Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten</span><span class="sxs-lookup"><span data-stu-id="c5257-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="c5257-120">Wenn Ihre produktionsumgebung Azure ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist.</span><span class="sxs-lookup"><span data-stu-id="c5257-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="c5257-121">Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c5257-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c5257-122">[Vorherigen] (Docker-terminology.md) [weiter] (Docker-Anwendung-Lebenszyklus/index.md)</span><span class="sxs-lookup"><span data-stu-id="c5257-122">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
