---
title: Docker-Container, -Images und -Registrierungen
description: Erfahren Sie, die wichtige Rolle, dass Registrierungen wie Docker Bereitstellung von Anwendungen allgemeine spielen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583315"
---
# <a name="docker-containers-images-and-registries"></a>Docker-Container, -Images und -Registrierungen

Mithilfe von Docker erstellen Sie eine app oder -Dienst und -Paket, diese und ihre Abhängigkeiten in einem containerimage. Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.

Für die Ausführung einer App oder eines Diensts wird das Image der App oder des Diensts instanziiert, um einen Container zu erstellen, der auf dem Docker-Host ausgeführt wird. Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.

Speichern Sie Bilder in einer Registrierung, die als eine Bibliothek mit Images fungiert. Sie benötigen eine Registrierung bei der Bereitstellung für produktionsorchestratoren. Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit, einschließlich der [Azure Container Registry](https://azure.microsoft.com/services/container-registry/). Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.

Abbildung 1 – 4 zeigt, wie Images und Registrierungen in Docker andere Komponenten in Beziehung stehen. Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.

![Grundlegende Taxonomie in Docker: Die Registrierung ist wie eine virtuelle Bibliothek, in denen Bilder sind, gespeichert und abgerufen werden, für das Erstellen von Containern, um Dienste oder Web-apps ausführen. Es sind private Docker-Registrierungen auf lokale und in der öffentlichen Cloud. Docker Hub ist eine öffentliche Registrierung, die von Docker betrieben wird, die Docker Trusted Registry ist eine für Unternehmen geeignete Lösung, und Azure bietet die Azure Container Registry an. AWS, Google und andere verfügen ebenfalls über Containerregistrierungen.](./media/image4.png)

**Abbildung 1-4.** Taxonomie der Docker-Begriffe und -Konzepte

Durch das Einfügen von Images in einer Registrierung, können Sie statische und unveränderliche anwendungsbereitstellung, einschließlich aller ihrer Abhängigkeiten auf Frameworkebene speichern. Sie können verschiedene Versionen und Images in mehreren Umgebungen bereitstellen und dadurch eine konsistente Bereitstellungseinheit bereitstellen.

Private Imageregistrierungen, die lokal oder in der Cloud gehostet werden, werden empfohlen, wenn:

- Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen

- Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten Beispielsweise ist die produktionsumgebung auf Azure, wahrscheinlich Ihre Images speichern möchten [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so, dass die Netzwerklatenz minimal ist. Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.

>[!div class="step-by-step"]
>[Zurück](docker-terminology.md)
>[Weiter](road-to-modern-applications-based-on-containers.md)
