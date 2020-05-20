---
title: Infrastructure-as-Code
description: Einbeziehen von Infrastructure-as-Code (IAC) mit cloudbasierten Anwendungen
ms.date: 05/13/2020
ms.openlocfilehash: cfc9e1f0b2733048d5921de5a0400998c282b1fa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613953"
---
# <a name="infrastructure-as-code"></a>Infrastructure-as-Code

In der Cloud systemeigene Systeme sind zum Erreichen von Geschwindigkeit und Agilität das Erstellen von Funktionen, Containern und modernen System Entwürfen. Sie bieten automatisierte Build-und releasephasen, um konsistenten und qualitativ hochwertigen Code sicherzustellen Aber das ist nur ein Teil der Story. Wie stellen Sie die cloudumgebungen bereit, auf denen diese Systeme ausgeführt werden?

Moderne Native Cloud-Anwendungen nutzen die weit verbreitete [Infrastruktur als Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)oder `IaC` .  Mit IAC automatisieren Sie die Platt Form Bereitstellung. Sie wenden im Wesentlichen Software Entwicklungsverfahren wie Tests und Versionsverwaltung auf Ihre devops-Verfahren an. Ihre Infrastruktur und bereit Stellungen sind automatisiert, konsistent und wiederholbar. Ebenso wie Continuous Delivery das herkömmliche Modell manueller bereit Stellungen automatisiert, wird Infrastructure as Code (IAC) weiterentwickelt, wie Anwendungsumgebungen verwaltet werden.

Tools wie Azure Resource Manager (Arm), TERRAFORM und die Azure-Befehlszeilenschnittstelle (CLI) ermöglichen Ihnen die deklarative Skripterstellung für die erforderliche cloudinfrastruktur.

## <a name="azure-resource-manager-templates"></a>Azure-Ressourcen-Manager-Vorlagen

Arm steht für [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/). Dabei handelt es sich um eine API-Bereitstellungs-Engine, die in Azure integriert ist und als API-Dienst verfügbar gemacht wird. Mit Arm können Sie die in der Azure-Ressourcengruppe enthaltenen Ressourcen in einem einzigen, koordinierten Vorgang bereitstellen, aktualisieren, löschen und verwalten. Sie stellen der Engine eine JSON-basierte Vorlage bereit, die die benötigten Ressourcen und deren Konfiguration angibt. Arm orchestriert die Bereitstellung automatisch in der richtigen Reihenfolge, in der Abhängigkeiten berücksichtigt werden. Die Engine stellt Idempotenz sicher. Wenn eine gewünschte Ressource bereits mit derselben Konfiguration vorhanden ist, wird die Bereitstellung ignoriert.

Azure Resource Manager Vorlagen sind eine JSON-basierte Sprache zum Definieren verschiedener Ressourcen in Azure. Das grundlegende Schema sieht in etwa wie in Abbildung 10-14 aus.

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

**Abbildung 10-14** : das Schema für eine Ressourcen-Manager Vorlage

Innerhalb dieser Vorlage kann ein Speicher Container im Ressourcenabschnitt wie folgt definiert werden:

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

**Abbildung 10-15** : ein Beispiel für ein Speicherkonto, das in einer Ressourcen-Manager Vorlage definiert ist

Eine Arm-Vorlage kann mit dynamischen Umgebungs-und Konfigurationsinformationen parametrisiert werden. Dadurch kann die Anwendung wieder verwendet werden, um unterschiedliche Umgebungen zu definieren, wie z. b. Entwicklung, QA oder Produktion. Normalerweise werden von der Vorlage alle Ressourcen innerhalb einer einzelnen Azure-Ressourcengruppe erstellt. Es ist möglich, bei Bedarf mehrere Ressourcengruppen in einer einzigen Ressourcen-Manager Vorlage zu definieren. Sie können alle Ressourcen in einer Umgebung löschen, indem Sie die Ressourcengruppe selbst löschen. Die Kostenanalyse kann auch auf Ressourcengruppen Ebene ausgeführt werden und ermöglicht eine schnelle Erfassung der Kosten für jede Umgebung.

