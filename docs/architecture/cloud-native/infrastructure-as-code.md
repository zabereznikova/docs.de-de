---
title: Infrastruktur als Code
description: Architektur von Cloud Native .net-apps für Azure | Infrastruktur als Code
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841780"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="e621f-103">Infrastruktur als Code</span><span class="sxs-lookup"><span data-stu-id="e621f-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e621f-104">Native Cloud-Anwendungen nutzen tendenziell alle Arten von fantastischen Platform-as-a-Service-Komponenten (Platform-as-a-Service, PAS).</span><span class="sxs-lookup"><span data-stu-id="e621f-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="e621f-105">In einer cloudplattform wie Azure können diese Komponenten z. b. Speicher, Service Bus und den signalr-Dienst umfassen.</span><span class="sxs-lookup"><span data-stu-id="e621f-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="e621f-106">Wenn Anwendungen komplizierter werden, wird die Anzahl der verwendeten Dienste wahrscheinlich vergrößert.</span><span class="sxs-lookup"><span data-stu-id="e621f-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="e621f-107">Ebenso wie Continuous Delivery das herkömmliche Modell der Bereitstellung in einer Umgebung manuell unterbrochen hat, brach die schnelle Geschwindigkeit der Änderung auch das Modell einer zentralisierten IT-Gruppe zur Verwaltung von IT-Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="e621f-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="e621f-108">Das aufbauen von Umgebungen kann auch automatisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e621f-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="e621f-109">Es gibt eine Vielzahl von bewährten Tools, die den Prozess vereinfachen können.</span><span class="sxs-lookup"><span data-stu-id="e621f-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="e621f-110">Azure Resource Manager Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e621f-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="e621f-111">Azure Resource Manager Vorlagen sind eine JSON-basierte Sprache zum Definieren verschiedener Ressourcen in Azure.</span><span class="sxs-lookup"><span data-stu-id="e621f-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="e621f-112">Das grundlegende Schema sieht in etwa wie in Abbildung 11-10 aus.</span><span class="sxs-lookup"><span data-stu-id="e621f-112">The basic schema looks something like Figure 11-10.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="e621f-113">**Abbildung 11-10** : das Schema für eine Ressourcen-Manager Vorlage</span><span class="sxs-lookup"><span data-stu-id="e621f-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="e621f-114">Innerhalb dieser Vorlage kann ein Speicher Container im Ressourcenabschnitt wie folgt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="e621f-114">Within this template, one might define a storage container inside the resources section like so:</span></span>

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="e621f-115">**Abbildung 11-11** : ein Beispiel für ein Speicherkonto, das in einer Ressourcen-Manager Vorlage definiert ist</span><span class="sxs-lookup"><span data-stu-id="e621f-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="e621f-116">Die Vorlagen können parametrisiert werden, damit eine Vorlage mit unterschiedlichen Einstellungen wieder verwendet werden kann, um Entwicklungs-, QA-und Produktionsumgebungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e621f-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="e621f-117">Dadurch lassen sich Überraschungen bei der Migration zu einer höheren Umgebung vermeiden, die in den niedrigeren Umgebungen anders eingerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="e621f-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="e621f-118">Die Ressourcen, die in einer Vorlage definiert sind, werden in der Regel in einer einzelnen Ressourcengruppe in Azure erstellt (es ist möglich, mehrere Ressourcengruppen in einer einzigen Ressourcen-Manager Vorlage zu definieren, aber ungewöhnliche).</span><span class="sxs-lookup"><span data-stu-id="e621f-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="e621f-119">Dadurch ist es sehr einfach, eine Umgebung zu löschen, indem einfach die Ressourcengruppe als Ganzes gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="e621f-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="e621f-120">Die Kostenanalyse kann auch auf Ressourcengruppen Ebene ausgeführt werden und ermöglicht eine schnelle Erfassung der Kosten für jede Umgebung.</span><span class="sxs-lookup"><span data-stu-id="e621f-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="e621f-121">Es gibt zahlreiche Beispiel Vorlagen, die im [Azure-Schnellstart Vorlagen](https://github.com/Azure/azure-quickstart-templates) -Projekt auf GitHub definiert sind und beim Starten mit einer neuen Vorlage oder beim Hinzufügen zu einer vorhandenen Vorlage eine Reihe von Informationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="e621f-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="e621f-122">Ressourcen-Manager Vorlagen können auf unterschiedlichste Weise ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e621f-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="e621f-123">Die einfachste Möglichkeit besteht darin, Sie einfach in den Azure-Portal einzufügen.</span><span class="sxs-lookup"><span data-stu-id="e621f-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="e621f-124">Bei experimentellen bereit Stellungen kann diese Methode sehr schnell sein.</span><span class="sxs-lookup"><span data-stu-id="e621f-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="e621f-125">Sie können auch als Teil eines Build-oder Releaseprozesses in Azure devops ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e621f-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="e621f-126">Es gibt Aufgaben, die Verbindungen mit Azure zum Ausführen der Vorlagen nutzen.</span><span class="sxs-lookup"><span data-stu-id="e621f-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="e621f-127">Änderungen an Ressourcen-Manager Vorlagen werden inkrementell angewendet, was bedeutet, dass zum Hinzufügen einer neuen Ressource diese lediglich der Vorlage hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="e621f-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="e621f-128">Das Tool verarbeitet das Vergleich der aktuellen Ressourcengruppe mit der gewünschten Ressourcengruppe, die in der Vorlage definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e621f-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="e621f-129">Anschließend werden Ressourcen erstellt oder geändert, sodass Sie mit den in der Vorlage definierten Vorlagen verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e621f-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="e621f-130">TERRAFORM</span><span class="sxs-lookup"><span data-stu-id="e621f-130">Terraform</span></span>

