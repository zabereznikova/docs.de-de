---
title: Weitere Optionen für die Container Bereitstellung
description: Weitere Bereitstellungs Optionen für Container mithilfe von Azure
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841162"
---
# <a name="other-container-deployment-options"></a>Weitere Optionen für die Container Bereitstellung

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Zusätzlich zur Bereitstellung in AKS können Sie Container auch zum Azure App Service für Container und Azure Container Instances bereitstellen.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>Wann ist es sinnvoll, App Service für Container bereitzustellen?

Einfache Produktionsanwendungen, für die keine Orchestrierung erforderlich ist, eignen sich gut für die Azure App Service von Containern.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Bereitstellen in App Service für Container

Zum Bereitstellen von für [Azure App Service für Container](https://azure.microsoft.com/services/app-service/containers/)müssen Sie einen Azure Container Registry (ACR) und Anmelde Informationen für den Zugriff konfiguriert haben. Übersetzen Sie den Container, den Sie hosten möchten, in die Registrierung, damit er in ihren Azure App Service abgerufen werden kann. Nach der Erstellung können Sie die APP für die kontinuierliche Bereitstellung konfigurieren, die automatisch Updates für die APP bereitstellt, wenn Sie das entsprechende Image in ACR aktualisieren.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Wann ist es sinnvoll, für Azure Container Instances bereitzustellen?

Azure Container Instances werden am besten für Testszenarien verwendet. Sie bieten eine schnelle und einfache Möglichkeit, eine Anwendung für eine in der Cloud gehostete Container Instanz bereitzustellen. Verwenden Sie diese, um Anwendungen zu testen oder zu testen, wenn Sie keine Skalierungs-und Orchestrierungs Funktionen von Azure Kubernetes Service benötigen.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Bereitstellen einer APP für Azure Container Instances

Zum Bereitstellen auf [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)müssen Sie einen Azure Container Registry (ACR) und Anmelde Informationen für den Zugriff konfiguriert haben. Sie müssen das Container Image auch zuvor in die Registrierung übermittelt haben, damit es in ACI abgerufen werden kann. Sie können mit ACI arbeiten, indem Sie die Azure CLI oder über das Portal verwenden. Azure Container Registrierungen vereinfachen das direkte bereitstellen einzelner Container Instanzen in ACI in der Registrierung, wie in Abbildung 3-14 dargestellt.

![Azure Container Registry Lauf Instanz](./media/acr-runinstance-contextmenu.png)

**Abbildung 3-14**. Azure Container Registry Lauf Instanz

Wenn Sie eine Container Instanz aus der Registrierung erstellen, müssen Sie lediglich die üblichen Azure-Einstellungen (Name, Abonnement, Ressourcengruppe und Standort), den Arbeitsspeicher, der dem Container zuzuordnen ist, und den Port angeben, an dem die Überwachung durchführt werden soll. In dieser Schnellstartanleitung erfahren Sie [, wie Sie mithilfe der Azure-Portal eine Container Instanz in ACI](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)bereitstellen.

Nachdem die Bereitstellung abgeschlossen ist, suchen Sie die IP-Adresse des neu bereitgestellten Containers, und kommunizieren Sie über den Port, den Sie angegeben haben.

Azure Container Instances bietet die schnellste und einfachste Möglichkeit, einen Container in Azure auszuführen. Es ist nicht erforderlich, einen app Service oder einen Orchestrator zu konfigurieren oder virtuelle Computer zu bearbeiten. Aus Gründen der Einfachheit sollte ACI jedoch hauptsächlich zu Testzwecken verwendet werden. Wenn Ihre Anwendung eine automatische Skalierbarkeit, mehrere Container, die für die Zusammenarbeit konfiguriert sind, oder alle zusätzlichen komplexen Features erfordert, sind andere besser geeignete Azure-Dienste zum Hosten Ihrer app verfügbar.

## <a name="references"></a>Verweise

- [Azure Container Instances-Dokumentation](https://docs.microsoft.com/azure/container-instances/)
- [Bereitstellen einer Container Instanz über ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Zurück](scale-containers-serverless.md)
>[Weiter](communication-patterns.md)
