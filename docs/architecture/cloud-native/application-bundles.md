---
title: Bundles von cloudbasierten Anwendungen
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Anwendungs Bündel
ms.date: 06/30/2019
ms.openlocfilehash: 6f85ca14ff4d17f9c7a90a9ace51a1448b89fcb3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895683"
---
# <a name="cloud-native-application-bundles"></a><span data-ttu-id="4747c-103">Bundles von cloudbasierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4747c-103">Cloud Native Application Bundles</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4747c-104">Eine Schlüsseleigenschaft von Cloud-native Anwendungen ist, dass Sie die Eigenschaften der Cloud nutzen, um die Entwicklung zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="4747c-104">A key property of cloud-native applications is that they leverage the properties of the cloud to speed up development.</span></span> <span data-ttu-id="4747c-105">Dies bedeutet häufig, dass eine vollständige Anwendung verschiedene Arten von Technologien verwendet.</span><span class="sxs-lookup"><span data-stu-id="4747c-105">This often means that a full application uses different kinds of technologies.</span></span> <span data-ttu-id="4747c-106">Anwendungen können in docker-Containern ausgeliefert werden. einige Dienste können Azure Functions verwenden, während andere Teile direkt auf virtuellen Computern ausgeführt werden können, die auf großen Metal-Servern mit Hardware-GPU-Beschleunigung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4747c-106">Applications may be shipped in Docker containers, some services may use Azure Functions while other parts may run directly on virtual machines allocated on large metal servers with hardware GPU acceleration.</span></span> <span data-ttu-id="4747c-107">Es sind keine zwei cloudbasierten Anwendungen identisch, weshalb es schwierig ist, einen einzigen Mechanismus für den Versand bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4747c-107">No two cloud-native applications are the same, so it's been difficult to provide a single mechanism for shipping them.</span></span>

<span data-ttu-id="4747c-108">Die Docker-Container können auf Kubernetes mithilfe eines Helm-Diagramms für die Bereitstellung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-108">The Docker containers may run on Kubernetes using a Helm Chart for deployment.</span></span> <span data-ttu-id="4747c-109">Die Azure Functions können mithilfe von TERRAFORM-Vorlagen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-109">The Azure Functions may be allocated using Terraform templates.</span></span> <span data-ttu-id="4747c-110">Schließlich können die virtuellen Computer mithilfe von TERRAFORM zugeordnet, aber mithilfe von ansible erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-110">Finally, the virtual machines may be allocated using Terraform but built out using Ansible.</span></span> <span data-ttu-id="4747c-111">Dabei handelt es sich um eine ganze Reihe von Technologien, und es gibt keine Möglichkeit, Sie in einem angemessenen Paket zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="4747c-111">This is a whole mess of technologies and there has been no way to package them all together into a reasonable package.</span></span> <span data-ttu-id="4747c-112">Bis jetzt.</span><span class="sxs-lookup"><span data-stu-id="4747c-112">Until now.</span></span>

<span data-ttu-id="4747c-113">Native Cloud-Anwendungspakete (cnabs) sind ein gemeinsamer Aufwand für eine Reihe von communityorientierten Unternehmen wie Microsoft, docker und hashicorp, um eine Spezifikation für das Verpacken von Paketen verteilter Anwendungen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="4747c-113">Cloud Native Application Bundles (CNABs) are a joint effort of a number of community-minded companies such as Microsoft, Docker, and HashiCorp to develop a specification to package distributed applications.</span></span>

