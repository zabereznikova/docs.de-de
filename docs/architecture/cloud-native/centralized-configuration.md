---
title: Zentralisierte Konfiguration
description: Zentralisieren der Konfiguration für Native Cloud-Anwendungen mit Azure-App-Konfiguration und azurekey Vault.
ms.date: 05/13/2020
ms.openlocfilehash: d389d29dcdb1db5162d95370d181ab5a85d72dc8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614226"
---
# <a name="centralized-configuration"></a>Zentralisierte Konfiguration

Anders als bei einer monolithischen APP, in der alles innerhalb einer einzelnen Instanz ausgeführt wird, besteht eine native Cloud-Anwendung aus unabhängigen Diensten, die auf virtuelle Computer, Container und geografische Regionen verteilt sind. Das Verwalten von Konfigurationseinstellungen für Dutzende voneinander abhängiger Dienste kann eine Herausforderung darstellen. Doppelte Kopien von Konfigurationseinstellungen über verschiedene Speicherorte hinweg sind fehleranfällig und schwer zu verwalten. Die zentralisierte Konfiguration ist eine wichtige Voraussetzung für verteilte cloudbasierte Anwendungen.

Wie in [Kapitel 1](introduction.md)erläutert, ist für die Empfehlungen der 12-stufigen App eine strikte Trennung zwischen Code und Konfiguration erforderlich. Die Konfiguration muss extern von der Anwendung gespeichert und bei Bedarf eingelesen werden. Das Speichern von Konfigurations Werten als Konstanten oder Literalwerte im Code stellt einen Verstoß dar. Die gleichen Konfigurationswerte werden häufig von vielen Diensten in derselben Anwendung verwendet. Außerdem müssen wir dieselben Werte in mehreren Umgebungen unterstützen, z. b. dev, Testing und Production. Die bewährte Vorgehensweise besteht darin, Sie in einem zentralisierten Konfigurations Speicher zu speichern.

Die Azure-Cloud bietet einige hervorragend Optionen.

## <a name="azure-app-configuration"></a>Azure App Configuration

