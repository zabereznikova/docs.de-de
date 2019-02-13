---
title: Docker-Container, -Images und -Registrierungen
description: Erfahren Sie, die wichtige Rolle, dass Registrierungen wie Docker Bereitstellung von Anwendungen allgemeine spielen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 7a2e20e09561a5cc91aa29059fb8d19a14205bb5
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221198"
---
# <a name="docker-containers-images-and-registries"></a>Docker-Container, -Images und -Registrierungen

Mithilfe von Docker erstellen Sie eine app oder -Dienst und -Paket, diese und ihre Abhängigkeiten in einem containerimage. Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.

Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird. Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.

Speichern Sie Bilder in einer Registrierung, fungiert als eine Bibliothek mit Images. Sie benötigen eine Registrierung bei der Bereitstellung für produktionsorchestratoren. Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit. Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.

Abbildung 1 – 4 zeigt, wie Images und Registrierungen in Docker andere Komponenten in Beziehung stehen. Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.

![](./media/image4.png)

Abbildung 1 – 4: Taxonomie der Docker-Begriffe und -Konzepte

Durch das Einfügen von Images in einer Registrierung, können Sie statische und unveränderliche anwendungsbereitstellung, einschließlich aller ihrer Abhängigkeiten auf Frameworkebene speichern. Sie können verschiedene Versionen und Images in mehreren Umgebungen bereitstellen und dadurch eine konsistente Bereitstellungseinheit bereitstellen.

Private imageregistrierungen, entweder lokal gehostet oder in der Cloud, werden für den folgenden Situationen empfohlen:

-   Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen

-   Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten Beispielsweise wenn Ihre produktionsumgebung Azure ist, sollten Sie die Images in Azure Container Registry speichern, sodass Netzwerklatenz minimal ist. Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.

>[!div class="step-by-step"]
>[Zurück](docker-terminology.md)
>[Weiter](road-to-modern-applications-based-on-containers.md)
