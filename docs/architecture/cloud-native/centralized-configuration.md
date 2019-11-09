---
title: Zentralisierte Konfiguration
description: Eine zentralisierte Konfiguration mithilfe von Azure Key Vault kann die Verwaltung von Cloud-Native apps vereinfachen.
ms.date: 06/30/2019
ms.openlocfilehash: 4c516b6773d913acd71ff06742302e9766a141e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841138"
---
# <a name="centralized-configuration"></a>Zentralisierte Konfiguration

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Native Cloud-Anwendungen umfassen viele weitere Dienste, als herkömmliche monolithische Single-Instance-Apps. Das Verwalten von Konfigurationseinstellungen für Dutzende voneinander abhängiger Dienste kann eine Herausforderung darstellen, weshalb zentralisierte Konfigurations Speicher häufig für verteilte Anwendungen implementiert werden.

Wie in [Kapitel 1](introduction.md)erläutert, ist für die Empfehlungen der 12-stufigen App eine strikte Trennung zwischen Code und Konfiguration erforderlich. Dies bedeutet, dass das Speichern von Konfigurationseinstellungen als Konstanten oder Literalwerte im Code eine Verletzung darstellt. Diese Empfehlung ist vorhanden, da derselbe Code in mehreren Umgebungen verwendet werden sollte, einschließlich Entwicklung, Tests, Staging und Produktion. Allerdings unterscheiden sich die Konfigurationswerte wahrscheinlich zwischen den einzelnen Umgebungen. Daher sollten Konfigurationswerte in der Umgebung selbst gespeichert werden, oder die Umgebung sollte die Anmelde Informationen in einem zentralisierten Konfigurations Speicher speichern.

Die eshoponcontainers-Anwendung enthält lokale Anwendungseinstellungs-Dateien mit jedem-mikrodienst. Diese Dateien werden in die Quell Code Verwaltung eingecheckt, enthalten aber keine Produktionsgeheimnisse wie Verbindungs Zeichenfolgen oder API-Schlüssel. In der Produktionsumgebung können einzelne Einstellungen mit Umgebungsvariablen pro Dienst überschrieben werden. Dies ist eine gängige Vorgehensweise bei gehosteten Anwendungen, bietet aber keinen zentralen Konfigurations Speicher. Zur Unterstützung der zentralisierten Verwaltung von Konfigurationseinstellungen enthält jeder-Dienst eine Einstellung zum Umschalten zwischen der Verwendung lokaler Einstellungen oder Azure Key Vault Einstellungen.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault bietet sichere Speicherung von Token, Kenn Wörtern, Zertifikaten, API-Schlüsseln und anderen vertraulichen Geheimnissen. Der Zugriff auf Key Vault erfordert ordnungsgemäße Aufrufer-Authentifizierung und-Autorisierung, was bei den eshoponcontainers-mikrodiensten die Verwendung einer ClientID/clientsecret-Kombination bedeutet. Checken Sie diese Anmelde Informationen nicht in die Quell Code Verwaltung ein, sondern stattdessen in der Anwendungsumgebung. Der direkte Zugriff auf Key Vault von AKS kann mithilfe von [Key Vault flexvolume](https://github.com/Azure/kubernetes-keyvault-flexvol)erreicht werden.

Bei der zentralisierten Konfiguration können Einstellungen, die für die gesamte Anwendung gelten (z. b. der zentrale Protokollierungs Endpunkt), einmalig festgelegt und von jedem Teil der verteilten Anwendung verwendet werden. Obwohl die-Dienste von den anderen unabhängig sein sollten, gibt es in der Regel weiterhin einige freigegebene Abhängigkeiten, deren Konfigurationsdetails von einem zentralisierten Konfigurations Speicher profitieren können.

>[!div class="step-by-step"]
>[Zurück](deploy-eshoponcontainers-azure.md)
>[Weiter](scale-applications.md)
