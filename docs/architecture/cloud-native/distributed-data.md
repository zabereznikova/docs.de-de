---
title: Verteilte Daten
description: Architektur von Cloud Native .net-apps für Azure | Verteilte Daten für Native Cloud-apps
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841810"
---
# <a name="distributed-data-for-cloud-native-apps"></a>Verteilte Daten für Native Cloud-apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Beim Erstellen eines cloudbasierten Systems, das aus vielen unabhängigen mikrodiensten besteht, sollten Sie sich mit Datenspeicher Änderungen beschäftigen.

Herkömmliche monolithische Anwendungen bevorzugen einen zentralisierten Datenspeicher, der in Abbildung 5-1 dargestellt wird.

![Einzelne monolithische Datenbank](./media/single-monolithic-database.png)

**Abbildung 5–1**. Einzelne monolithische Datenbank

Beachten Sie in der vorherigen Abbildung, wie alle Anwendungskomponenten eine einzelne relationale Datenbank nutzen.

Dieser Ansatz bietet viele Vorteile. Das Abfragen von Daten, die auf mehrere Tabellen verteilt sind, ist ganz einfach. es ist einfach, [ACID-Transaktionen](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) zu implementieren, die die Datenkonsistenz sicherstellen. Sie verfügen immer über eine *sofortige Konsistenz*: entweder all Ihre Daten Updates oder keine von Ihnen.

Cloud-Native Systeme bevorzugen eine in Abbildung 5-2 gezeigte Datenarchitektur, in der jeder microservice seine eigenen Daten besitzt und kapselt.

![Mehrere Datenbanken über mehrere mikroservices hinweg](./media/data-across-microservices.png)

**Abbildung 5-2**. Mehrere Datenbanken über mehrere mikroservices hinweg

Beachten Sie, dass in der vorherigen Abbildung jeder microservice den IT-Datenspeicher besitzt und kapselt und nur Daten für die Außenwelt von der öffentlichen API verfügbar macht.

Mit diesem Modell können sich die einzelnen mikrodienste unabhängig voneinander weiterentwickeln, ohne dass Datenschema Änderungen mit anderen-Diensten koordiniert werden müssen. Jeder-mikrodienst kann den Datenspeicher (relationale Datenbank, dokumentdatenbank, Schlüssel-Wert-Speicher), der seinen Anforderungen am besten entspricht, implementieren. Zur Laufzeit kann jeder-Dienst seine Daten entsprechend skalieren. Dies wird in Abbildung 5-3 dargestellt:

![Polyglot-Daten Persistenz](./media/polyglot-data-persistence.png)

**Abbildung 5-3**. Polyglot-Daten Persistenz

Beachten Sie, dass in der obigen Abbildung die Inventur-und Inventur-Inventur relationale Datenbanken, den mikrodienst Bestellung, eine nosql-dokumentdatenbank und den waren Korb-mikrodienst, bei dem es sich um einen externen Schlüsselwert Speicher handelt, übernehmen. Relationale Datenbanken sind zwar für neuronale Datenbanken mit komplexen Daten relevant, aber nosql-Datenbanken haben beträchtliche Beliebtheit erzielt, sodass Sie Anpassbarkeit, schnelle Suche und hohe Verfügbarkeit bieten. Die Schema lose Natur ermöglicht Entwicklern, von einer Architektur typisierter Daten Klassen und ORMs zu wechseln, die die kostenaufwendig und zeitaufwändig gestalten.

>[!div class="step-by-step"]
>[Zurück](service-mesh-communication-infrastructure.md)
>[Weiter](data-patterns.md)