[Azure-App Konfiguration](https://docs.microsoft.com/azure/azure-app-configuration/overview) ist ein vollständig verwalteter Azure-Dienst, der nicht geheime Konfigurationseinstellungen an einem sicheren, zentralisierten Speicherort speichert. Gespeicherte Werte können von mehreren Diensten und Anwendungen gemeinsam genutzt werden.

Der Dienst ist einfach zu verwenden und bietet mehrere Vorteile:

- Flexible Schlüssel-Wert-Darstellungen und Zuordnungen
- Tagging mit Azure-Bezeichnungen
- Dedizierte Benutzeroberfläche für die Verwaltung
- Verschlüsselung vertraulicher Informationen
- Abfragen und Batch Abruf

Bei der Azure-App Konfiguration werden die Änderungen an den Schlüsselwert Einstellungen sieben Tage lang beibehalten. Mit dem Feature für die Point-in-Time-Momentaufnahme können Sie den Verlauf einer Einstellung und sogar Rollbacks für eine fehlgeschlagene Bereitstellung rekonstruieren.

Bei der APP-Konfiguration werden automatisch alle Einstellungen zwischengespeichert, um übermäßige Aufrufe des Konfigurations Speichers zu vermeiden. Beim Aktualisierungsvorgang wird abgewartet, bis der zwischengespeicherte Wert einer Einstellung abgelaufen ist, bevor die Einstellung aktualisiert wird. Dies gilt auch, wenn sich der zugehörige Wert im Konfigurationsspeicher ändert. Die Standarddauer für den Ablauf des Caches beträgt 30 Sekunden. Sie können die Ablaufzeit außer Kraft setzen.

In der APP-Konfiguration werden alle Konfigurationswerte während der Übertragung und im Ruhezustand verschlüsselt. Schlüsselnamen und Bezeichnungen werden als Indizes zum Abrufen von Konfigurationsdaten verwendet und sind nicht verschlüsselt.

Obwohl die APP-Konfiguration Sicherheits-und Sicherheits Sicherheit bietet, ist Azure Key Vault immer noch der beste Ort zum Speichern von Anwendungs Geheimnissen Key Vault bietet Verschlüsselung auf Hardwareebene, differenzierte Zugriffsrichtlinien und Verwaltungsvorgänge, wie z. b. die Zertifikats Rotation. Sie können APP-Konfigurationswerte erstellen, die auf in einem Key Vault gespeicherte Geheimnisse verweisen.

## <a name="azure-key-vault"></a>Azure-Schlüsseltresor

Key Vault ist ein verwalteter Dienst für die sichere Speicherung und den Zugriff auf Geheimnisse. Als Geheimnis wird alles bezeichnet, für das Sie den Zugriff streng kontrollieren möchten, z.B. API-Schlüssel, Kennwörter oder Zertifikate. Ein Tresor ist eine logische Gruppe von Geheimnissen.

Mit Key Vault lässt sich das Risiko einer unbeabsichtigten Weitergabe von Geheimnissen erheblich senken. Dank Key Vault müssen Anwendungsentwickler Sicherheitsinformationen nicht mehr in der Anwendung speichern. Diese Vorgehensweise entfällt, dass diese Informationen in Ihrem Code gespeichert werden müssen. Ein Beispiel: Angenommen, eine Anwendung muss eine Verbindung mit einer Datenbank herstellen. Anstatt die Verbindungszeichenfolge im App-Code zu speichern, können Sie diese sicher in Key Vault speichern.

Ihre Anwendungen können mithilfe von URIs sicher auf benötigte Informationen zugreifen. Diese URIs bieten den Anwendungen die Möglichkeit, bestimmte Versionen eines geheimen Schlüssels abzurufen. Es ist nicht erforderlich, benutzerdefinierten Code zu schreiben, um die in Key Vault gespeicherten geheimen Informationen zu schützen.

Der Zugriff auf Key Vault erfordert ordnungsgemäße Aufrufer Authentifizierung und Autorisierung. In der Regel verwendet jeder Cloud-Native-Dienst eine ClientID-/clientgeheim-Kombination. Es ist wichtig, diese Anmelde Informationen außerhalb der Quell Code Verwaltung zu speichern. Eine bewährte Vorgehensweise besteht darin, Sie in der Umgebung der Anwendung festzulegen. Der direkte Zugriff auf Key Vault von AKS kann mithilfe von [Key Vault flexvolume](https://github.com/Azure/kubernetes-keyvault-flexvol)erreicht werden.

## <a name="configuration-in-eshop"></a>Konfiguration im eShop

Die eshoponcontainers-Anwendung enthält lokale Anwendungseinstellungs-Dateien mit jedem-mikrodienst. Diese Dateien werden in die Quell Code Verwaltung eingecheckt, enthalten aber keine Produktionsgeheimnisse wie Verbindungs Zeichenfolgen oder API-Schlüssel. In der Produktionsumgebung können einzelne Einstellungen mit Umgebungsvariablen pro Dienst überschrieben werden. Das Einfügen von Geheimnissen in Umgebungsvariablen ist eine gängige Vorgehensweise bei gehosteten Anwendungen, bietet aber keinen zentralen Konfigurations Speicher. Zur Unterstützung der zentralisierten Verwaltung von Konfigurationseinstellungen enthält jeder-Dienst eine Einstellung zum Umschalten zwischen der Verwendung lokaler Einstellungen oder Azure Key Vault Einstellungen.

## <a name="references"></a>References

- [Die eshoponcontainers-Architektur](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Architecture)
- [Orchestrieren von Microservices und Anwendungen mit mehreren Containern für hohe Skalierbarkeit und Verfügbarkeit](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/scalable-available-multi-container-microservice-applications)
- [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-key-concepts)
- [Übersicht über Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)
- [Azure Cache for Redis](https://azure.microsoft.com/services/cache/)
- [MongoDB-API von Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Monitor – Übersicht](https://docs.microsoft.com/azure/azure-monitor/overview)
- [eshoponcontainers: Erstellen eines Kubernetes-Clusters in AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eshoponcontainers: Azure dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Zurück](deploy-eshoponcontainers-azure.md)
>[Weiter](scale-applications.md)
