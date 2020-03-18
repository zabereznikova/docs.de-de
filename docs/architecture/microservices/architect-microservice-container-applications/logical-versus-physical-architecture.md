---
title: Logische und physische Architektur im Vergleich
description: Unterschiede verstehen zwischen logischer und physischer Architektur
ms.date: 09/20/2018
ms.openlocfilehash: 8d1bfca190eb9b18d46625fa4afdec963eb07054
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834401"
---
# <a name="logical-architecture-versus-physical-architecture"></a>Logische und physische Architektur im Vergleich

Zunächst einmal soll der Unterschied zwischen logischer und physischer Architektur beschrieben und erläutert werden, wie diese Architekturen auf das Design von auf einem Microservice basierenden Anwendungen anwendbar sind.

Für das Erstellen von Microservices sind keine spezifischen Technologien erforderlich. Beispielsweise sind keine Docker-Container erforderlich, um eine auf einem Microservice basierende Architektur zu erstellen. Diese Microservices könnten auch als einfache Prozesse ausgeführt werden. Microservices bauen auf einer logischen Architektur auf.

Zudem ist diese Parität eines Unternehmensmicroservice und physischem Dienst oder Container nicht immer erforderlich, wenn Sie eine umfangreiche und komplexe Anwendung erstellen, die aus dutzenden oder sogar hunderten von Diensten besteht. Dies ist auch nicht der Fall, wenn ein Microservice physisch als einzelner Dienst, Prozess oder Container implementiert werden könnte (der Einfachheit halber wird dieser Ansatz in der ersten Version von [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) angewendet).

In diesem Zusammenhang besteht ein Unterschied zwischen der logischen und der physischen Architektur einer Anwendung. Die logische Architektur und die logischen Begrenzungen eines Systems können nicht in jeder einzelnen Komponente der physischen Architektur bzw. der Bereitstellungsarchitektur zugeordnet werden. Dies ist zwar möglich, allerdings ist es nur selten der Fall.

Auch wenn Sie möglicherweise einen bestimmten Unternehmensmicroservice oder einen begrenzten Kontext ermittelt haben, bedeutet dies nicht, dass die Erstellung eines einzelnen Diensts (z.B. eine ASP.NET-Web-API) oder eines einzelnen Docker-Containers für jeden Unternehmensmicroservice immer die beste Möglichkeit darstellt, diese zu implementieren. Wenn Sie über eine Regel verfügen, die festlegt, dass jeder Unternehmensmicroservice über einen einzelnen Dienst oder Container implementiert werden muss, schränkt Sie das zu sehr ein.

Aus diesem Grund handelt es sich bei einem Unternehmensmicroservice oder bei einem begrenzten Kontext um eine logische Architektur, die sich möglicherweise mit der physischen Architektur überschneidet. Wichtig ist, dass der Unternehmensmicroservice oder der begrenzte Kontext autonom sind. Dies erreichen Sie, indem Sie zulassen, dass für Codes und Zustand unabhängige Versionen erstellt und diese unabhängig bereitgestellt und skaliert werden.

Wie in der Abbildung 4-8 dargestellt, kann der Katalogunternehmensmicroservice ggf. aus mehreren Diensten oder Prozessen bestehen. Dabei kann es sich um mehrere ASP.NET-Web-API-Dienste oder um beliebige Dienste handeln, die HTTP oder ein beliebiges anderes Protokoll verwenden. Vor allem können die Dienste ggf. alle auf dieselben Daten zugreifen, solange sie sich eine Geschäftsdomäne teilen.

![Diagramm des Unternehmensmicroservice für den Katalog mit physischen Servern.](./media/logical-versus-physical-architecture/multiple-physical-services.png)

**Abbildung 4-8**. Unternehmensmicroservice mit mehreren physischen Diensten

Die Dienste in diesem Beispiel verfügen alle über dasselbe Datenmodell, da der Web-API-Dienst auf dieselben Daten ausgerichtet ist wie der Suchdienst. D.h., Sie teilen diese Funktion für die physische Implementierung des Unternehmensmicroservices auf, damit Sie diese internen Dienste nach Belieben zentral hoch- oder herunterskalieren können. Es kann sein, dass der Web-API-Dienst mehr Instanzen benötigt als der Suchdienst – oder umgekehrt.

Zusammenfassend lässt sich sagen, dass sich die logische Architektur von Microservices nicht immer mit der physischen Bereitstellungsarchitektur überschneiden muss. In diesem Handbuch ist mit dem Begriff „Microservice“ immer ein logischer Microservice oder ein Unternehmensmicroservice gemeint, der mindestens einem (physischen) Dienst zugeordnet werden kann. In den meisten Fällen handelt es sich nur um einen einzelnen Dienst. Es können aber auch mehr Dienste zugeordnet werden.

>[!div class="step-by-step"]
>[Zurück](data-sovereignty-per-microservice.md)
>[Weiter](distributed-data-management.md)
