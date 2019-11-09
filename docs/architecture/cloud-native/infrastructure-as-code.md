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
# <a name="infrastructure-as-code"></a>Infrastruktur als Code

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Native Cloud-Anwendungen nutzen tendenziell alle Arten von fantastischen Platform-as-a-Service-Komponenten (Platform-as-a-Service, PAS). In einer cloudplattform wie Azure können diese Komponenten z. b. Speicher, Service Bus und den signalr-Dienst umfassen. Wenn Anwendungen komplizierter werden, wird die Anzahl der verwendeten Dienste wahrscheinlich vergrößert. Ebenso wie Continuous Delivery das herkömmliche Modell der Bereitstellung in einer Umgebung manuell unterbrochen hat, brach die schnelle Geschwindigkeit der Änderung auch das Modell einer zentralisierten IT-Gruppe zur Verwaltung von IT-Umgebungen.

Das aufbauen von Umgebungen kann auch automatisiert werden. Es gibt eine Vielzahl von bewährten Tools, die den Prozess vereinfachen können.

## <a name="azure-resource-manager-templates"></a>Azure Resource Manager Vorlagen

Azure Resource Manager Vorlagen sind eine JSON-basierte Sprache zum Definieren verschiedener Ressourcen in Azure. Das grundlegende Schema sieht in etwa wie in Abbildung 11-10 aus.

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

**Abbildung 11-10** : das Schema für eine Ressourcen-Manager Vorlage

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

**Abbildung 11-11** : ein Beispiel für ein Speicherkonto, das in einer Ressourcen-Manager Vorlage definiert ist

Die Vorlagen können parametrisiert werden, damit eine Vorlage mit unterschiedlichen Einstellungen wieder verwendet werden kann, um Entwicklungs-, QA-und Produktionsumgebungen zu definieren. Dadurch lassen sich Überraschungen bei der Migration zu einer höheren Umgebung vermeiden, die in den niedrigeren Umgebungen anders eingerichtet ist. Die Ressourcen, die in einer Vorlage definiert sind, werden in der Regel in einer einzelnen Ressourcengruppe in Azure erstellt (es ist möglich, mehrere Ressourcengruppen in einer einzigen Ressourcen-Manager Vorlage zu definieren, aber ungewöhnliche). Dadurch ist es sehr einfach, eine Umgebung zu löschen, indem einfach die Ressourcengruppe als Ganzes gelöscht wird. Die Kostenanalyse kann auch auf Ressourcengruppen Ebene ausgeführt werden und ermöglicht eine schnelle Erfassung der Kosten für jede Umgebung.

Es gibt zahlreiche Beispiel Vorlagen, die im [Azure-Schnellstart Vorlagen](https://github.com/Azure/azure-quickstart-templates) -Projekt auf GitHub definiert sind und beim Starten mit einer neuen Vorlage oder beim Hinzufügen zu einer vorhandenen Vorlage eine Reihe von Informationen erhalten.

Ressourcen-Manager Vorlagen können auf unterschiedlichste Weise ausgeführt werden. Die einfachste Möglichkeit besteht darin, Sie einfach in den Azure-Portal einzufügen. Bei experimentellen bereit Stellungen kann diese Methode sehr schnell sein. Sie können auch als Teil eines Build-oder Releaseprozesses in Azure devops ausgeführt werden. Es gibt Aufgaben, die Verbindungen mit Azure zum Ausführen der Vorlagen nutzen. Änderungen an Ressourcen-Manager Vorlagen werden inkrementell angewendet, was bedeutet, dass zum Hinzufügen einer neuen Ressource diese lediglich der Vorlage hinzugefügt werden muss. Das Tool verarbeitet das Vergleich der aktuellen Ressourcengruppe mit der gewünschten Ressourcengruppe, die in der Vorlage definiert ist. Anschließend werden Ressourcen erstellt oder geändert, sodass Sie mit den in der Vorlage definierten Vorlagen verglichen werden.  

## <a name="terraform"></a>TERRAFORM

Ein wahrgenommener Nachteil von Ressourcen-Manager Vorlagen ist, dass Sie für die Azure-Cloud spezifisch sind. Es ist ungewöhnlich, Anwendungen zu erstellen, die Ressourcen aus mehr als einer Cloud enthalten. in Fällen, in denen das Unternehmen auf eine spektakuläre Betriebszeit basiert, sind die Kosten für die Unterstützung mehrerer Clouds möglicherweise lohnenswert. Wenn eine Vorlagen Sprache vorhanden war, die in jeder Cloud verwendet werden konnte, wäre es auch möglich, dass Entwickler Kenntnisse viel besser portierbar sind.

Es gibt mehrere Technologien, die genau das tun. Das ausgereifte Angebot in diesem Bereich wird als [TERRAFORM](https://www.terraform.io/)bezeichnet. TERRAFORM unterstützt jeden großen Cloud-Player, wie z. b. Azure, Google Cloud Platform, AWS und alicloud, und unterstützt auch Dutzende von neben Akteuren, wie z. b. heroku und digitalozean. Anstatt JSON als Vorlagen Definitions Sprache zu verwenden, wird die etwas genauere YAML verwendet.

Eine TERRAFORM-Beispieldatei, die die gleiche wie die vorherige Ressourcen-Manager Vorlage (Abbildung 11-11) verwendet, ist in Abbildung 11-12 dargestellt:

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

**Abbildung 11-12** : ein Beispiel für eine Ressourcen-Manager Vorlage

TERRAFORM bietet eine bessere Möglichkeit, sinnvolle Fehlermeldungen bereitzustellen, wenn eine Ressource aufgrund eines Fehlers in der Vorlage nicht bereitgestellt werden kann. Dies ist ein Bereich, in dem Ressourcen-Manager Vorlagen einige fortlaufende Herausforderungen haben. Es gibt auch eine sehr praktische Validate-Aufgabe, die in der Buildphase zum frühen erfassen von Vorlagen Fehlern verwendet werden kann.

Wie bei Ressourcen-Manager Vorlagen gibt es Befehlszeilen Tools, die zum Bereitstellen von TERRAFORM-Vorlagen verwendet werden können. Es gibt auch von der Community erstellte Aufgaben in Azure Pipelines, die TERRAFORM-Vorlagen validieren und anwenden können.

Wenn die TERRAFORM-oder Ressourcen-Manager Vorlage interessante Werte (z. b. die Verbindungs Zeichenfolge) für eine neu erstellte Datenbank ausgibt, können Sie in der Buildpipeline aufgezeichnet und in nachfolgenden Aufgaben verwendet werden.

>[!div class="step-by-step"]
>[Zurück](devops.md)
>[Weiter](application-bundles.md)
