---
title: Infrastructure-as-Code
description: Einbeziehen von Infrastructure-as-Code (IAC) mit cloudbasierten Anwendungen
ms.date: 05/12/2020
ms.openlocfilehash: 309dd8610ab3b72a6c6da5297f109f822520c5ff
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395344"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="65411-103">Infrastructure-as-Code</span><span class="sxs-lookup"><span data-stu-id="65411-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="65411-104">In der Cloud systemeigene Systeme sind zum Erreichen von Geschwindigkeit und Agilität das Erstellen von Funktionen, Containern und modernen System Entwürfen.</span><span class="sxs-lookup"><span data-stu-id="65411-104">Cloud-native systems embrace microservices, containers, and modern system design to achieve speed and agility.</span></span> <span data-ttu-id="65411-105">Sie bieten automatisierte Build-und releasephasen, um konsistenten und qualitativ hochwertigen Code sicherzustellen</span><span class="sxs-lookup"><span data-stu-id="65411-105">They provide automated build and release stages to ensure consistent and quality code.</span></span> <span data-ttu-id="65411-106">Aber das ist nur ein Teil der Story.</span><span class="sxs-lookup"><span data-stu-id="65411-106">But, that's only part of the story.</span></span> <span data-ttu-id="65411-107">Wie stellen Sie die cloudumgebungen bereit, auf denen diese Systeme ausgeführt werden?</span><span class="sxs-lookup"><span data-stu-id="65411-107">How do you provision the cloud environments upon which these systems run?</span></span>

<span data-ttu-id="65411-108">Moderne Native Cloud-Anwendungen nutzen die weit verbreitete [Infrastruktur als Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)oder `IaC` .</span><span class="sxs-lookup"><span data-stu-id="65411-108">Modern cloud-native applications embrace the widely accepted practice of [Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), or `IaC`.</span></span>  <span data-ttu-id="65411-109">Mit IAC automatisieren Sie die Platt Form Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="65411-109">With IaC, you automate platform provisioning.</span></span> <span data-ttu-id="65411-110">Sie wenden im Wesentlichen Software Entwicklungsverfahren wie Tests und Versionsverwaltung auf Ihre devops-Verfahren an.</span><span class="sxs-lookup"><span data-stu-id="65411-110">You essentially apply software engineering practices such as testing and versioning to your DevOps practices.</span></span> <span data-ttu-id="65411-111">Ihre Infrastruktur und bereit Stellungen sind automatisiert, konsistent und wiederholbar.</span><span class="sxs-lookup"><span data-stu-id="65411-111">Your infrastructure and deployments are automated, consistent, and repeatable.</span></span> <span data-ttu-id="65411-112">Ebenso wie Continuous Delivery das herkömmliche Modell manueller bereit Stellungen automatisiert, wird Infrastructure as Code (IAC) weiterentwickelt, wie Anwendungsumgebungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="65411-112">Just as continuous delivery automated the traditional model of manual deployments, Infrastructure as Code (IaC) is evolving how application environments are managed.</span></span>

<span data-ttu-id="65411-113">Tools wie Azure Resource Manager (Arm), TERRAFORM und die Azure-Befehlszeilenschnittstelle (CLI) ermöglichen Ihnen die deklarative Skripterstellung für die erforderliche cloudinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="65411-113">Tools like Azure Resource Manager (ARM), Terraform, and the Azure Command Line Interface (CLI) enable you to declaratively script the cloud infrastructure you require.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="65411-114">Azure-Ressourcen-Manager-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="65411-114">Azure Resource Manager templates</span></span>