<span data-ttu-id="4747c-114">Der Aufwand wurde im Dezember 2018 angekündigt. es gibt also noch eine Menge Arbeit, um den Aufwand für die größere Community offenzulegen.</span><span class="sxs-lookup"><span data-stu-id="4747c-114">The effort was announced in December of 2018, so there's still a fair bit of work to do to expose the effort to the greater community.</span></span> <span data-ttu-id="4747c-115">Es gibt jedoch bereits eine [offene Spezifikation](https://github.com/deislabs/cnab-spec) und eine Referenz Implementierung, die als [Duffle](https://duffle.sh/)bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="4747c-115">However, there's already an [open specification](https://github.com/deislabs/cnab-spec) and a reference implementation known as [Duffle](https://duffle.sh/).</span></span> <span data-ttu-id="4747c-116">Dieses Tool, das in go geschrieben wurde, ist ein gemeinsamer Aufwand zwischen docker und Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4747c-116">This tool, which was written in Go, is a joint effort between Docker and Microsoft.</span></span>

<span data-ttu-id="4747c-117">Die cnabs können unterschiedliche Arten von Installationstechnologien enthalten.</span><span class="sxs-lookup"><span data-stu-id="4747c-117">The CNABs can contain different kinds of installation technologies.</span></span> <span data-ttu-id="4747c-118">Dadurch können z. b. Helm-Diagramme, TERRAFORM-Vorlagen und ansible-Playbooks im selben Paket nebeneinander vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4747c-118">This allows things like Helm Charts, Terraform templates, and Ansible Playbooks to coexist in the same package.</span></span> <span data-ttu-id="4747c-119">Nachdem die Pakete erstellt wurden, sind Sie eigenständig und portabel. Sie können über einen USB-Stick installiert werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-119">Once built, the packages are self-contained and portable; they can be installed from a USB stick.</span></span>  <span data-ttu-id="4747c-120">Die Pakete werden kryptografisch signiert, um sicherzustellen, dass Sie von der Partei stammen, die Sie beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="4747c-120">The packages are cryptographically signed to ensure they originate from the party they claim.</span></span>

<span data-ttu-id="4747c-121">Der Kern von cnab ist eine Datei mit dem `bundle.json`Namen.</span><span class="sxs-lookup"><span data-stu-id="4747c-121">The core of a CNAB is a file called `bundle.json`.</span></span> <span data-ttu-id="4747c-122">Mit dieser Datei werden die Inhalte des Bündels definiert, also "TERRAFORM" oder "Images" oder etwas anderes.</span><span class="sxs-lookup"><span data-stu-id="4747c-122">This file defines the contents of the bundle, be they Terraform or images or anything else.</span></span> <span data-ttu-id="4747c-123">In Abbildung 11-9 wird ein cnab-Element definiert, das eine TERRAFORM aufruft.</span><span class="sxs-lookup"><span data-stu-id="4747c-123">Figure 11-9 defines a CNAB that invokes some Terraform.</span></span> <span data-ttu-id="4747c-124">Beachten Sie jedoch, dass es tatsächlich ein Aufruf Bild definiert, das zum Aufrufen von TERRAFORM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4747c-124">Notice, however, that it actually defines an invocation image that is used to invoke the Terraform.</span></span> <span data-ttu-id="4747c-125">Beim Verpacken wird die Docker-Datei, die sich im *cnab* -Verzeichnis befindet, in ein docker-Image integriert, das im Paket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4747c-125">When packaged up, the Docker file that is located in the *cnab* directory is built into a Docker image, which will be included in the bundle.</span></span> <span data-ttu-id="4747c-126">Wenn TERRAFORM innerhalb eines docker-Containers im Paket installiert ist, bedeutet dies, dass Benutzer nicht auf Ihrem Computer TERRAFORM installieren müssen, um die Bündelung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4747c-126">Having Terraform installed inside a Docker container in the bundle means that users don't need to have Terraform installed on their machine to run the bundling.</span></span>

```json
{
    "name": "terraform",
    "version": "0.1.0",
    "schemaVersion": "v1.0.0-WD",
    "parameters": {
        "backend": {
            "type": "boolean",
            "defaultValue": false,
            "destination": {
                "env": "TF_VAR_backend"
            }
        }
    },
    "invocationImages": [
        {
        "imageType": "docker",
        "image": "cnab/terraform:latest"
        }
    ],
    "credentials": {
        "tenant_id": {
            "env": "TF_VAR_tenant_id"
        },
        "client_id": {
            "env": "TF_VAR_client_id"
        },
        "client_secret": {
            "env": "TF_VAR_client_secret"
        },
        "subscription_id": {
            "env": "TF_VAR_subscription_id"
        },
        "ssh_authorized_key": {
            "env": "TF_VAR_ssh_authorized_key"
        }
    },
    "actions": {
        "status": {
            "modifies": true
        }
    }
}
```

<span data-ttu-id="4747c-127">**Abbildung 11-13** : ein Beispiel für eine TERRAFORM-Datei</span><span class="sxs-lookup"><span data-stu-id="4747c-127">**Figure 11-13** - An example Terraform file</span></span>

<span data-ttu-id="4747c-128">Der `bundle.json` definiert auch eine Reihe von Parametern, die in TERRAFORM nach unten übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-128">The `bundle.json` also defines a set of parameters that are passed down into the Terraform.</span></span> <span data-ttu-id="4747c-129">Die Parametrisierung des Pakets ermöglicht die Installation in einer Vielzahl unterschiedlicher Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="4747c-129">Parameterization of the bundle allows for installation in a variety of different environments.</span></span>

<span data-ttu-id="4747c-130">Das cnab-Format ist auch flexibel, sodass es für jede beliebige Cloud verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4747c-130">The CNAB format is also flexible, allowing it to be used against any cloud.</span></span> <span data-ttu-id="4747c-131">Sie kann sogar für lokale Lösungen wie [openstack](https://www.openstack.org/)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-131">It can even be used against on-premises solutions such as [OpenStack](https://www.openstack.org/).</span></span>

## <a name="devops-decisions"></a><span data-ttu-id="4747c-132">Devops-Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="4747c-132">DevOps Decisions</span></span>

<span data-ttu-id="4747c-133">Heutzutage gibt es viele großartige Tools im devops-Raum und sogar noch mehr fantastische Bücher und Beiträge zum Erfolg.</span><span class="sxs-lookup"><span data-stu-id="4747c-133">There are so many great tools in the DevOps space these days and even more fantastic books and papers on how to succeed.</span></span> <span data-ttu-id="4747c-134">Ein bevorzugtes Buch für den Einstieg in die devops-Reise ist [das Phoenix-Projekt](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), das die Transformation eines fiktiven Unternehmens von noops zu devops befolgt.</span><span class="sxs-lookup"><span data-stu-id="4747c-134">A favorite book to get started on the DevOps journey is [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), which follows the transformation of a fictional company from NoOps to DevOps.</span></span> <span data-ttu-id="4747c-135">Ein wichtiger Punkt ist, dass devops bei der Bereitstellung komplexer, nativer Cloud-Anwendungen nicht mehr "schön ist".</span><span class="sxs-lookup"><span data-stu-id="4747c-135">One thing is for certain: DevOps is no longer a "nice to have" when deploying complex, Cloud Native Applications.</span></span> <span data-ttu-id="4747c-136">Dies ist eine Anforderung und sollte am Anfang jedes Projekts geplant und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4747c-136">It's a requirement and should be planned for and resourced at the start of any project.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4747c-137">[Zurück](infrastructure-as-code.md)
>[Weiter](summary.md)</span><span class="sxs-lookup"><span data-stu-id="4747c-137">[Previous](infrastructure-as-code.md)
[Next](summary.md)</span></span>
