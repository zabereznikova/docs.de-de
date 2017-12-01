---
title: Entwerfen der Anwendungsschicht Microservice und Web-API
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Entwerfen der Anwendungsschicht Microservice und Web-API"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Entwerfen der Anwendungsschicht Microservice und Web-API

## <a name="using-solid-principles-and-dependency-injection"></a>EINFARBIG Prinzipien und Abhängigkeitsinjektion verwenden

EINFARBIGE Prinzipien sind wichtige Techniken, mit denen in jeder modernen und unternehmenswichtigen Anwendung, z. B. ein Microservice mit DDD Mustern entwickeln verwendet werden. EINFARBIG ist ein Akronym, Gruppen fünf grundlegenden Prinzipien:

-   Einzelne Verantwortung Prinzip

-   Prinzip öffnen/schließen

-   Liskovsche Ersetzung Prinzip

-   Die Umkehrung Trennung Prinzip

-   Abhängigkeit Umkehrung Prinzip

DURCHGEZOGEN gibt mehr zu, wie Sie Ihre Anwendung oder eine interne Ebenen Microservice entwerfen und zu entkoppeln von Abhängigkeiten zwischen ihnen. Es ist nicht mit der Domäne, jedoch zu technischen Entwurf der Anwendung verknüpft. Das endgültige Prinzip, das Prinzip Abhängigkeit Umkehrung (DI) können Sie vom Rest der Ebenen, die Infrastrukturebene entkoppeln dadurch eine bessere entkoppelte Implementierung DDD Ebenen.

DI ist eine Möglichkeit, implementieren das Prinzip die Umkehrung der Abhängigkeit. Es ist eine Technik zum Erreichen einer losen Kopplung zwischen Objekten und ihren Abhängigkeiten. Statt direkt instanziieren Projektmitarbeiter oder der Code statische Verweise verwenden, werden die Objekte, die eine Klasse benötigt wird, um die Aktionen bereitgestellt, um (oder "in die eingefügten") der Klasse. In den meisten Fällen werden Klassen deklarieren, deren Abhängigkeiten über ihren Konstruktor, der ihnen ermöglicht, dem expliziten Abhängigkeiten Prinzip folgen. DI basiert in der Regel auf bestimmte Inversion of Control (IoC)-Container. ASP.NET Core bietet einen einfache, integrierte IoC-Container, aber Sie können auch Ihre bevorzugten IoC-Container, z. B. Autofac oder Ninject.

Anhand der VOLLTONFARBE Prinzipien werden Ihre Klassen natürlich tendenziell klein, gut ausgearbeitete und einfache Weise getestet werden. Doch wie können Sie beurteilen, wenn zu viele Abhängigkeiten in Ihren Klassen eingefügt wird, werden? Bei Verwendung von DI durch den Konstruktor werden leicht, die anhand der Anzahl von Parametern für den Konstruktor erkannt. Wenn zu viele Abhängigkeiten vorhanden sind, ist dies in der Regel ein Vorzeichen (eine [code Geruch](http://deviq.com/code-smells/)), dass Ihre Klasse zu viele Vorgänge versucht und ist wahrscheinlich das Prinzip der einzigen Verantwortung verletzen.

Es würde eine andere Anleitung zur DURCHGEZOGEN ausführlich behandelt. Dieses Handbuch erfordert daher nur eine minimale Kenntnisse in diesen Themen.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **DURCHGEZOGEN: Grundlegende OOP-Prinzipien**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Die Umkehrung der Steuerelementcontainer und dem Muster Abhängigkeitsinjektion**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. Neue Gerätekontenverzeichnisses ist**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Vorherigen] (Nosql-Datenbank-Persistenz-infrastructure.md) [weiter] (Microservice-application-layer-implementation-web-api.md)
