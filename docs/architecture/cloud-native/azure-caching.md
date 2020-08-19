---
title: Zwischenspeichern einer cloudnativen Anwendung
description: Erfahren Sie mehr über das Zwischenspeichern von Strategien in einer Cloud-native Anwendung.
author: robvet
ms.date: 05/17/2020
ms.openlocfilehash: a33f143499b5f9545493bc4bc757cc3d152f7aa9
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557515"
---
# <a name="caching-in-a-cloud-native-app"></a>Caching in einer cloudbasierten App

Die Vorteile der Zwischenspeicherung sind gut verständlich. Das Verfahren funktioniert durch temporäres kopieren häufig aufgerufene Daten aus einem Back-End-Datenspeicher in einen *schnellen Speicher* , der sich näher an der Anwendung befindet. Caching wird häufig implementiert, wenn...

- Die Daten bleiben relativ statisch.
- Der Datenzugriff ist langsam, insbesondere im Vergleich zur Geschwindigkeit des Caches.
- Daten unterliegen hohen Konflikten.

## <a name="why"></a>Warum?

Wie im Leitfaden zum [Microsoft Caching](https://docs.microsoft.com/azure/architecture/best-practices/caching)erläutert, kann die Zwischenspeicherung die Leistung, Skalierbarkeit und Verfügbarkeit für einzelne und das System als Ganzes verbessern. Es verringert die Latenz und die Konflikte bei der Verarbeitung großer Mengen gleichzeitiger Anforderungen an einen Datenspeicher. Wenn sich das Datenvolumen und die Anzahl der Benutzer erhöhen, sind die Vorteile der Zwischenspeicherung umso größer.

Das Zwischenspeichern ist am effektivsten, wenn ein Client wiederholt Daten liest, die unveränderlich sind oder sich nur selten ändern. Beispiele hierfür sind Referenzinformationen, z. b. Produkt-und Preisinformationen, oder freigegebene statische Ressourcen, die teuer zu erstellen sind.

Während die Zustands losen Dienste zustandslos sein sollten, kann ein verteilter Cache den gleichzeitigen Zugriff auf Sitzungszustandsdaten bei Bedarf unterstützen.

Beachten Sie auch Caching, um wiederkehrende Berechnungen zu vermeiden. Wenn ein Vorgang Daten transformiert oder eine komplizierte Berechnung durchführt, wird das Ergebnis für nachfolgende Anforderungen zwischengespeichert.

## <a name="caching-architecture"></a>Cachingarchitektur

Native Cloud-Anwendungen implementieren in der Regel eine verteilte zwischen Speicherungs Architektur. Der Cache wird als cloudbasierter [Sicherungsdienst](./definition.md#backing-services)(getrennt von den-Diensten) gehostet. In Abbildung 5-15 wird die Architektur dargestellt.

![Zwischenspeichern in einer nativen Cloud-App](media/caching-in-a-cloud-native-app.png)

**Abbildung 5-15**: Zwischenspeichern in einer nativen Cloud-App

Beachten Sie in der obigen Abbildung, wie der Cache von den-und-Diensten unabhängig ist und von diesen gemeinsam genutzt wird. In diesem Szenario wird der Cache vom [API-Gateway](./front-end-communication.md)aufgerufen. Wie in Kapitel 4 erläutert, fungiert das Gateway als Front-End für alle eingehenden Anforderungen. Der verteilte Cache erhöht die Reaktionsfähigkeit des Systems durch die Rückgabe von zwischengespeicherten Daten nach Möglichkeit. Wenn Sie den Cache von den Diensten trennen, kann der Cache außerdem unabhängig voneinander zentral hoch-oder herunterskaliert werden, um größere Datenverkehrs Anforderungen zu erfüllen.

Die vorherige Abbildung zeigt ein gängiges zwischen Speicherungs Muster, das als [Cache Abbild Muster](https://docs.microsoft.com/azure/architecture/patterns/cache-aside)bezeichnet wird. Bei einer eingehenden Anforderung Fragen Sie zuerst den Cache (Schritt \# 1) nach einer Antwort ab. Wenn Sie gefunden werden, werden die Daten sofort zurückgegeben. Wenn die Daten im Cache (als [Cache](https://www.techopedia.com/definition/6308/cache-miss)Fehler bezeichnet) nicht vorhanden sind, werden Sie aus einer lokalen Datenbank in einem Downstreamdienst abgerufen (Schritt \# 2). Sie wird dann für zukünftige Anforderungen in den Cache geschrieben (Schritt \# 3) und an den Aufrufer zurückgegeben. Es muss darauf geachtet werden, dass zwischengespeicherte Daten regelmäßig entfernt werden, damit das System rechtzeitig und konsistent bleibt.

Wenn ein frei gegebener Cache wächst, kann es sich als vorteilhaft erweisen, seine Daten über mehrere Knoten hinweg zu partitionieren. Dies kann helfen, Konflikte zu minimieren und die Skalierbarkeit zu verbessern. Viele Caching-Dienste unterstützen die Fähigkeit, Knoten dynamisch hinzuzufügen und zu entfernen und Daten über mehrere Partitionen hinweg neu auszugleichen. Diese Vorgehensweise umfasst in der Regel Clustering. Clustering macht eine Auflistung von Verbund Knoten als nahtlosen, einzelnen Cache verfügbar. Intern werden die Daten jedoch auf die Knoten verteilt, die auf eine vordefinierte Verteilungs Strategie folgen, die die Last gleichmäßig ausgleicht.

## <a name="azure-cache-for-redis"></a>Azure Cache for Redis

[Azure Cache für redis](https://azure.microsoft.com/services/cache/) ist ein sicherer Daten Cache-und Messaging Broker Dienst, der vollständig von Microsoft verwaltet wird. Dieses Angebot wird als Platform-as-a-Service-Angebot (Platform-as-a-Service, PAS) genutzt und bietet einen hohen Durchsatz und geringe Latenz Der Dienst ist für jede Anwendung innerhalb oder außerhalb von Azure zugänglich.

Der Azure Cache for redis-Dienst verwaltet den Zugriff auf Open Source-redis-Server, die in Azure-Rechenzentren gehostet werden. Der-Dienst fungiert als Fassade, die Verwaltung, Zugriffs Steuerung und Sicherheit bereitstellt. Der Dienst unterstützt nativ einen umfangreichen Satz von Datenstrukturen, einschließlich Zeichen folgen, Hashes, Listen und Sets. Wenn Ihre Anwendung bereits redis verwendet, funktioniert Sie mit Azure Cache for redis unverändert.

Azure Cache für redis ist mehr als ein einfacher Cache Server. Es kann eine Reihe von Szenarien unterstützen, um eine microservices-Architektur zu verbessern:

- Ein in-Memory-Datenspeicher
- Eine verteilte nicht relationale Datenbank
- Ein Nachrichten Broker
- Einen Konfigurations-oder Ermittlungs Server
  
Für erweiterte Szenarien kann eine Kopie der zwischengespeicherten Daten [auf dem](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-how-to-premium-persistence)Datenträger persistent gespeichert werden. Wenn ein schwerwiegender Ereignis sowohl den primären als auch den Replikat Cache deaktiviert, wird der Cache aus der neuesten Momentaufnahme rekonstruiert.

Azure redis Cache ist für eine Reihe vordefinierter Konfigurationen und Tarife verfügbar. Der [Premium](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-overview#service-tiers) -Tarif bietet viele Features auf Unternehmensebene, z. b. Clustering, Daten Persistenz, georeplikation und Virtual-Network-Isolation.

>[!div class="step-by-step"]
>[Zurück](relational-vs-nosql-data.md)
>[Weiter](elastic-search-in-azure.md)