Im [Azure-Schnellstart Vorlagen](https://github.com/Azure/azure-quickstart-templates) -Projekt auf GitHub stehen zahlreiche Beispiele oder arm-Vorlagen zur Verfügung. Sie können dabei helfen, die Erstellung einer neuen Vorlage zu beschleunigen oder eine vorhandene zu ändern.

Ressourcen-Manager Vorlagen können auf viele Arten ausgeführt werden. Die einfachste Möglichkeit besteht darin, Sie einfach in den Azure-Portal einzufügen. Bei experimentellen bereit Stellungen kann diese Methode schnell sein. Sie können auch als Teil eines Build-oder Releaseprozesses in Azure devops ausgeführt werden. Es gibt Aufgaben, die Verbindungen mit Azure zum Ausführen der Vorlagen nutzen. Änderungen an Ressourcen-Manager Vorlagen werden inkrementell angewendet, was bedeutet, dass zum Hinzufügen einer neuen Ressource diese lediglich der Vorlage hinzugefügt werden muss. Die Tools Stimmen die Unterschiede zwischen den aktuellen Ressourcen und den in der Vorlage definierten Ressourcen ab. Anschließend werden Ressourcen erstellt oder geändert, sodass Sie mit den in der Vorlage definierten Vorlagen verglichen werden.  

## <a name="terraform"></a>Terraform

Native Cloud-Anwendungen werden häufig als konstruiert `cloud agnostic` . Dies bedeutet, dass die Anwendung nicht eng mit einem bestimmten cloudanbieter verknüpft ist und in jedem Public Cloud bereitgestellt werden kann.

[TERRAFORM](https://www.terraform.io/) ist ein kommerzielles Vorlagen Tool, das in der Cloud native Anwendungen für alle wichtigen cloudplayer bereitstellen kann: Azure, Google Cloud Platform, AWS und alicloud. Anstatt JSON als Vorlagen Definitions Sprache zu verwenden, wird die etwas genauere YAML verwendet.

Eine TERRAFORM-Beispieldatei, die die gleiche wie die vorherige Ressourcen-Manager Vorlage (Abbildung 10-15) verwendet, ist in Abbildung 10-16 dargestellt:

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

**Abbildung 10-16** : ein Beispiel für eine Ressourcen-Manager Vorlage

TERRAFORM bietet auch intuitive Fehlermeldungen für problemvorlagen. Es gibt auch eine praktische Validate-Aufgabe, die in der Buildphase zum frühen erfassen von Vorlagen Fehlern verwendet werden kann.

Wie bei Ressourcen-Manager Vorlagen sind Befehlszeilen Tools zum Bereitstellen von TERRAFORM-Vorlagen verfügbar. Es gibt auch von der Community erstellte Aufgaben in Azure Pipelines, die TERRAFORM-Vorlagen validieren und anwenden können.

Manchmal geben TERRAFORM-und Arm-Vorlagen sinnvolle Werte aus, z. b. eine Verbindungs Zeichenfolge für eine neu erstellte Datenbank. Diese Informationen können in der Buildpipeline aufgezeichnet und in nachfolgenden Aufgaben verwendet werden.

## <a name="azure-cli-scripts-and-tasks"></a>Skripts und Aufgaben Azure CLI

Zum Schluss können Sie [Azure CLI](https://docs.microsoft.com/cli/azure/) für die deklarative Skripterstellung für Ihre cloudinfrastruktur nutzen. Azure CLI Skripts können erstellt, gefunden und freigegeben werden, um nahezu jede Azure-Ressource bereitzustellen und zu konfigurieren. Die CLI ist einfach zu verwenden, und zwar mit einer sanften Lernkurve. Skripts werden entweder in PowerShell oder in bash ausgeführt. Sie sind auch unkompliziert zu debuggen, besonders im Vergleich zu arm-Vorlagen.

Azure CLI Skripts funktionieren gut, wenn Sie Ihre Infrastruktur abbrechen und erneut bereitstellen müssen. Das Aktualisieren einer vorhandenen Umgebung kann knifflig sein. Viele CLI-Befehle sind nicht idempotent. Dies bedeutet, dass Sie die Ressource jedes Mal neu erstellen, wenn Sie ausgeführt wird, auch wenn die Ressource bereits vorhanden ist. Es ist immer möglich, Code hinzuzufügen, der überprüft, ob jede Ressource vorhanden ist, bevor Sie erstellt wird. Allerdings kann Ihr Skript mit einem blobverhalten und schwer zu verwalten werden.

Diese Skripts können auch in Azure devops-Pipelines als eingebettet werden `Azure CLI tasks` . Beim Ausführen der Pipeline wird das Skript aufgerufen.

In Abbildung 10-17 wird ein YAML-Code Ausschnitt gezeigt, der die Version von Azure CLI und die Details des Abonnements auflistet. Beachten Sie, wie Azure CLI Befehle in ein Inline Skript eingefügt werden.

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

**Abbildung 10-17** -Azure CLI Skript

Im Artikel [Was ist Infrastructure as Code, wird](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)der Autor Sam Guckenheimer beschrieben, wie "Teams, die IAC implementieren, schnelle und skalierbare Umgebungen bereitstellt. Teams vermeiden die manuelle Konfiguration von Umgebungen und erzwingen Konsistenz, indem Sie den gewünschten Zustand ihrer Umgebungen über Code darstellen. Infrastruktur Bereitstellungen mit IAC sind wiederholbar und verhindern Lauf Zeit Probleme, die durch Konfigurations Abweichung oder fehlende Abhängigkeiten verursacht werden. Devops-Teams können mit einem einheitlichen Satz von Methoden und Tools zusammenarbeiten, um Anwendungen und deren unterstützende Infrastruktur schnell, zuverlässig und skalierbar bereitzustellen. "

>[!div class="step-by-step"]
>[Zurück](feature-flags.md)
>[Weiter](application-bundles.md)
