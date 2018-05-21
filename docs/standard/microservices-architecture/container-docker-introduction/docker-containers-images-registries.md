---
title: Docker-Container, -Images und -Registrierungen
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Docker-Container, -Images und -Registrierungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 02ee40ebab37ae1898dc46e215728cba512a23e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="a7284-103">Docker-Container, -Images und -Registrierungen</span><span class="sxs-lookup"><span data-stu-id="a7284-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="a7284-104">Mithilfe von Docker erstellen Entwickler Apps und Dienste und packen diese und ihre Abhängigkeiten in ein Containerimage.</span><span class="sxs-lookup"><span data-stu-id="a7284-104">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="a7284-105">Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="a7284-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="a7284-106">Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a7284-106">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="a7284-107">Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.</span><span class="sxs-lookup"><span data-stu-id="a7284-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="a7284-108">Entwickler sollten Images in einer Registrierung speichern. Diese fungiert als Bibliothek für Images und ist bei der Bereitstellung für Produktionsorchestratoren erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7284-108">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="a7284-109">Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit.</span><span class="sxs-lookup"><span data-stu-id="a7284-109">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="a7284-110">Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.</span><span class="sxs-lookup"><span data-stu-id="a7284-110">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="a7284-111">In Abbildung 2-4 wird dargestellt, wie Images und Registrierungen in Docker mit anderen Komponenten in Beziehung stehen.</span><span class="sxs-lookup"><span data-stu-id="a7284-111">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="a7284-112">Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a7284-112">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="a7284-113">**Abbildung 2-4**.</span><span class="sxs-lookup"><span data-stu-id="a7284-113">**Figure 2-4**.</span></span> <span data-ttu-id="a7284-114">Taxonomie der Docker-Begriffe und -Konzepte</span><span class="sxs-lookup"><span data-stu-id="a7284-114">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="a7284-115">Durch das Einfügen von Images in eine Registrierung können Sie statische und unveränderliche Komponenten der Anwendung speichern, einschließlich aller Abhängigkeiten auf Frameworkebene.</span><span class="sxs-lookup"><span data-stu-id="a7284-115">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="a7284-116">Diese Images können dann mit einer Versionsangabe versehen und in mehreren Umgebungen bereitgestellt werden. Dadurch wird eine konsistente Bereitstellungseinheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7284-116">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="a7284-117">Private Imageregistrierungen, die lokal oder in der Cloud gehostet werden, werden empfohlen, wenn:</span><span class="sxs-lookup"><span data-stu-id="a7284-117">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="a7284-118">Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen</span><span class="sxs-lookup"><span data-stu-id="a7284-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="a7284-119">Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten</span><span class="sxs-lookup"><span data-stu-id="a7284-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="a7284-120">Wenn Ihre Produktionsumgebung beispielsweise die Azure-Cloud ist, möchten Sie Ihre Images wahrscheinlich in Azure Container Registry speichern, um eine minimale Netzwerklatenz zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="a7284-120">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="a7284-121">Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a7284-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a7284-122">[Zurück] (docker-terminology.md) [Weiter] (../net-core-net-framework-containers/index.md)</span><span class="sxs-lookup"><span data-stu-id="a7284-122">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
