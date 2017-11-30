---
title: Docker-Containern, Bilder und Registrierungen
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b115b25d8ae335aafbe41bac0d694170be7e3c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker-Containern, Bilder und Registrierungen

Wenn Sie Docker verwenden zu können, erstellen Sie eine app oder den Dienst und die Paket sie und ihre Abhängigkeiten in einem containerimage. Ein Image ist eine statische Darstellung der app oder Dienst, Konfiguration und seine Abhängigkeiten.

Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert. Container werden zunächst in einer Entwicklungsumgebung oder PC getestet.

Durch das Speichern von Bildern in eine Registrierung, die als eine Bibliothek mit Images fungiert. Sie benötigen eine Registrierung bei der Bereitstellung für die Produktion Orchestrators. Docker verwaltet eine öffentliche Registrierung über [Docker Hub](https://hub.docker.com/); andere Anbieter stellen Registrierungen für verschiedene Sammlungen von Bildern. Alternativ können Unternehmen haben eine private Registrierung on-Premises für ihre eigenen Docker-Images.

Abbildung 1 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen. Es zeigt auch die mehrere Registrierung Angebote von anderen Anbietern.

![](./media/image4.png)

Abbildung 1 – 4: Taxonomie Docker-Begriffe und Konzepte

Verlegen Sie Bilder in einer Registrierung verwenden, können Sie statische und unveränderlichen Anwendungskomponenten, einschließlich aller zugehörigen Abhängigkeiten an, auf einer Frameworkebene speichern. Sie können verschiedene Versionen und Bereitstellen von Images in mehreren Umgebungen und und bieten so eine konsistente Bereitstellungseinheit.

Privates Image-Registrierungen, entweder lokal gehostet oder in der Cloud für den folgenden Situationen empfohlen:

-   Die Bilder müssen aufgrund der Vertraulichkeit nicht öffentlich freigegeben werden.

-   Möchten Sie die minimale Netzwerklatenz zwischen der Bilder und der ausgewählten bereitstellungsumgebung haben. Wenn Ihre produktionsumgebung Azure ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist. Auf ähnliche Weise Wenn Ihre produktionsumgebung lokal ist sollten Sie ein lokaler Docker Trusted Registry innerhalb der gleichen lokalen Netzwerk zur Verfügung zu haben.

>[!div class="step-by-step"]
[Vorherigen] (Docker-terminology.md) [weiter] (Docker-Anwendung-Lebenszyklus/index.md)
