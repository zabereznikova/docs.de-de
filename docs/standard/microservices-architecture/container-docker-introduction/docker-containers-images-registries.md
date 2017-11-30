---
title: Docker-Containern, Bilder und Registrierungen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Docker-Containern, Bilder und Registrierungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker-Containern, Bilder und Registrierungen

Wenn Sie Docker verwenden zu können, erstellt ein Entwickler eine Anwendung oder Dienst und Pakete sie und ihre Abhängigkeiten in einem containerimage. Ein Image ist eine statische Darstellung der app oder Dienst, Konfiguration und seine Abhängigkeiten.

Um die app oder Ihrem Dienst ausführen, wird der app-Images zum Erstellen eines Containers, der auf dem Docker-Host ausgeführt werden, wird instanziiert. Container werden zunächst in einer Entwicklungsumgebung oder PC getestet.

Entwickler sollten Bilder in einer Registrierung speichern die fungiert als eine Bibliothek mit Images und ist erforderlich, wenn für die Produktion Orchestrators bereitstellen. Docker verwaltet eine öffentliche Registrierung über [Docker Hub](https://hub.docker.com/); andere Anbieter stellen Registrierungen für verschiedene Sammlungen von Bildern. Alternativ können Unternehmen haben eine private Registrierung on-Premises für ihre eigenen Docker-Images.

Abbildung 2 – 4 zeigt, wie Bilder und Registrierungen in Docker an andere Komponenten in Beziehung stehen. Es zeigt auch die mehrere Registrierung Angebote von anderen Anbietern.

![](./media/image5.PNG)

**Abbildung 2 – 4**. Taxonomie Docker-Begriffe und Konzepte

Einfügen von Bildern in einer Registrierung ermöglicht das Speichern von statischen und unveränderlichen Anwendungskomponenten, z. B. alle ihre Abhängigkeiten auf einer Frameworkebene. Diese Bilder können mit Versionsangabe und in mehreren Umgebungen bereitgestellt werden und bieten daher eine konsistente Bereitstellungseinheit.

Privates Image-Registrierungen entweder gehostet lokal oder in der Cloud werden empfohlen, wenn:

-   Die Bilder müssen aufgrund der Vertraulichkeit nicht öffentlich freigegeben werden.

-   Möchten Sie die minimale Netzwerklatenz zwischen der Bilder und der ausgewählten bereitstellungsumgebung haben. Wenn Ihre produktionsumgebung Azure-Cloud ist, z. B. Sie wahrscheinlich die Images in Azure-Container-Registrierung zu speichern, sodass Netzwerklatenz minimal ist. Auf ähnliche Weise Wenn Ihre produktionsumgebung lokal ist sollten Sie ein lokaler Docker Trusted Registry innerhalb der gleichen lokalen Netzwerk zur Verfügung zu haben.

>[!div class="step-by-step"]
[Vorherigen] (Docker-terminology.md) [weiter] (.. /NET-Core-NET-Framework-Containers/Index.MD)