<span data-ttu-id="e621f-131">Ein wahrgenommener Nachteil von Ressourcen-Manager Vorlagen ist, dass Sie für die Azure-Cloud spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="e621f-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="e621f-132">Es ist ungewöhnlich, Anwendungen zu erstellen, die Ressourcen aus mehr als einer Cloud enthalten. in Fällen, in denen das Unternehmen auf eine spektakuläre Betriebszeit basiert, sind die Kosten für die Unterstützung mehrerer Clouds möglicherweise lohnenswert.</span><span class="sxs-lookup"><span data-stu-id="e621f-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="e621f-133">Wenn eine Vorlagen Sprache vorhanden war, die in jeder Cloud verwendet werden konnte, wäre es auch möglich, dass Entwickler Kenntnisse viel besser portierbar sind.</span><span class="sxs-lookup"><span data-stu-id="e621f-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="e621f-134">Es gibt mehrere Technologien, die genau das tun.</span><span class="sxs-lookup"><span data-stu-id="e621f-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="e621f-135">Das ausgereifte Angebot in diesem Bereich wird als [TERRAFORM](https://www.terraform.io/)bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e621f-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="e621f-136">TERRAFORM unterstützt jeden großen Cloud-Player, wie z. b. Azure, Google Cloud Platform, AWS und alicloud, und unterstützt auch Dutzende von neben Akteuren, wie z. b. heroku und digitalozean.</span><span class="sxs-lookup"><span data-stu-id="e621f-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="e621f-137">Anstatt JSON als Vorlagen Definitions Sprache zu verwenden, wird die etwas genauere YAML verwendet.</span><span class="sxs-lookup"><span data-stu-id="e621f-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="e621f-138">Eine TERRAFORM-Beispieldatei, die die gleiche wie die vorherige Ressourcen-Manager Vorlage (Abbildung 11-11) verwendet, ist in Abbildung 11-12 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e621f-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="e621f-139">**Abbildung 11-12** : ein Beispiel für eine Ressourcen-Manager Vorlage</span><span class="sxs-lookup"><span data-stu-id="e621f-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="e621f-140">TERRAFORM bietet eine bessere Möglichkeit, sinnvolle Fehlermeldungen bereitzustellen, wenn eine Ressource aufgrund eines Fehlers in der Vorlage nicht bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e621f-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="e621f-141">Dies ist ein Bereich, in dem Ressourcen-Manager Vorlagen einige fortlaufende Herausforderungen haben.</span><span class="sxs-lookup"><span data-stu-id="e621f-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="e621f-142">Es gibt auch eine sehr praktische Validate-Aufgabe, die in der Buildphase zum frühen erfassen von Vorlagen Fehlern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e621f-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="e621f-143">Wie bei Ressourcen-Manager Vorlagen gibt es Befehlszeilen Tools, die zum Bereitstellen von TERRAFORM-Vorlagen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e621f-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="e621f-144">Es gibt auch von der Community erstellte Aufgaben in Azure Pipelines, die TERRAFORM-Vorlagen validieren und anwenden können.</span><span class="sxs-lookup"><span data-stu-id="e621f-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="e621f-145">Wenn die TERRAFORM-oder Ressourcen-Manager Vorlage interessante Werte (z. b. die Verbindungs Zeichenfolge) für eine neu erstellte Datenbank ausgibt, können Sie in der Buildpipeline aufgezeichnet und in nachfolgenden Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e621f-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e621f-146">[Zurück](devops.md)
>[Weiter](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="e621f-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>
