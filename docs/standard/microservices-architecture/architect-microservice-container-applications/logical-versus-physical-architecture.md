---
title: Logische Architektur im Vergleich zu physischen Architektur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Logische Architektur im Vergleich zu physischen Architektur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 635774a8fcd0cf1c0ede6a73c604071f538a37fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a>Logische Architektur im Vergleich zu physischen Architektur

Es empfiehlt sich zu diesem Zeitpunkt zu beenden und erläutert den Unterschied zwischen der logischen Architektur und physische Architektur und wie dies am Entwurf von Microservice-basierte Anwendungen gilt.

Um zu beginnen, erstellen Microservices erfordern die Verwendung einer bestimmten Technologie nicht. Docker-Containern sind z. B. nicht erforderlich, um ein Microservice-basierter Architektur zu erstellen. Diese Microservices kann auch als einfache Prozesse ausgeführt werden. Microservices ist eine logische Architektur.

Darüber hinaus auch dann, wenn ein Microservice physisch als Einzelgerät, Prozess oder Container implementiert werden kann (aus Gründen der Einfachheit, Ansatz in der ersten Version von ist [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), zwischen diesen Parität Business Microservice und physische oder Container nicht unbedingt in allen Fällen muss beim Erstellen einer großen und komplexen Anwendung besteht aus vielen Dutzende oder sogar Hunderte von Diensten.

Dies ist, wenn es ein Unterschied zwischen der logischen Architektur und physische Architektur einer Anwendungsverzeichnis ist. Die logische Architektur und den logischen Grenzen eines Systems zuordnen nicht unbedingt 1: 1-Architektur physischen Computer oder die Bereitstellung. Es kann vorkommen, aber dies häufig nicht der Fall.

Obwohl Sie bestimmte Business Microservices oder begrenzt, die den Kontext möglicherweise identifiziert, bedeutet dies nicht, dass die beste Möglichkeit zur Implementierung immer ist durch Erstellen eines einzelnen Diensts (z. B. einer ASP.NET Web-API) oder einzelne Docker-Container für jede Business Microservice. Müssen eine Regel besagt jedes Business Microservice muss mit einem einzigen Dienst implementiert werden, oder Container zu fest ist.

Aus diesem Grund eine Business Microservice oder begrenzt, die den Kontext ist eine logische Architektur, die (oder nicht) in der Regel möglicherweise mit der physischen Architektur. Der wichtige Punkt ist, dass eine Business Microservice oder begrenzt, die den Kontext muss autonome Code und unabhängig Versionsangaben werden bereitgestellt, als auch skaliert.

Wie in Abbildung 4 – 8 gezeigt, kann der Katalog Business Microservice aus mehrere Dienste oder Prozesse bestehen. Diese können mehrere ASP.NET Web-API-Dienste oder eine beliebige andere Art von Diensten, die über HTTP oder ein anderes Protokoll sein. Vor allem konnte die Dienste die gleichen Daten freigeben, solange dieser Dienste kann in Bezug auf die gleichen Business-Domäne sind.

![](./media/image8.png)

**Abbildung 4 – 8**. Business Microservice mit verschiedenen physischen-Diensten

Die Dienste im Beispiel Freigabe das gleiche Datenmodell aus, da die Web-API-Dienst die gleichen Daten wie der Search-Dienst gerichtet ist. Daher sind Sie in der physischen Implementierung der Business Microservice, diese Funktion, damit Sie jeden dieser Dienste interne nach oben oder unten skaliert werden können, je nach Bedarf aufteilen. Vielleicht Instanzen der Web-API-Dienst muss in der Regel mehr als der Search-Dienst (oder umgekehrt).)

Kurz gesagt, muss die logische Architektur des Microservices immer nicht mit der physischen Bereitstellungsarchitektur übereinstimmen. In diesem Handbuch Wenn wir ein Microservice erwähnt eine Business oder gemeint logische Microservice, die auf einem oder mehreren Diensten zugeordnet werden konnte. In den meisten Fällen werden einem einzelnen Dienst, jedoch ist es möglicherweise weitere.


>[!div class="step-by-step"]
[Vorherigen] (Data-Hoheit-pro-microservice.md) [weiter] (distributed-Daten-management.md)
