---
title: Docker-Container, -Images und -Registrierungen
description: Lernen Sie die Schlüsselrolle kennen, die Registrierungen überall in der Docker-Methode zum Bereitstellen von Anwendungen spielen.
ms.date: 02/15/2019
ms.openlocfilehash: bfef21cab7be89abaf33b89366d7cff2115a7cc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72770931"
---
# <a name="docker-containers-images-and-registries"></a>Docker-Container, -Images und -Registrierungen

Bei der Verwendung von Docker erstellen Sie eine App oder einen Dienst und verpacken sie bzw. ihn zusammen mit den jeweiligen Abhängigkeiten in einem Containerimage. Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.

Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird. Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.

Sie speichern Images in einer Registrierung, die als Katalog für Images fungiert. Sie benötigen eine Registrierung für das Bereitstellen an Produktionsorchestratoren. Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit, einschließlich der [Azure Container Registry](https://azure.microsoft.com/services/container-registry/). Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.

In Abbildung 1–4 wird dargestellt, wie Images und Registrierungen in Docker mit anderen Komponenten in Beziehung stehen. Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.

![Abbildung, die die grundlegende Taxonomie in Docker zeigt.](./media/docker-containers-images-and-registries/taxonomy-docker-terms-concepts.png)

**Abbildung 1-4.** Taxonomie der Docker-Begriffe und -Konzepte

Die Registrierung funktioniert wie ein Bücherregal, in dem Images gespeichert und für den Abruf zum Erstellen von Containern verfügbar sind, in denen Dienste oder Web-Apps ausgeführt werden. Private Docker-Registrierungen gibt es lokal und in der öffentlichen Cloud. Docker Hub ist eine öffentliche Registrierung, die von Docker betrieben wird, die Docker Trusted Registry ist eine für Unternehmen geeignete Lösung, und Azure bietet die Azure Container Registry an. AWS, Google und andere verfügen ebenfalls über Containerregistrierungen.

Durch das Einfügen von Images in eine Registrierung können Sie statische und unveränderliche Komponenten der Anwendung speichern, einschließlich aller Abhängigkeiten auf Frameworkebene. Diese Images können dann mit einer Versionsangabe versehen und in mehreren Umgebungen bereitgestellt werden. Dadurch steht eine konsistente Bereitstellungseinheit zur Verfügung.

Private Imageregistrierungen, die lokal oder in der Cloud gehostet werden, werden empfohlen, wenn:

- Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen

- Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten Wenn Ihre Produktionsumgebung beispielsweise Azure ist, möchten Sie Ihre Images wahrscheinlich in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) speichern, um eine minimale Netzwerklatenz zu erzielen. Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.

>[!div class="step-by-step"]
>[Zurück](docker-terminology.md)
>[Weiter](road-to-modern-applications-based-on-containers.md)
