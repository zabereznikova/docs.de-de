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
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="703e8-103">Verteilte Daten für Native Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="703e8-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="703e8-104">Beim Erstellen eines cloudbasierten Systems, das aus vielen unabhängigen mikrodiensten besteht, sollten Sie sich mit Datenspeicher Änderungen beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="703e8-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="703e8-105">Herkömmliche monolithische Anwendungen bevorzugen einen zentralisierten Datenspeicher, der in Abbildung 5-1 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="703e8-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![Einzelne monolithische Datenbank](./media/single-monolithic-database.png)

<span data-ttu-id="703e8-107">**Abbildung 5–1**.</span><span class="sxs-lookup"><span data-stu-id="703e8-107">**Figure 5-1**.</span></span> <span data-ttu-id="703e8-108">Einzelne monolithische Datenbank</span><span class="sxs-lookup"><span data-stu-id="703e8-108">Single monolithic database</span></span>

<span data-ttu-id="703e8-109">Beachten Sie in der vorherigen Abbildung, wie alle Anwendungskomponenten eine einzelne relationale Datenbank nutzen.</span><span class="sxs-lookup"><span data-stu-id="703e8-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="703e8-110">Dieser Ansatz bietet viele Vorteile.</span><span class="sxs-lookup"><span data-stu-id="703e8-110">There are many benefits to this approach.</span></span> <span data-ttu-id="703e8-111">Das Abfragen von Daten, die auf mehrere Tabellen verteilt sind, ist ganz einfach. es ist einfach, [ACID-Transaktionen](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) zu implementieren, die die Datenkonsistenz sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="703e8-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="703e8-112">Sie verfügen immer über eine *sofortige Konsistenz*: entweder all Ihre Daten Updates oder keine von Ihnen.</span><span class="sxs-lookup"><span data-stu-id="703e8-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="703e8-113">Cloud-Native Systeme bevorzugen eine in Abbildung 5-2 gezeigte Datenarchitektur, in der jeder microservice seine eigenen Daten besitzt und kapselt.</span><span class="sxs-lookup"><span data-stu-id="703e8-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![Mehrere Datenbanken über mehrere mikroservices hinweg](./media/data-across-microservices.png)

<span data-ttu-id="703e8-115">**Abbildung 5-2**.</span><span class="sxs-lookup"><span data-stu-id="703e8-115">**Figure 5-2**.</span></span> <span data-ttu-id="703e8-116">Mehrere Datenbanken über mehrere mikroservices hinweg</span><span class="sxs-lookup"><span data-stu-id="703e8-116">Multiple databases across microservices</span></span>

<span data-ttu-id="703e8-117">Beachten Sie, dass in der vorherigen Abbildung jeder microservice den IT-Datenspeicher besitzt und kapselt und nur Daten für die Außenwelt von der öffentlichen API verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="703e8-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="703e8-118">Mit diesem Modell können sich die einzelnen mikrodienste unabhängig voneinander weiterentwickeln, ohne dass Datenschema Änderungen mit anderen-Diensten koordiniert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="703e8-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="703e8-119">Jeder-mikrodienst kann den Datenspeicher (relationale Datenbank, dokumentdatenbank, Schlüssel-Wert-Speicher), der seinen Anforderungen am besten entspricht, implementieren.</span><span class="sxs-lookup"><span data-stu-id="703e8-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="703e8-120">Zur Laufzeit kann jeder-Dienst seine Daten entsprechend skalieren.</span><span class="sxs-lookup"><span data-stu-id="703e8-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="703e8-121">Dies wird in Abbildung 5-3 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="703e8-121">This is shown in Figure 5-3:</span></span>

![Polyglot-Daten Persistenz](./media/polyglot-data-persistence.png)

<span data-ttu-id="703e8-123">**Abbildung 5-3**.</span><span class="sxs-lookup"><span data-stu-id="703e8-123">**Figure 5-3**.</span></span> <span data-ttu-id="703e8-124">Polyglot-Daten Persistenz</span><span class="sxs-lookup"><span data-stu-id="703e8-124">Polyglot data persistence</span></span>

<span data-ttu-id="703e8-125">Beachten Sie, dass in der obigen Abbildung die Inventur-und Inventur-Inventur relationale Datenbanken, den mikrodienst Bestellung, eine nosql-dokumentdatenbank und den waren Korb-mikrodienst, bei dem es sich um einen externen Schlüsselwert Speicher handelt, übernehmen.</span><span class="sxs-lookup"><span data-stu-id="703e8-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="703e8-126">Relationale Datenbanken sind zwar für neuronale Datenbanken mit komplexen Daten relevant, aber nosql-Datenbanken haben beträchtliche Beliebtheit erzielt, sodass Sie Anpassbarkeit, schnelle Suche und hohe Verfügbarkeit bieten.</span><span class="sxs-lookup"><span data-stu-id="703e8-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="703e8-127">Die Schema lose Natur ermöglicht Entwicklern, von einer Architektur typisierter Daten Klassen und ORMs zu wechseln, die die kostenaufwendig und zeitaufwändig gestalten.</span><span class="sxs-lookup"><span data-stu-id="703e8-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="703e8-128">[Zurück](service-mesh-communication-infrastructure.md)
>[Weiter](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="703e8-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