<span data-ttu-id="65411-115">Arm steht für [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span><span class="sxs-lookup"><span data-stu-id="65411-115">ARM stands for [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span></span> <span data-ttu-id="65411-116">Dabei handelt es sich um eine API-Bereitstellungs-Engine, die in Azure integriert ist und als API-Dienst verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="65411-116">It's an API provisioning engine that is built into Azure and exposed as an API service.</span></span> <span data-ttu-id="65411-117">Mit Arm können Sie die in der Azure-Ressourcengruppe enthaltenen Ressourcen in einem einzigen, koordinierten Vorgang bereitstellen, aktualisieren, löschen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="65411-117">ARM enables you to deploy, update, delete, and manage the resources contained in Azure resource group in a single, coordinated operation.</span></span> <span data-ttu-id="65411-118">Sie stellen der Engine eine JSON-basierte Vorlage bereit, die die benötigten Ressourcen und deren Konfiguration angibt.</span><span class="sxs-lookup"><span data-stu-id="65411-118">You provide the engine with a JSON-based template that specifies the resources you require and their configuration.</span></span> <span data-ttu-id="65411-119">Arm orchestriert die Bereitstellung automatisch in der richtigen Reihenfolge, in der Abhängigkeiten berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="65411-119">ARM automatically orchestrates the deployment in the correct order respecting dependencies.</span></span> <span data-ttu-id="65411-120">Die Engine stellt Idempotenz sicher.</span><span class="sxs-lookup"><span data-stu-id="65411-120">The engine ensures idempotency.</span></span> <span data-ttu-id="65411-121">Wenn eine gewünschte Ressource bereits mit derselben Konfiguration vorhanden ist, wird die Bereitstellung ignoriert.</span><span class="sxs-lookup"><span data-stu-id="65411-121">If a desired resource already exists with the same configuration, provisioning will be ignored.</span></span>

<span data-ttu-id="65411-122">Azure Resource Manager Vorlagen sind eine JSON-basierte Sprache zum Definieren verschiedener Ressourcen in Azure.</span><span class="sxs-lookup"><span data-stu-id="65411-122">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="65411-123">Das grundlegende Schema sieht in etwa wie in Abbildung 10-14 aus.</span><span class="sxs-lookup"><span data-stu-id="65411-123">The basic schema looks something like Figure 10-14.</span></span>

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

<span data-ttu-id="65411-124">**Abbildung 10-14** : das Schema für eine Ressourcen-Manager Vorlage</span><span class="sxs-lookup"><span data-stu-id="65411-124">**Figure 10-14** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="65411-125">Innerhalb dieser Vorlage kann ein Speicher Container im Ressourcenabschnitt wie folgt definiert werden:</span><span class="sxs-lookup"><span data-stu-id="65411-125">Within this template, one might define a storage container inside the resources section like so:</span></span>

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

<span data-ttu-id="65411-126">**Abbildung 10-15** : ein Beispiel für ein Speicherkonto, das in einer Ressourcen-Manager Vorlage definiert ist</span><span class="sxs-lookup"><span data-stu-id="65411-126">**Figure 10-15** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="65411-127">Eine Arm-Vorlage kann mit dynamischen Umgebungs-und Konfigurationsinformationen parametrisiert werden.</span><span class="sxs-lookup"><span data-stu-id="65411-127">An ARM template can be parameterized with dynamic environment and configuration information.</span></span> <span data-ttu-id="65411-128">Dadurch kann die Anwendung wieder verwendet werden, um unterschiedliche Umgebungen zu definieren, wie z. b. Entwicklung, QA oder Produktion.</span><span class="sxs-lookup"><span data-stu-id="65411-128">Doing so enables it to be reused to define different environments, such as development, QA, or production.</span></span> <span data-ttu-id="65411-129">Normalerweise werden von der Vorlage alle Ressourcen innerhalb einer einzelnen Azure-Ressourcengruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="65411-129">Normally, the template creates all resources within a single Azure resource group.</span></span> <span data-ttu-id="65411-130">Es ist möglich, bei Bedarf mehrere Ressourcengruppen in einer einzigen Ressourcen-Manager Vorlage zu definieren.</span><span class="sxs-lookup"><span data-stu-id="65411-130">It's possible to define multiple resource groups in a single Resource Manager template, if needed.</span></span> <span data-ttu-id="65411-131">Sie können alle Ressourcen in einer Umgebung löschen, indem Sie die Ressourcengruppe selbst löschen.</span><span class="sxs-lookup"><span data-stu-id="65411-131">You can delete all resources in an environment by deleting the resource group itself.</span></span> <span data-ttu-id="65411-132">Die Kostenanalyse kann auch auf Ressourcengruppen Ebene ausgeführt werden und ermöglicht eine schnelle Erfassung der Kosten für jede Umgebung.</span><span class="sxs-lookup"><span data-stu-id="65411-132">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="65411-133">Im [Azure-Schnellstart Vorlagen](https://github.com/Azure/azure-quickstart-templates) -Projekt auf GitHub stehen zahlreiche Beispiele oder arm-Vorlagen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="65411-133">There are many examples or ARM templates available in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub.</span></span> <span data-ttu-id="65411-134">Sie können dabei helfen, die Erstellung einer neuen Vorlage zu beschleunigen oder eine vorhandene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65411-134">They can help accelerate creating a new template or modifying an existing one.</span></span>

<span data-ttu-id="65411-135">Ressourcen-Manager Vorlagen können auf viele Arten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65411-135">Resource Manager templates can be run in many of ways.</span></span> <span data-ttu-id="65411-136">Die einfachste Möglichkeit besteht darin, Sie einfach in den Azure-Portal einzufügen.</span><span class="sxs-lookup"><span data-stu-id="65411-136">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="65411-137">Bei experimentellen bereit Stellungen kann diese Methode schnell sein.</span><span class="sxs-lookup"><span data-stu-id="65411-137">For experimental deployments, this method can be quick.</span></span> <span data-ttu-id="65411-138">Sie können auch als Teil eines Build-oder Releaseprozesses in Azure devops ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65411-138">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="65411-139">Es gibt Aufgaben, die Verbindungen mit Azure zum Ausführen der Vorlagen nutzen.</span><span class="sxs-lookup"><span data-stu-id="65411-139">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="65411-140">Änderungen an Ressourcen-Manager Vorlagen werden inkrementell angewendet, was bedeutet, dass zum Hinzufügen einer neuen Ressource diese lediglich der Vorlage hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="65411-140">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="65411-141">Die Tools Stimmen die Unterschiede zwischen den aktuellen Ressourcen und den in der Vorlage definierten Ressourcen ab.</span><span class="sxs-lookup"><span data-stu-id="65411-141">The tooling will reconcile differences between the current resources and those defined in the template.</span></span> <span data-ttu-id="65411-142">Anschließend werden Ressourcen erstellt oder geändert, sodass Sie mit den in der Vorlage definierten Vorlagen verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="65411-142">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="65411-143">Terraform</span><span class="sxs-lookup"><span data-stu-id="65411-143">Terraform</span></span>

<span data-ttu-id="65411-144">Native Cloud-Anwendungen werden häufig als konstruiert `cloud agnostic` .</span><span class="sxs-lookup"><span data-stu-id="65411-144">Cloud-native applications are often constructed to be `cloud agnostic`.</span></span> <span data-ttu-id="65411-145">Dies bedeutet, dass die Anwendung nicht eng mit einem bestimmten cloudanbieter verknüpft ist und in jedem Public Cloud bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="65411-145">Being so means the application isn't tightly coupled to a particular cloud vendor and can be deployed to any public cloud.</span></span>

<span data-ttu-id="65411-146">[TERRAFORM](https://www.terraform.io/) ist ein kommerzielles Vorlagen Tool, das in der Cloud native Anwendungen für alle wichtigen cloudplayer bereitstellen kann: Azure, Google Cloud Platform, AWS und alicloud.</span><span class="sxs-lookup"><span data-stu-id="65411-146">[Terraform](https://www.terraform.io/) is commercial templating tool that can provision cloud-native applications across all the major cloud players: Azure, Google Cloud Platform, AWS, and AliCloud.</span></span> <span data-ttu-id="65411-147">Anstatt JSON als Vorlagen Definitions Sprache zu verwenden, wird die etwas genauere YAML verwendet.</span><span class="sxs-lookup"><span data-stu-id="65411-147">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="65411-148">Eine TERRAFORM-Beispieldatei, die die gleiche wie die vorherige Ressourcen-Manager Vorlage (Abbildung 10-15) verwendet, ist in Abbildung 10-16 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="65411-148">An example Terraform file that does the same as the previous Resource Manager template (Figure 10-15) is shown in Figure 10-16:</span></span>

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

<span data-ttu-id="65411-149">**Abbildung 10-16** : ein Beispiel für eine Ressourcen-Manager Vorlage</span><span class="sxs-lookup"><span data-stu-id="65411-149">**Figure 10-16** - An example of a Resource Manager template</span></span>

<span data-ttu-id="65411-150">TERRAFORM bietet auch intuitive Fehlermeldungen für problemvorlagen.</span><span class="sxs-lookup"><span data-stu-id="65411-150">Terraform also provides intuitive error messages for problem templates.</span></span> <span data-ttu-id="65411-151">Es gibt auch eine praktische Validate-Aufgabe, die in der Buildphase zum frühen erfassen von Vorlagen Fehlern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="65411-151">There's also a handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="65411-152">Wie bei Ressourcen-Manager Vorlagen sind Befehlszeilen Tools zum Bereitstellen von TERRAFORM-Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65411-152">As with Resource Manager templates, command-line tools are available to deploy Terraform templates.</span></span> <span data-ttu-id="65411-153">Es gibt auch von der Community erstellte Aufgaben in Azure Pipelines, die TERRAFORM-Vorlagen validieren und anwenden können.</span><span class="sxs-lookup"><span data-stu-id="65411-153">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="65411-154">Manchmal geben TERRAFORM-und Arm-Vorlagen sinnvolle Werte aus, z. b. eine Verbindungs Zeichenfolge für eine neu erstellte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="65411-154">Sometimes Terraform and ARM templates output meaningful values, such as a connection string to a newly created database.</span></span> <span data-ttu-id="65411-155">Diese Informationen können in der Buildpipeline aufgezeichnet und in nachfolgenden Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65411-155">This information can be captured in the build pipeline and used in subsequent tasks.</span></span>

## <a name="azure-cli-scripts-and-tasks"></a><span data-ttu-id="65411-156">Skripts und Aufgaben Azure CLI</span><span class="sxs-lookup"><span data-stu-id="65411-156">Azure CLI Scripts and Tasks</span></span>

<span data-ttu-id="65411-157">Zum Schluss können Sie [Azure CLI](https://docs.microsoft.com/cli/azure/) für die deklarative Skripterstellung für Ihre cloudinfrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="65411-157">Finally, you can leverage [Azure CLI](https://docs.microsoft.com/cli/azure/) to declaratively script your cloud infrastructure.</span></span> <span data-ttu-id="65411-158">Azure CLI Skripts können erstellt, gefunden und freigegeben werden, um nahezu jede Azure-Ressource bereitzustellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="65411-158">Azure CLI scripts can be created, found, and shared to provision and configure almost any Azure resource.</span></span> <span data-ttu-id="65411-159">Die CLI ist einfach zu verwenden, und zwar mit einer sanften Lernkurve.</span><span class="sxs-lookup"><span data-stu-id="65411-159">The CLI is simple to use with a gentle learning curve.</span></span> <span data-ttu-id="65411-160">Skripts werden entweder in PowerShell oder in bash ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="65411-160">Scripts are executed within either PowerShell or Bash.</span></span> <span data-ttu-id="65411-161">Sie sind auch unkompliziert zu debuggen, besonders im Vergleich zu arm-Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="65411-161">They're also straightforward to debug, especially when compared with ARM templates.</span></span>

<span data-ttu-id="65411-162">Azure CLI Skripts funktionieren gut, wenn Sie Ihre Infrastruktur abbrechen und erneut bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="65411-162">Azure CLI scripts work well when you need to tear down and redeploy your infrastructure.</span></span> <span data-ttu-id="65411-163">Das Aktualisieren einer vorhandenen Umgebung kann knifflig sein.</span><span class="sxs-lookup"><span data-stu-id="65411-163">Updating an existing environment can be tricky.</span></span> <span data-ttu-id="65411-164">Viele CLI-Befehle sind nicht idempotent.</span><span class="sxs-lookup"><span data-stu-id="65411-164">Many CLI commands aren't idempotent.</span></span> <span data-ttu-id="65411-165">Dies bedeutet, dass Sie die Ressource jedes Mal neu erstellen, wenn Sie ausgeführt wird, auch wenn die Ressource bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="65411-165">That means they'll recreate the resource each time they're run, even if the resource already exists.</span></span> <span data-ttu-id="65411-166">Es ist immer möglich, Code hinzuzufügen, der überprüft, ob jede Ressource vorhanden ist, bevor Sie erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="65411-166">It's always possible to add code that checks for the existence of each resource before creating it.</span></span> <span data-ttu-id="65411-167">Allerdings kann Ihr Skript mit einem blobverhalten und schwer zu verwalten werden.</span><span class="sxs-lookup"><span data-stu-id="65411-167">But, doing so, your script can become bloated and difficult to manage.</span></span>

<span data-ttu-id="65411-168">Diese Skripts können auch in Azure devops-Pipelines als eingebettet werden `Azure CLI tasks` .</span><span class="sxs-lookup"><span data-stu-id="65411-168">These scripts can also be embedded in Azure DevOps pipelines as `Azure CLI tasks`.</span></span> <span data-ttu-id="65411-169">Beim Ausführen der Pipeline wird das Skript aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="65411-169">Executing the pipeline invokes the script.</span></span>

<span data-ttu-id="65411-170">In Abbildung 10-17 wird ein YAML-Code Ausschnitt gezeigt, der die Version von Azure CLI und die Details des Abonnements auflistet.</span><span class="sxs-lookup"><span data-stu-id="65411-170">Figure 10-17 shows a YAML snippet that lists the version of Azure CLI and the details of the subscription.</span></span> <span data-ttu-id="65411-171">Beachten Sie, wie Azure CLI Befehle in ein Inline Skript eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="65411-171">Note how Azure CLI commands are included in an inline script.</span></span>

```yaml
- task: AzureCLI@2
  displayName: Azure CLI
  inputs:
    azureSubscription: <Name of the Azure Resource Manager service connection>
    scriptType: ps
    scriptLocation: inlineScript
    inlineScript: |
      az --version
      az account show
```

<span data-ttu-id="65411-172">**Abbildung 10-17** -Azure CLI Skript</span><span class="sxs-lookup"><span data-stu-id="65411-172">**Figure 10-17** - Azure CLI script</span></span>

<span data-ttu-id="65411-173">Im Artikel [Was ist Infrastructure as Code, wird](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)der Autor Sam Guckenheimer beschrieben, wie "Teams, die IAC implementieren, schnelle und skalierbare Umgebungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="65411-173">In the article, [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), Author Sam Guckenheimer describes how, "Teams who implement IaC can deliver stable environments rapidly and at scale.</span></span> <span data-ttu-id="65411-174">Teams vermeiden die manuelle Konfiguration von Umgebungen und erzwingen Konsistenz, indem Sie den gewünschten Zustand ihrer Umgebungen über Code darstellen.</span><span class="sxs-lookup"><span data-stu-id="65411-174">Teams avoid manual configuration of environments and enforce consistency by representing the desired state of their environments via code.</span></span> <span data-ttu-id="65411-175">Infrastruktur Bereitstellungen mit IAC sind wiederholbar und verhindern Lauf Zeit Probleme, die durch Konfigurations Abweichung oder fehlende Abhängigkeiten verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="65411-175">Infrastructure deployments with IaC are repeatable and prevent runtime issues caused by configuration drift or missing dependencies.</span></span> <span data-ttu-id="65411-176">Devops-Teams können mit einem einheitlichen Satz von Methoden und Tools zusammenarbeiten, um Anwendungen und deren unterstützende Infrastruktur schnell, zuverlässig und skalierbar bereitzustellen. "</span><span class="sxs-lookup"><span data-stu-id="65411-176">DevOps teams can work together with a unified set of practices and tools to deliver applications and their supporting infrastructure rapidly, reliably, and at scale."</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="65411-177">[Zurück](feature-flags.md)
>[Weiter](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="65411-177">[Previous](feature-flags.md)
[Next](application-bundles.md)</span></span>
