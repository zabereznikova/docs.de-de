---
title: Docker-Container, -Images und -Registrierungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9de37f9ee3a8fe7ce4a337fc548030b2aeadba55
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="docker-containers-images-and-registries"></a>Docker-Container, -Images und -Registrierungen

Wenn Sie Docker verwenden zu können, erstellen Sie eine app oder den Dienst und die Paket sie und ihre Abhängigkeiten in einem containerimage. Ein Image entspricht einer statischen Darstellung der Apps oder Dienste und von deren Konfigurationen und Abhängigkeiten.

Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert. Container werden zunächst in einer Entwicklungsumgebung oder auf einem PC getestet.

Durch das Speichern von Bildern in eine Registrierung, die als eine Bibliothek mit Images fungiert. Sie benötigen eine Registrierung bei der Bereitstellung für die Produktion Orchestrators. Docker verwaltet eine öffentliche Registrierung über den [Docker-Hub](https://hub.docker.com/). Andere Anbieter stellen Registrierungen für verschiedene Imagesammlungen bereit. Alternativ können Unternehmen eine private lokale Registrierung für eigene Docker-Images einrichten.

Abbildung 1 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen. Die Angebote verschiedener Anbieter für Registrierungen werden ebenfalls dargestellt.

![](./media/image4.png)

Abbildung 1 – 4: Taxonomie Docker-Begriffe und Konzepte

Verlegen Sie Bilder in einer Registrierung verwenden, können Sie statische und unveränderlichen Anwendungskomponenten, einschließlich aller zugehörigen Abhängigkeiten an, auf einer Frameworkebene speichern. Sie können verschiedene Versionen und Bereitstellen von Images in mehreren Umgebungen und und bieten so eine konsistente Bereitstellungseinheit.

Privates Image-Registrierungen, entweder lokal gehostet oder in der Cloud für den folgenden Situationen empfohlen:

-   Ihre Images wegen Vertraulichkeit nicht öffentlich freigegeben werden dürfen

-   Sie eine minimale Netzwerklatenz zwischen Ihren Images und der ausgewählten Bereitstellungsumgebung erzielen möchten Wenn Ihre produktionsumgebung Azure ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist. Ähnliches gilt, wenn Ihre Produktionsumgebung lokal ist: Dann Sie möchten vermutlich sicherstellen, dass ein lokaler Docker Trusted Registry-Dienst innerhalb desselben lokalen Netzwerks verfügbar ist.

>[!div class="step-by-step"]
[Vorherigen] (Docker-terminology.md) [weiter] (Docker-Anwendung-Lebenszyklus/index.md)
